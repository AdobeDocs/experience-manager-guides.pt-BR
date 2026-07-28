---
title: Migração de alterações da estrutura de extensão para o Editor 2.0
description: Saiba mais sobre a migração para a estrutura de extensão do Editor 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 75954eab3ac1738705fe2a7280973af39b9214df
workflow-type: tm+mt
source-wordcount: '1904'
ht-degree: 0%

---


# Migrar estrutura de extensão para o Editor 2.0 (Novo editor)

Este guia ajuda os autores de extensões a entender o que está envolvido na movimentação de suas personalizações do **Antigo Editor** para o **Novo Editor** no AEM Guides, para que eles possam planejar sua transição sem problemas e com o mínimo de interrupção.

>[!IMPORTANT]
> 
> Se você tiver uma extensão do AEM Guides existente (Editor antigo), incluindo itens de menu de contexto personalizados, botões da barra de ferramentas, caixas de diálogo, lógica de atributos ou metadados ou estilo de conteúdo, este guia ajudará a mantê-lo funcionando com o Novo editor.

## Visão geral

- **Seu registro não é alterado**: Continue usando o `window.extension` / `tcx.extension.register`.
- **A tela do Editor é uma nova superfície.** Os itens do menu de contexto devem declarar a nova identificação do widget
  `markup_editor_menu`; o comportamento no editor deve parar de tocar no DOM.
- **Parar de ler/gravar o DOM**: substituir o acesso DOM `tcx.curEditor.*` pelo
  API `guides.editor`: [ler com `runUtil(...)`](#migrate-reads-dom-runutil), [gravar com `runCommand(...)`](#migrate-writes-dom-mutation-runcommand), [estilo com decorações](#migrate-rendering-only-logic-dom-paint-decorations) e [executar ações globais (salvar) por meio de eventos de aplicativo](#migrate-global-actions-savefocus-app-events).
- **Os menus do App-Shell (repositório, visualizador de mapa, arquivo/pasta) permanecem inalterados**: eles ainda são executados em
estrutura herdada.
- **Ambos os editores coexistem**: direcione ambos com matrizes. Ao carregar **Registrar** plug-ins incondicionalmente; limitar apenas *tempo de execução* ações por `guides.editor.version` (que permanece `1.0.0` até que um arquivo seja aberto, exibir [Detectar o editor e a inicialização com segurança](#detect-the-Editor-and-bootstrap-safely)).


## Por que a mudança?

| Critérios | CKEditor herdado | Novo MarkupEditor |
|---|---|---|
| Source da verdade | DOM | Documento ProseMirror |
| Seleção | `getSelection()` em um documento raiz | Seleção de ProseMirror (posições/intervalos) |
| Para alterar o conteúdo | Modificar atributos/classes DOM | Enviar um comando (transação) |
| Renderização | DOM é permanente | DOM é um renderizador efêmero em um DOM sombra, reconstruído a qualquer momento |
| Estilo | CSS de page ou clientlib | O CSS injetou o DOM de sombra por meio do plug-in de registro. Consulte [Olá, mundo: um plug-in de destaque somente CSS](#hello-world-a-css-only-highlight-plugin) para o para usar classes existentes e adicionar CSS e [Migrar lógica somente de renderização](#migrate-rendering-only-logic-dom-paint-decorations) para adicionar uma nova classe e adicionar estilo. |

Qualquer extensão que altere o DOM ou qualquer alteração do DOM não é mantida, ela é eliminada na próxima renderização. Basicamente, a migração é *mover de DOM-first para model-first*.

## Detectar o editor e a inicialização com segurança

O objeto global `guides` é o ponto de entrada para todas as novas integrações:

```js
guides.editor    // editor interaction APIs
guides.util      // bundled utility libs (lodash, async)
guides.ready(cb) // fires once at app load (view system ready) — before any file is open
```

`guides.editor.version` relata o **editor aberto no momento**, portanto, isso só é significativo uma vez
o arquivo está realmente aberto:

| `guides.editor.version` | Significado |
|---|---|
| `2.0.0` | Um arquivo MarkupEditor (ProseMirror) está aberto |
| `1.0.0` | Um arquivo CKEditor herdado está aberto ou nenhum arquivo está aberto ainda |

>[!IMPORTANT]
>
> Quando o evento `guides.ready` ocorrer, nenhum arquivo foi aberto ainda, portanto, `version` será relatado como `1.0.0`, independentemente do MarkupEditor estar habilitado. Não use `version` para determinar se os plug-ins são *registrados* (exibir [Registro de Plug-ins e Classificação de Tempo de Execução](#plugin-registration-and-runtime-gating)). Use-o somente para ramificar o comportamento *runtime* e avaliá-lo no ponto de execução (por exemplo, em um manipulador de menu), onde um arquivo tem garantia de estar aberto.

### Registro de plug-in e marcação em tempo de execução

- **Registro** (`registerPlugin`, configuração única): Execute-o **incondicionalmente** em `guides.ready`. É uma operação inútil no editor herdado: o editor herdado nunca lê o registro do plug-in e sua fábrica é executada somente quando um MarkupEditor é realmente construído. Ele faz **não** lançamento.

- **Chamadas em tempo de execução** (`runCommand`, `runUtil`, `addDecoration`, ...): a porta por versão existe e não é igual a &quot;1.0.0&quot; no momento da chamada. Eles não são acionados no editor herdado (retornam com segurança `false`/`undefined`), mas a marcação evita avisos de operação inútil e permite que você mantenha um fallback herdado.

```js
guides.ready(() => {
  // Always register — inert on legacy, applied only when a MarkupEditor opens.
  guides.editor.registerPlugin(createMyPlugin);
});

function onMenuClick() {
  if (guides.editor.version && guides.editor.version !== "1.0.0") {
    guides.editor.runCommand('surroundWithElement', 'sup'); // MarkupEditor path
  } else {
    // legacy path (or no-op)
  }
}
```

Passar uma **fábrica** `() => ({ plugin, css })` — para `registerPlugin`, nunca uma instância de plug-in construída. Uma não função é a única entrada que ela rejeita (acionada em ambos os editores). Não armazenar a instância do editor em cache; chamar `guides.editor.*` novamente sempre.

### Olá, mundo: um plug-in de destaque somente para CSS

A menor extensão útil envia **somente CSS** um plug-in ProseMirror sem operação e estilos. Este
realça cada elemento `<note>` com um plano de fundo amarelo dentro do editor:

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no behavior — CSS only
    css: `[data-xml-element="note"] { background: #fff3cd; outline: 1px solid #ffe08a; }`
  }));
});
```

- Cada elemento é renderizado como `data-xml-element="<tag>"`, para que você possa direcionar qualquer elemento DITA dessa forma
(`note`, `codeblock`, `section`, `table`, ...).
- O CSS **deve** ser enviado por meio do registerPlugin: o editor reside em um DOM de sombra, portanto, o CSS page/clientlib não pode
alcance-o.
- Abra um tópico DITA contendo um `<note>` para vê-lo aplicado. O registro é incondicional (§ 2.1),
portanto, isto é seguro mesmo que `version` ainda seja `1.0.0` às `guides.ready` hora.


## Inventariar sua extensão (lista de verificação grep)

```bash
# DOM-first reads that will break
grep -rnE "rootDocument|rootElement|getSelection\(|selectedHtml|selectedText|\.xmlDoc|\.ancestors\b" src

# DOM/legacy writes that will break
grep -rnE "updateAttributes\(|setAttribute\(|classList\.|\.saveFile\(|resetDirty\(|validateRangeForInsertion\(" src

# The editor handle itself
grep -rn "tcx.curEditor" src

# Context-menu targeting + page CSS
grep -rnE "contextMenuWidget|dita_editor_menu|author_outline_element" src
grep -rn "dita_content_overrides" .
```

Cada ocorrência é um item de migração. Classificar cada uma como: *superfície de menu de contexto*, *estado lido*, *conteúdo
gravação*, *ação global*, *somente renderização* ou *CSS*.


## Comum para ambos os editores

Os comportamentos e estruturas a seguir se aplicam de forma idêntica a ambos os Editores:

- **Registro:** `window.extension[id] = config` e/ou `tcx.extension.register(id, config)` em
o evento `tcx-loaded`.
- **Forma do objeto de configuração:** `{ id, contextMenuWidget, view: { items }, controller }`.
- **Os menus de contexto do App-shell** mantêm suas IDs de widget existentes e o comportamento herdado:

  | Superficial | ID do widget (inalterada) |
  |---|---|
  | Painel Repositório (arquivo/pasta) | `repository_panel` / `file_options` / `folder_options` |
  | Visualizador de mapa | `ditamap_viewer` / `map_view_options` |
  | Painéis de linha de base/predefinidos | `baseline_panel_menu` / `preset_item_menu` |

  Os itens direcionados a estas superfícies não precisam de **nenhuma alteração** para o Novo Editor. Não os mova para
  `markup_editor_menu`.

## Referência de substituição de API

| Herdados (`tcx.curEditor…` / DOM) | Novo MarkupEditor |
|---|---|
| `tcx.curEditor.filePath` | `guides.editor.filePath` |
| `getSelection()` / `selectedHtml` / `selectedText` | `runUtil('getSelectedXml' / 'getSelectedPlainText' / 'hasSelection')` |
| `rootDocument.querySelector(tag)` | `runUtil('findPositionRange' / 'findPositionRanges', tag)` |
| elemento `.getAttribute` / `xmlDoc.attributes` | `runUtil('getAttributeAtPosition', pos, name)` / `getSerializableAttributes(xpath)` |
| id raiz (`querySelector('[concept]').id`) | `runUtil('getAttributeAtPosition', 0, 'id')` |
| `editor.ancestors` | `runUtil('getAncestorsDetails' / 'getAncestorXpaths')` |
| `editor.updateAttributes(attrs, root)` | `runCommand('setNodeXmlAttributes', 0, attrs)` |
| definir attr no elemento | `runCommand('setNodeXmlAttribute', pos, name, value)` |
| quebrar automaticamente / inserir / quebrar seleção | `runCommand('surroundWithElement' / 'insertXml' / 'unwrapNode', …)` |
| `canInsertXmlElement` / `validateRangeForInsertion` | `canRunCommand(name, …)` / `canInsertXmlElement(tag)` |
| `editor.focus()` | `guides.editor.focus()` |
| `tcx.curEditor.saveFile()` | `tcx.eventHandler.next(KEYS.AUTHOR_SAVE_KEY)` |
| `setAttribute` / `classList` para estilo | `addDecoration` / `batchDecorations` / `registerPlugin` |
| CSS page/clientlib para conteúdo do editor | `registerPlugin({ css })` (DOM de sombra) |
| `contextMenuWidget: 'dita_editor_menu'` | `['dita_editor_menu', 'markup_editor_menu']` |


## Migrar itens do menu de contexto (tela Editor)

Isso se aplica somente a menus que direcionaram o **editor** (`dita_editor_menu`,
`author_outline_element`), ou seja, o menu de navegação estrutural/clique com o botão direito do mouse dentro da superfície de edição.

### Como é roteado no novo editor

```
window.extension[id]  ─►  filtered by contextMenuWidget == 'markup_editor_menu'
                      ─►  view.items rendered in the canvas menu
   (click) ───────────►  fires an extension event:
                          • eventid is a known global key  → run as a built-in editor command
                          • otherwise                       → your controller[eventid]() runs
```

### Adicionar o novo id do widget (a matriz mantém o funcionamento antigo)

```js
// BEFORE
contextMenuWidget: 'dita_editor_menu',
// AFTER
contextMenuWidget: ['dita_editor_menu', 'markup_editor_menu'],
```

### Manter a forma esperada

- Itens acionáveis em `view.items` com um `data.eventid`.
- Cada nome de método `controller` **corresponde** a `eventid` exatamente.

```js
view: {
  items: [{
    displayName: 'Edit Cross Reference',
    icon: 'link',
    data: { eventid: 'editCrossReference' },
    target: { key: 'displayName', value: 'Cut', viewState: 'prepend' }
  }]
},
controller: {
  editCrossReference() { /* runs on click */ }
}
```

### Ancorar novamente `target`

O novo menu resolve `target` em relação aos próprios itens de menu do MarkupEditor.

- `target.key`: `displayName | id | icon | eventid`
- `target.viewState`: `append | prepend | replace`
- Ancorar em um item nativo estável, como **`Cut`**.
- Se a âncora não resolver, o item ainda aparecerá, mas será colocado na posição padrão
(não é um erro, corrija a âncora).

### Escolha o roteiro por item

```js
data: { eventid: 'AUTHOR_CUT' }          // built-in command → routed natively, no controller needed
data: { eventid: 'editCrossReference' }  // custom → runs controller.editCrossReference()
```

Adicione `readOnly: true` em um item que deve permanecer habilitado em conteúdo somente leitura.

### Substituir o corpo do manipulador

Os manipuladores geralmente leem a seleção e alteram um nó, migram-nos do DOM.

## Leituras de migração (DOM: `runUtil`)

```js
// BEFORE — DOM selection / queries
const { editor } = tcx.curEditor;
const html = editor.selectedHtml;
const topicId = editor.rootDocument.querySelector('[data-tcx-tag="concept"]').id;

// AFTER — read from the document model
const selectedXml = guides.editor.runUtil('getSelectedXml');
const hasSel      = !!guides.editor.runUtil('hasSelection'); // check if selection is empty
const topicId     = guides.editor.runUtil('getAttributeAtPosition', 0, 'id'); // root = position 0
```

Localize um nó por tag, corresponda por id e leia um atributo XML:

```js
let value = '';
for (const range of (guides.editor.runUtil('findPositionRanges', 'xref') || [])) {
  const id = guides.editor.runUtil('getAttributeAtPosition', range.from, 'id');
  if (String(id) !== String(targetId)) continue;
  value = guides.editor.runUtil('getAttributeAtPosition', range.from, 'placeholdertext') || '';
  break;
}
```

**Utilitários de leitura:** `getTextPos`, `getNodePosition`, `getSelectedXml`, `getSelectedPlainText`,
`hasSelection`, `getAncestorsNames`, `getAncestorsDetails`, `getAncestorXpaths`,
`findPositionRange`, `findPositionRanges`, `getAttributeAtPosition`, `getSerializableAttributes`. Consulte [Apêndice](#appendix-a-more-exposed-utils-examples).


## Migrar gravações (mutação de DOM: `runCommand`)

```js
// BEFORE
const root = editor.rootElement.findOne('[data-tcx-tag="concept"]');
editor.updateAttributes({ docOwner: 'Jane' }, root);

// AFTER — update the model; persists across rerenders
guides.editor.runCommand('setNodeXmlAttributes', 0, { docOwner: 'Jane' });
```

```js
// Set one attribute at a found position
guides.editor.runCommand('setNodeXmlAttribute', pos, 'placeholdertext', text);

// Wrap / insert / unwrap
guides.editor.runCommand('surroundWithElement', 'sup');
guides.editor.runCommand('insertXml', '<sup></sup>', undefined, { setCursorInContent: true });
guides.editor.runCommand('unwrapNode');
```

**Pré-requisitos**

```js
guides.editor.focus();
if (!guides.editor.canInsertXmlElement('xref')) {
  return tcx.util.showAlert('warning', 'xref is not allowed here'); 
}
if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
  guides.editor.runCommand('surroundWithElement', 'sup');
}
```

**Comandos:** `setNodeXmlAttributes`, `setNodeXmlAttribute`, `surroundWithElement`, `insertXml`,
`unwrapNode`. Consulte [Apêndice](#appendix-b-more-exposed-commands-examples).

## Migrar ações globais (salvar/focalizar: eventos de aplicativo)

```js
// BEFORE
tcx.curEditor?.saveFile?.();
// AFTER
tcx.eventHandler.next(tcx.eventHandler.KEYS.AUTHOR_SAVE_KEY);
```

`resetDirty(...)` e `tcx.curEditor.html` não têm um equivalente a MarkupEditor. Portanto, solte-os; salvando
por meio do evento manipula o estado sujo centralmente. Use `guides.editor.focus()` para foco.


## Migrar lógica somente de renderização (pintura DOM: decorações)

Qualquer coisa que tenha adicionado classes CSS, `data-*` atributos ou &quot;texto de exibição&quot; modificando o DOM deverá
torne-se uma **decoração** ou desaparece na renderização. Abaixo estão casos declarativos simples:

```js
guides.editor.addDecoration('important-sections', 'section', {
  class: 'section-important',
  computeAttributes: (node, ctx) => ({ 'data-number-label': String(ctx.index + 1) }),
  filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
});

guides.editor.batchDecorations([
  { action: 'remove', id: 'legacy-numbering' },
  { action: 'add', id: 'division-numbering', selector: 'conbody', options: { class: 'division-numbering' } }
]);

guides.editor.removeDecoration('important-sections');
guides.editor.clearDecorations();
guides.editor.getDecorations();
```

Casos complexos (estado personalizado, estado interrompido por meio de meta de transação, texto do widget): Registrar um
Plug-in ProseMirror uma vez, usando as bibliotecas expostas:

```js
const createXrefPlugin = () => {
  const { Plugin, PluginKey } = guides.editor.prosemirror.state;
  const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  return {
    plugin: new Plugin({ key: new PluginKey('xrefDisplay'), props: { decorations(state) { /* … */ } } }),
    css: `.xref-broken { text-decoration: underline wavy red; }`
  };
};

guides.ready(() => guides.editor.registerPlugin(createXrefPlugin));
```

Registre os plug-ins no carregamento do aplicativo (uma vez), não em caixas de diálogo ou repetidamente, o registro não exclui a duplicação. `registerPlugin` aceita apenas uma **função de fábrica**, não uma instância de plug-in.
`guides.editor.prosemirror` expõe: `state`, `model`, `view`, `transform`, `commands`, `keymap`,
`history`, `tables`, `dropcursor`, `collab`, `markdown`.


## Migrar CSS (page clientlib → shadow DOM)

O MarkupEditor é renderizado dentro de um **DOM de sombra**; o CSS da biblioteca de cliente da AEM e de nível de página não o atinge.

```js
guides.editor.registerPlugin(() => ({
  plugin: new guides.editor.prosemirror.state.Plugin({}),   // no-op, CSS only
  css: `[data-xml-element="codeblock"] { font-family: monospace; background: #f5f5f5; }`
}));
```

A categoria clientlib do conteúdo herdado (`apps.guides.xml_editor.dita_content_overrides`) ainda
Estila somente o editor herdado, mantenha-o se você oferecer suporte a ambos, mas saiba que está inserido no MarkupEditor.

## Acessando o EditorView ao vivo (plug-in `view` prop): hachura de escape DOM

As decorações e os comandos são a abordagem preferida. No entanto, alguns efeitos não podem ser implementados como decorações. Nesses casos, use a propriedade de plug-in `view` para acessar o `EditorView` ativo e operar em `editorView.dom`. Essa é a única maneira compatível de interagir diretamente com o DOM do editor renderizado.

```js
const createMyPlugin = () => {
  const { Plugin } = guides.editor.prosemirror.state;
  return {
    plugin: new Plugin({
      view(editorView) {
        const root = editorView.dom;          // the shadow-DOM editor node
        const apply = () => { /* re-color / rewrite target nodes in `root` */ };
        apply();
        return {
          update(view, prevState): apply,                       // re-apply after every rerender
          destroy() { /* remove any listeners/observers */ },
        };
      },
    }),
    css: `/* ... */`,
  };
};

guides.ready(() => guides.editor.registerPlugin(createMyPlugin));
```

**Medidas de proteção**:

- Escape apenas hachura, use decorações para classes, rótulos e estilo.
- `editorView.dom` é o único identificador com suporte;
- Aplique novamente a partir de `update()` para que a alteração sobreviva às renderizações; limpe em `destroy()`.

## Ciclo de vida do registro de plug-ins

`registerPlugin` em `guides.ready` registra a fábrica apenas uma vez. A fábrica funciona novamente
cada vez que um arquivo é aberto — cada abertura de arquivo do MarkupEditor o chama para criar o
instância do plug-in.

## Problemas comuns

- Onde o código DOM endereça nós e `Range`s, MarkupEditor endereça **posições**, números inteiros simples indexando no documento (`0` = início do documento, ou seja, a raiz). Um `range` é `{ from, to }`, duas posições delimitando um span, não um DOM `Range`. As posições mudam à medida que o documento muda, portanto, não armazene em cache uma edição.
- **O item não aparece no menu Novo Editor**: `contextMenuWidget` está ausente
  `markup_editor_menu` ou a configuração foi registrada *depois*, o editor abriu (a configuração foi lida
  uma vez no editor (registrar construção no carregamento do aplicativo).
- **O item aparece no local errado**: a âncora `target` não resolve; ancore para um item que
existe no novo menu (por exemplo, `Cut`).
- **Alterar &quot;funciona&quot; e depois desaparecer**: você alterou o DOM. Usar um comando (gravar) ou uma decoração
(estilo) em vez disso.
- **CSS não tem efeito**: é no nível da página; o editor está em um DOM de sombra. Usar `registerPlugin({ css })`.
- **Liberação de protetores inseguros**: padrões como `if (!tcx.curEditor && !tcx.curEditor.editor)` evaluate
  `.editor` em um objeto falsy. Proteger os recursos `guides.editor` em vez disso:
  `if (!guides?.editor) return;`.
- **Tentando migrar menus do shell de aplicativos**: os menus Repositório/mapa/arquivo não são a tela do editor;
deixe-os em suas ids de widget herdadas.

## Lista de verificação de verificação

- Os itens do menu de contexto aparecem em **ambos** os menus legacy e MarkupEditor.
- Os itens chegam na posição esperada.
- Personalizar `eventid` executa `controller[eventid]`; chaves globais acionam o comando interno.
- As leituras de estado retornam valores corretos após digitar/renderizar (modelo, não DOM obsoleto).
- As gravações de conteúdo *persistem após salvar e reabrir*.
- As decorações sobrevivem a uma renderização.
- O CSS Shadow-DOM se aplica visivelmente dentro do editor.
- Salvar é acionado via `AUTHOR_SAVE_KEY` e limpa o estado sujo.
- `readOnly` itens se comportam corretamente no conteúdo bloqueado.
- Visualizar ou lado a lado; o trabalho DOM intencional somente leitura é deixado como está.
- `grep -rn "tcx.curEditor" src` está limpo (ou apenas o restante intencional documentado).
- Plug-ins registrados exatamente uma vez, dentro de `guides.ready`.


## Sequência de implantação sugerida

1. **Bootstrap**: ajustar a configuração em `guides.ready`; registrar plug-ins incondicionalmente e adicionar `version` somente com ações de *tempo de execução* (para obter detalhes, exibir [Registro de Plug-ins e Runtime Gating](#plugin-registration-and-runtime-gating)).
2. **Superfície de menu de contexto**: adicionar `markup_editor_menu`, corrigir `target` âncoras. Os itens agora aparecem.
3. **Leituras**: Migrar leituras de seleção/atributo para `runUtil`.
4. **Gravações**: Migrar mutações para `runCommand`; salva em eventos de aplicativo.
5. **Renderização**: mover o estilo DOM para decorações / `registerPlugin`; mover CSS para o DOM de sombra.
6. **Proteger**: corrija os protetores inseguros, remova o identificador do editor e verifique em ambos os editores.

Migre uma superfície de cada vez e mantenha os caminhos herdados funcionando (matrizes + controle de versão) para
a build de extensão única é executada em ambos os editores durante toda a transição.

## Apêndice A: utilitários mais expostos (exemplos)

Encontre os utilitários abaixo para usar até `runUtil`.

| Util | Params → Retornos | O que faz |
|---|---|---|
| `getTextPos` | `(): { start, end }` | Limites do nó de texto selecionado atual |
| `getValidElementNames` | `(ancestorLevel?): ElementName[]` | Nomes de elementos que podem ser legalmente inseridos/envolvidos na seleção atual. |
| `getValidElementNamesBefore` | `(): ElementName[]` | Nomes de elemento válidos imediatamente antes da seleção atual. |
| `getSelectedText` | `(): string` | Texto bruto selecionado. |
| `getSerializableAttributes` | `(): { [key]: string }` | Mapa de atributo XML do nó atual, digitado pelo nome do atributo. |
| `getTagName` | `(): string \| null` | Nome da tag do nó atual. |
| `hasSelection` | `(): boolean` | Se algum conteúdo está selecionado no momento. |
| `isSelectionEditable` | `(): boolean` | Se a seleção atual pode ser editada. |
| `getAncestorPos` | `(name): number \| undefined` | Posição do ancestral mais próximo com o nome de elemento fornecido, da seleção atual. |
| `getValidWrapNodeElementNames` | `(): ElementName[]` | Nomes de elementos válidos para `wrapNode` na seleção atual. |
| `getValidRenameNodeElementNames` | `(): ElementName[]` | Nomes de elementos para os quais o nó atual pode ser renomeado legalmente. |
| `getValidSurroundElementNames` | `(): ElementName[]` | Nomes de elementos válidos para `surroundWithElement` na seleção atual. |
| `serialize` | `(doc?): string` | Serializa um documento ProseMirror (ou o documento inteiro) para XML. |
| `getSelectedXml` | `(range?): string` | XML da seleção atual ou um intervalo `{ from, to }` explícito. |
| `getRangeXml` | `(xpaths): string` | XML para um ou mais intervalos xpath-object (consulte o xpath caveat do §8 — este é o formulário de objeto, não o formulário de sequência). |
| `mapToXpath` | `(position, doc?): XPathPosition` | Converte uma posição no xpath da forma do objeto. |
| `inverseMap` | `(xpath \| position, doc?): number` | Converte um xpath (ou posição) de forma de objeto de volta para uma posição. |
| `getAncestorsDetails` | `(): { ancestors, previousSibling, nextSibling, currNode } \| undefined` | Cadeia ancestral mais irmãos imediatos do nó atual. |
| `getAncestorsNames` | `(): ElementName[]` | Cadeia ancestral como nomes de elemento somente, para o nó atual. |
| `getPreviousSibling` | `(): ElementName \| undefined` | Nome do elemento irmão anterior. |
| `getNextSibling` | `(): ElementName \| undefined` | Nome do próximo elemento irmão. |
| `getAncestorXpaths` | `(includeNodeAtPosition?): { tag, xpath }[]` | Cadeia ancestral como `{tag, xpath}` pares — xpath do formulário de objeto, não o formulário de sequência de caracteres `updateAttributeByXpath` (§8). |
| `getSelectedPlainText` | `(range?): string` | Texto sem formatação da seleção atual ou de um intervalo explícito. |
| `getDecorations` | `(): string[]` | IDs de todas as decorações aplicadas atualmente. |
| `getResolvedDitaDocumentTitle` | `(props?): string` | Título de exibição resolvido do documento DITA. `props`: `doc` para direcionar um documento específico, `allowedPrefixElements` para permitir elementos de prefixo de título. |

## Apêndice B: Mais comandos expostos (exemplos)

Os comandos abaixo são exemplos adicionais do que é exposto via `guides.editor.runCommand(name, ...args)`.
Guarde qualquer comando com `guides.editor.canRunCommand(name, ...args)` primeiro se ele não puder ser aplicado no contexto atual.

| Comando | Params | O que faz |
|---|---|---|
| `focusEditor` | `()` | Focaliza o editor. |
| `unwrapNode` | `()` | Remove o elemento de encapsulamento na seleção atual, mantendo seus filhos. |
| `surroundWithElement` | `(elementName, attrs?, groupInline?)` | Envolve a seleção atual em um novo elemento em linha/bloco. `attrs`: mapa de atributos XML a ser definido no novo elemento de encapsulamento. |
| `insertXml` | `(xml)` | Insere um fragmento XML no cursor. |
| `replaceSelectionWithXml` | `(xml)` | Substitui a seleção atual pelo XML. |
| `insertText` | `(text)` | Insere texto simples no cursor. |
| `selectNodesFromXpaths` | `(xpaths)` | Seleciona um ou mais nós determinados xpaths de forma de objeto. |
| `delete` | `()` | Exclui a seleção atual. |
| `undo` / `redo` | `()` | Desfazer/refazer padrão. |
| `removeDecoration` | `(id)` | Remove uma única decoração por ID. |
| `clearDecorations` | `()` | Remove todas as decorações no arquivo aberto no momento. |
| `setFileReadOnly` | `(readOnly: boolean)` | Alterna o modo somente leitura para o arquivo. |
| `generateUniqueId` | `()` | Gera e atribui um atributo de identificação exclusivo ao nó atual. |