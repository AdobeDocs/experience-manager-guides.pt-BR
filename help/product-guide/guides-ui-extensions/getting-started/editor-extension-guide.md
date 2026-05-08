---
title: Alterações na estrutura de extensão do Editor 2.0
description: Saiba mais sobre as alterações na estrutura de extensão do Editor 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 2ba8eadcb30faca01170cb13ae2da6fdf7da19c8
workflow-type: tm+mt
source-wordcount: '2003'
ht-degree: 3%

---

# Alterações na estrutura de extensão do Editor 2.0 (Novo editor)

Este documento abrange todas as APIs adicionadas a `guides.editor` (e `guides`) como parte da estrutura de extensão do Novo Editor (editor baseado em ProseMirror). Essas APIs permitem que extensões externas interajam com o editor sem manipulação direta de DOM ou conhecimento de implementação interna.

## Visão geral

O objeto global `guides` é o ponto de entrada para todas as integrações de extensão:

```js
guides.editor    // Editor interaction APIs
guides.util      // Utility libraries (lodash, async)
guides.ready(cb) // Lifecycle hook fires when the editor is fully loaded
```

Todas as APIs do `guides.editor` podem ser chamadas com segurança de controladores de extensão, manipuladores de barra de ferramentas e lógica de caixa de diálogo.

## Ciclo de vida

`guides.ready(callback)`: registra um retorno de chamada para ser executado depois que o gerenciador de exibição de página estiver totalmente carregado. Use isto antes de registrar os plug-ins ou executar qualquer configuração do editor.

**Assinatura:**

```ts
guides.ready(callback: () => void): void
```

**Exemplo:**

```js
guides.ready(() => {
  // Safe to access guides.editor APIs here
  guides.editor.registerPlugin(createMyPlugin);
});
```

## Propriedades do estado do editor

- `guides.editor.filePath`: Retorna o caminho de arquivo do documento ativo no momento.

  **Tipo:** `string | undefined`

  **Exemplo: lendo caminho de arquivo para uma chamada de API de metadados:**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath) {
  tcx.api.getMetadata(filePath).subscribe((metadata) => {
    // use metadata...
    });
  }
  ```

  **Exemplo: lógica condicional baseada no local do arquivo**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath?.endsWith(".ditamap")) {
    // ditamap-specific handling
  }
  ```

- `guides.editor.version`: retorna a cadeia de caracteres da versão do editor carregado no momento.

  | Valor | Editor |
  |---------|------------------------------------|
  | `1.0.0` | CKEditor herdado (`xml_author_view`) |
  | `2.0.0` | Novo editor (baseado em ProseMirror) |

  **Tipo:** `string`

  **Exemplo:**

  ```js
  if (guides.editor.version  === '1.0.0') {
    // CKEditor specific logic 
  }
  ```

- `guides.editor.appState(keyName)`: Lê um valor do modelo de aplicativo por nome de chave.

  **Assinatura:**

  ```ts
  guides.editor.appState(keyName: string): unknown
  ```

  **Exemplo:**

  ```js
  const editorMode = guides.editor.appState('editorMode');
  ```

## Interação do editor

- `guides.editor.focus()`: Define o foco para o editor ativo. Chame isso antes de executar comandos que exigem que o editor tenha foco.

  **Assinatura:**

  ```ts
  guides.editor.focus(): boolean
  ```

  **Exemplo: focalizar antes de inserir o conteúdo**

  ```js
  guides.editor.focus();
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  // ...proceed with wrap or insert
  ```

- `guides.editor.canInsertXmlElement(tagName, insertAfter?)`: Verifica se um determinado elemento XML pode ser inserido na posição atual do cursor.

  **Assinatura:**

  ```ts
  guides.editor.canInsertXmlElement(tagName: string, insertAfter?: boolean): boolean
  ```

  **Exemplo: proteger antes de inserir`<xref>`**

  ```js
  const canInsert = guides.editor.canInsertXmlElement("xref");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "xref is not allowed here");
  }
  ```

  **Exemplo: proteger antes de inserir `<sup>` /`<sub>`**

  ```js
  const canInsert = guides.editor.canInsertXmlElement("sup");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "superscript is not allowed here");
  }
  ```

- `guides.editor.selectCurrentBlockElement()`: seleciona o elemento de nível de bloco atual no editor.

  **Assinatura:**

  ```ts
  guides.editor.selectCurrentBlockElement(): boolean
  ```

  **Exemplo:**

  ```js
  guides.editor.selectCurrentBlockElement();
  ```

- `guides.editor.getValidElementNamesForInsertion(args)`: Retorna uma lista de nomes de elementos XML válidos que podem ser inseridos na posição atual.

  **Assinatura:**

  ```ts
  guides.editor.getValidElementNamesForInsertion(args: {
    insertMode?: 'after' | 'before' | 'rename',
    strict: boolean
  }): string[] | false
  ```

  **Exemplo:**

  ```js
  const validElements = guides.editor.getValidElementNamesForInsertion({
    insertMode: 'after',
    strict: true
  });
  ```

- `guides.editor.updateAttributeByXpath(args)`: atualiza um atributo XML específico em um nó identificado por seu XPath. Delega para o método `updateAttributeByXpath` do editor ativo.

  **Assinatura:**

  ```ts
  guides.editor.updateAttributeByXpath(args: UpdateXpathArgs): any
  ```

## Execução do comando

- `guides.editor.runCommand(commandName, ...args)`: Executa um comando nomeado no Novo Editor. Retorna `true` se o comando for bem-sucedido, `false` caso contrário.

  **Assinatura:**

  ```ts
  guides.editor.runCommand(commandName: string, ...args: any[]): boolean
  ```

  **Comandos disponíveis**

  >[!NOTE]
  >
  > Estabilidade: os comandos listados abaixo fazem parte da interface pública. Seus nomes, assinaturas e comportamento observável são considerados estáveis e mantidos para compatibilidade. Comandos adicionais podem estar presentes no editor; no entanto, eles são internos, não se destinam a uso externo e podem ser alterados ou removidos sem aviso prévio.

  | Categoria | Comando | Argumentos | Descrição |
  |---|---|---|---|
  | Geral | `undo` | _(nenhum)_ | Desfaz a última alteração de documento |
  | Geral | `redo` | _(nenhum)_ | Refaz a última alteração desfeita |
  | Seleção | `select` | `from: number, to?: number` | Seleciona o intervalo de `from` a `to` (ou apenas `from` se `to` for omitido) |
  | Seleção | `cursor` | `pos: number` | Move o cursor para `pos` |
  | Seleção | `selectNodesFromXpaths` | `xpaths: Array<{path: Array<{name: string, count: number}>}>` | Seleciona nós identificados por posições XPath |
  | Formatação | `toggleBold` | _(nenhum)_ | Ativa ou desativa a formatação em negrito na seleção atual |
  | Formatação | `toggleItalic` | _(nenhum)_ | Alterna a formatação em itálico da seleção atual |
  | Formatação | `toggleUnderline` | _(nenhum)_ | Alterna a formatação do sublinhado na seleção atual |
  | Formatação | `toggleFormatting` | `markType: string, allowEmptySelection?: boolean` | Alterna um elemento de formatação (por exemplo, `'b'`, `'i'`, `'sup'`, `'sub'`) na seleção |
  | Inserção | `insertText` | `text: string` | Insere texto sem formatação no cursor |
  | Inserção | `insertXml` | `xml: string, position?: number, options?: InsertXmlOptions` | Insere o XML bruto na posição do cursor ou indicada |
  | Inserção | `insertXmlAfterElement` | `elementName: string, xmlString: string` | Insere o XML imediatamente após o ancestral mais próximo `elementName` correspondente |
  | Inserção | `replaceSelectionWithXml` | `xmlString: string` | Substitui a seleção atual pelo XML fornecido |
  | Operações de nó | `surroundWithElement` | `tagName: string, attrs?: Record<string,unknown>, replaceTextWithEmptyNode?: boolean` | Envolve a seleção atual com o elemento fornecido |
  | Operações de nó | `wrapNode` | `type: string, target?: number, attrs?: Record<string, unknown>` | Envolve o nó em `target` (ou o nó atual) em um elemento de `type` |
  | Operações de nó | `renameNode` | `newNodeName: string` | Renomeia o elemento do nó atual |
  | Operações de nó | `unwrapNode` | _(nenhum)_ | Remove o elemento wrapper do nó atual, mantendo seu conteúdo |
  | Excluir | `deleteSelection` | _(nenhum)_ | Exclui o conteúdo atualmente selecionado |
  | Excluir | `deleteNode` | _(nenhum)_ | Exclui todo o nó atual |
  | Atributos | `setNodeXmlAttributes` | `position: number, attrs: Record<string, unknown>` | Define vários atributos XML no nó em `position` |
  | Atributos | `setNodeXmlAttribute` | `position: number, attrName: string, value: string` | Define um único atributo XML no nó em `position` |
  | Listas | `toggleList` | `listName: 'ol' \| 'ul'` | Alterna o bloco atual entre uma lista do tipo fornecido e um parágrafo |
  | Tabelas | `addRowAfter` | `count?: number` | Adiciona `count` linhas abaixo da linha atual (padrão 1) |
  | Tabelas | `addColumnAfter` | `count?: number` | Adiciona `count` colunas à direita da coluna atual (padrão 1) |
  | Tabelas | `deleteRow` | _(nenhum)_ | Exclui a linha atual |
  | Tabelas | `deleteColumn` | _(nenhum)_ | Exclui a coluna atual |
  | Tabelas | `mergeCells` | _(nenhum)_ | Mescla as células selecionadas no momento |
  | Área de transferência | `copy` | _(nenhum)_ | Copia a seleção atual para a área de transferência |
  | Área de transferência | `cut` | _(nenhum)_ | Recorta a seleção atual para a área de transferência |
  | Localizar e substituir | `setSearchQuery` | `query: string, options?: { caseSensitive?: boolean, regex?: boolean }` | Define a consulta de pesquisa ativa |
  | Localizar e substituir | `findNext` | _(nenhum)_ | Move para a próxima correspondência de pesquisa |
  | Localizar e substituir | `replaceAll` | `replacement?: string` | Substitui cada correspondência da consulta de pesquisa atual por `replacement` |

   - **Exemplo: definir vários atributos em um nó**

     ```js
     guides.editor.runCommand(
       "setNodeXmlAttributes",
       rootRange.from,
       { createdDate: "2024-01-01", author: "Jane Doe" }
     );
     ```

   - **Exemplo: definir um único atributo em um nó**

     ```js
     guides.editor.runCommand(
       "setNodeXmlAttribute",
       range.from,
       "placeholdertext",
       "Chapter 3 — Safety Requirements"
     );
     ```

   - **Exemplo: quebrar seleção com um elemento e definir atributos**

     ```js
     const didWrap = guides.editor.runCommand(
       "surroundWithElement",
       "ph",
       { outputclass: "highlight" },
       true   // replace text content with empty node
     );
     ```

   - **Exemplo: Quebrar seleção automaticamente em `<sup>` (ativar/desativar sobrescrito)**

     ```js
     const didWrap = guides.editor.runCommand('surroundWithElement', 'sup');
     if (!didWrap) {
       tcx.util.showAlert("warning", "superscript is not allowed here");
     }
     ```

   - **Exemplo: Decodificar nó atual (desativar sobrescrito)**

     ```js
     const didUnwrap = guides.editor.runCommand('unwrapNode');
     ```

   - **Exemplo: Inserir XML no cursor com o sinal de interpolação colocado dentro de**

     ```js
     guides.editor.runCommand(
       'insertXml',
       '<sup></sup>',
       undefined,
       { setCursorInContent: true, focusEditor: true, selectInsertedXml: false }
     );
     ```

- `guides.editor.canRunCommand(commandName, ...args)`: Verifica se um comando nomeado pode ser executado no momento, sem executá-lo de fato.

  **Assinatura:**

  ```ts
  guides.editor.canRunCommand(commandName: string, ...args: any[]): boolean
  ```

  **Exemplo:**

  ```js
  if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
    guides.editor.runCommand('surroundWithElement', 'sup');
  }
  ```

## Funções utilitárias

- `guides.editor.runUtil(utilName, ...args)`: invoca um utilitário nomeado do Registro do utilitário do Novo Editor. Retorna o resultado do utilitário, ou `undefined` se ele não for encontrado.

  **Assinatura:**

  ```ts
  guides.editor.runUtil(utilName: string, ...args: any[]): any
  ```

  **Utilitários disponíveis**

  >[!NOTE]
  >
  > Estabilidade: os utilitários listados abaixo fazem parte da interface pública. Seus nomes, assinaturas e comportamento observável são considerados estáveis e mantidos para compatibilidade. Comandos adicionais podem estar presentes no editor; no entanto, eles são internos, não se destinam a uso externo e podem ser alterados ou removidos sem aviso prévio.


  | Categoria | Utilitário | Argumentos | Devoluções | Descrição |
  |---|---|---|---|---|
  | Posição | `getTextPos` | _(nenhum)_ | `{ start: number, end: number }` | Posições inicial e final da seleção atual no documento ProseMirror |
  | Posição | `getNodePosition` | `position?: number` | `number` | Posição do documento do nó atualmente selecionado/focalizado |
  | Posição | `mapToXpath` | `position: number` | `XPathPosition` | Mapeia uma posição do ProseMirror para um descritor XPath |
  | Posição | `inverseMap` | `xpath: XPathPosition \| number` | `number` | Mapeia um descritor XPath (ou posição numérica) de volta para uma posição ProseMirror |
  | Documento | `getNodeTree` | _(nenhum)_ | `NodeTree \| null` | Representação em árvore do documento, adequada para renderização de estrutura de tópicos |
  | Documento | `getAncestorsNames` | `position?: number` | `string[]` | Nomes de marcas XML de nós ancestrais em `position` |
  | Documento | `getAncestorsDetails` | `position?: number` | `{ currNode: string, ancestors: Array<{tagName: string}>, previousSibling?: string, nextSibling?: string } \| undefined` | Nó atual, ancestrais e irmãos imediatos em `position` |
  | Documento | `getAncestorXpaths` | `includeId?: boolean` | `AncestorXpathItem[]` | Sequências de caracteres XPath para todos os nós ancestrais |
  | Documento | `getPreviousSibling` | `position?: number` | `string \| undefined` | Nome da tag do irmão anterior, se houver |
  | Documento | `getNextSibling` | `position?: number` | `string \| undefined` | Nome da tag do irmão seguinte, se houver |
  | Documento | `getTagName` | `position?: number` | `string \| null` | Nome da marca do elemento em `position` (ou cursor) |
  | Pesquisa de elementos | `findPositionRange` | `tagName: string` | `{ from: number, to: number } \| undefined` | Intervalo do primeiro elemento com a tag fornecida |
  | Pesquisa de elementos | `findPositionRanges` | `tagName: string` | `Array<{ from: number, to: number }>` | Todos os intervalos de elementos correspondentes a `tagName` |
  | Atributos | `getAttributeAtPosition` | `position: number, attrName: string` | `unknown` | Lê um valor de atributo XML do nó em `position` |
  | Atributos | `getSerializableAttributes` | `xpath: string` | `Record<string, unknown>` | Todos os atributos XML serializáveis para o nó em `xpath` |
  | Serialização | `serialize` | _(nenhum)_ | `string` | Serializa o documento inteiro para XML |
  | Serialização | `serializeToText` | _(nenhum)_ | `string` | Serializa o documento inteiro para texto sem formatação |
  | Serialização | `getRangeXml` | `xpaths: AncestorXpathItem[]` | `string` | Retorna o XML para um intervalo definido por XPath |
  | Seleção | `getSelectedXml` | _(nenhum)_ | `string` | Conteúdo atualmente selecionado como uma sequência de caracteres XML |
  | Seleção | `getSelectedText` | _(nenhum)_ | `string` | Texto selecionado sem qualquer marcação |
  | Seleção | `hasSelection` | _(nenhum)_ | `boolean` | `true` se houver uma seleção de texto/nó ativa |
  | Seleção | `isSelectionEditable` | _(nenhum)_ | `boolean` | Se a seleção atual está dentro do conteúdo editável |
  | Seleção | `isPositionEditable` | `position: number` | `boolean` | Se `position` está dentro do conteúdo editável |
  | Inserção | `canInsert` | `name: string, position?: number, insertMode?: 'after' \| 'before' \| 'rename'` | `boolean` | Se `name` pode ser inserido em `position` (ou cursor) |
  | Inserção | `getInsertPosition` | `name: string, position?: number, insertMode?: 'after' \| 'before' \| 'rename'` | `number \| null` | Posição de inserção válida para `name`, ou `null` se não for inserível |
  | Inserção | `getNodeXml` | `nodeName: string, nodeContent?: string` | `string \| null` | Modelo XML para um tipo de nó |
  | Quebrar/renomear | `getValidWrapNodeElementNames` | _(nenhum)_ | `string[]` | Nomes de elementos que podem envolver a seleção atual |
  | Quebrar/renomear | `getValidRenameNodeElementNames` | _(nenhum)_ | `string[]` | Nomes de elementos para os quais o nó atual pode ser renomeado |
  | Tabelas | `getTableInfo` | `position?: number` | `{ rows: number, cols: number, header: number }` | Dimensões da tabela atual |
  | Exibição de tag | `isTagViewActive` | _(nenhum)_ | `boolean` | Se a renderização da visualização de tag está ativa |

  **Exemplo: obter a posição do cursor e os nomes de antecessores**

  ```js
  const textPos = guides.editor.runUtil("getTextPos");
  const ancestorNames = guides.editor.runUtil(
    "getAncestorsNames",
    typeof textPos === "number" ? textPos : undefined
  );
  ```

  **Exemplo: encontrar todos os elementos `<xref>` e ler seus atributos**

  ```js
  const xrefRanges = guides.editor.runUtil("findPositionRanges", "xref") || [];
  xrefRanges.forEach((range) => {
    const id = guides.editor.runUtil("getAttributeAtPosition", range.from, "id");
    const placeholderText = guides.editor.runUtil(
      "getAttributeAtPosition",
      range.from,
      "placeholdertext"
    );
  });
  ```

  **Exemplo: encontre o intervalo do elemento raiz e leia seus atributos**

  ```js
  const rootRange = guides.editor.runUtil("findPositionRange", "concept"); // or "topic"
  if (rootRange) {
    const createdDate = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "createdDate"
    );
    const author = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "author"
    );
  }
  ```

  **Exemplo: verifique a seleção e valide o contexto ancestral antes de uma operação**

  ```js
  const ancestorsDetails = guides.editor.runUtil('getAncestorsDetails');
  const selectedText = guides.editor.runUtil('getSelectedPlainText');
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  
  const firstAncestor = ancestorsDetails?.currNode || ancestorsDetails?.ancestors?.[0]?.tagName;
  if (firstAncestor === 'ph') {
    tcx.util.showAlert("warning", "Operation is not allowed inside this element type.");
    return;
  }
  ```

  **Exemplo: obter IDs de elementos de XPaths ancestrais**

  ```js
  const ancestorItems = guides.editor.runUtil('getAncestorXpaths', true);
  for (const item of ancestorItems) {
    const attrs = guides.editor.runUtil('getSerializableAttributes', item.xpath);
    if (attrs?.id) { /* use element ID */ }
  }
  ```

## API de decoração

A API de decoração fornece uma alternativa de nível superior para gravar plug-ins completos do ProseMirror para personalizações visuais comuns. Em vez de gerenciar `Plugin`, `PluginKey` e `DecorationSet` manualmente, você descreve *o que* decorar e *como*, e o gerenciador de decoração central do editor lida com o estado do ProseMirror internamente.

As decorações são identificadas por uma cadeia de caracteres `id` para que possam ser atualizadas ou removidas independentemente a qualquer momento.

>[!NOTE]
>
> **Somente novo editor** Essas APIs não são operações no editor herdado (`version === '1.0.0'`).

- `guides.editor.addDecoration(id, selector, options)`: adiciona ou substitui uma regra de decoração. Todos os nós correspondentes a `selector` no documento atual serão decorados de acordo com `options`. A decoração é reaplicada automaticamente em cada alteração de documento.

  **Assinatura:**

  ```ts
  guides.editor.addDecoration(
    id: string,
    selector: string,
    options: DecorationOptions
  ): boolean
  ```

  **`DecorationOptions`campos:**

  | Texto | Tipo | Descrição |
  |---|---|---|
  | `class` | `string` | Nomes de classe CSS adicionados aos nós correspondentes |
  | `computeAttributes` | `(node, context) => Record<string, string>` | Função que retorna `data-*` dinâmico ou outros atributos HTML por nó |
  | `filter` | `(node) => boolean` | Predicado opcional — somente nós onde isso retorna `true` são decorados |

  O objeto `context` passado para `computeAttributes` inclui:
   - `index` — Posição do nó baseada em 0 entre irmãos que correspondem ao seletor

  **Exemplo: adicionar uma classe CSS a todos os `<section>` elementos**

  ```js
  guides.editor.addDecoration('highlight-sections', 'section', {
    class: 'my-section-highlight'
  });
  ```

  **Exemplo: adicionar um atributo `data-number-label` calculado a cada seção**

  ```js
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

  **Exemplo: decorar somente seções que tenham `importance="high"` atributo**

  ```js
  guides.editor.addDecoration('important-sections', 'section', {
    class: 'section-important',
    filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
  });
  ```

  **Exemplo: combinar classe e atributos computados**

  ```js
  guides.editor.addDecoration('numbering-mode', 'conbody', {
    class: 'legacy-numbering'
  });
  
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

- `guides.editor.removeDecoration(id)`: remove uma decoração adicionada anteriormente por sua ID.

  **Assinatura:**

  ```ts
  guides.editor.removeDecoration(id: string): boolean
  ```

  **Exemplo:**

  ```js
  guides.editor.removeDecoration('section-numbers');
  ```

- `guides.editor.batchDecorations(changes)`: Aplica várias alterações de decoração de adição/remoção em uma única expedição de ProseMirror. Use isso ao alternar várias decorações de uma só vez para evitar várias renderizações.

  **Assinatura:**

  ```ts
  guides.editor.batchDecorations(changes: DecorationBatchChange[]): boolean
  
  type DecorationBatchChange =
    | { action: 'add', id: string, selector: string, options: DecorationOptions }
    | { action: 'remove', id: string }
  ```

  **Exemplo: alternar entre dois modos de numeração atomicamente**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'legacy-numbering' },
    {
      action: 'add',
      id: 'division-numbering',
      selector: 'conbody',
      options: { class: 'division-numbering' }
    }
  ]);
  ```

  **Exemplo: limpar uma decoração e adicionar duas novas**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'old-highlights' },
    {
      action: 'add',
      id: 'section-labels',
      selector: 'section',
      options: {
        computeAttributes: (node, ctx) => ({ 'data-section-index': String(ctx.index) })
      }
    },
    {
      action: 'add',
      id: 'note-style',
      selector: 'note',
      options: { class: 'styled-note' }
    }
  ]);
  ```

- `guides.editor.clearDecorations()`: remove todas as decorações ativas gerenciadas pelo gerenciador de decorações.

  **Assinatura:**

  ```ts
  guides.editor.clearDecorations(): boolean
  ```

  **Exemplo:**

  ```js
  guides.editor.clearDecorations();
  ```

- `guides.editor.getDecorations()`: retorna as IDs de todas as decorações ativas no momento.

  **Assinatura:**

  ```ts
  guides.editor.getDecorations(): string[]
  ```

  **Exemplo:**

  ```js
  const active = guides.editor.getDecorations();
  console.log('Active decorations:', active);
  // e.g. ['section-numbers', 'numbering-mode', 'note-style']
  ```


### API de decoração vs `registerPlugin`

| Cenário | Usar |
|---|---|
| Aplicar uma classe CSS ou `data-*` atributos aos elementos correspondentes | `addDecoration` |
| Alternar ou atualizar o estilo com base no estado do tempo de execução (metadados, ação do usuário) | `addDecoration` / `removeDecoration` / `batchDecorations` |
| Lógica complexa do plug-in: estado personalizado, atalhos de teclado, decorações do widget, manipuladores de eventos | `registerPlugin` |
| Inserção de CSS no DOM de sombra | `registerPlugin` com o campo `css` |


## Registro do plug-in ProseMirror

- `guides.editor.registerPlugin(factory)`: registra uma fábrica de plug-ins do ProseMirror a ser incluída em cada instância do novo editor. Somente funções de fábrica são aceitas, instâncias diretas de plug-in são rejeitadas. A fábrica é chamada uma vez por instância do editor, garantindo o estado isolado do plug-in.

  **Assinatura:**

  ```ts
  guides.editor.registerPlugin(factory: () => PluginConfig): void
  
  interface PluginConfig {
    plugin: ProseMirrorPlugin | ProseMirrorPlugin[]
    css?: string  // Injected into editor's shadow DOM
  }
  ```

  **Exemplo: registrar plug-ins depois que o editor estiver pronto**

  ```js
  guides.ready(() => {
    guides.editor.registerPlugin(createNumberingPlugin);
    guides.editor.registerPlugin(createXrefPlugin);
  });
  ```

  **Exemplo: fábrica integrada com CSS**

  ```js
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({
      key: new guides.editor.prosemirror.state.PluginKey("myPlugin"),
      props: {
        decorations(state) {
          // return DecorationSet...
        }
      }
    }),
    css: `.my-decoration { background: yellow; }`
  }));
  ```

  >[!NOTE]
  >
  > O CSS transmitido por `css` é inserido no DOM de sombra do editor. As folhas de estilos regulares no nível da página não se aplicam dentro do editor.

## Bibliotecas do ProseMirror

- `guides.editor.prosemirror`: expõe pacotes ProseMirror diretamente para uso no desenvolvimento de plug-in. Isso evita a necessidade de agrupar o ProseMirror separadamente no código de extensão.

  | Propriedade | Pacote |
  |---|---|
  | `state` | `prosemirror-state` |
  | `model` | `prosemirror-model` |
  | `view` | `prosemirror-view` |
  | `transform` | `prosemirror-transform` |
  | `commands` | `prosemirror-commands` |
  | `keymap` | `prosemirror-keymap` |
  | `history` | `prosemirror-history` |
  | `tables` | `prosemirror-tables` |
  | `dropcursor` | `prosemirror-dropcursor` |
  | `markdown` | `prosemirror-markdown` |

  **Exemplo: Criar um plug-in de decoração de nó**

  ```js
  const myPluginKey = new guides.editor.prosemirror.state.PluginKey("myPlugin");
  
  const createMyPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  
    return {
      plugin: new Plugin({
        key: myPluginKey,
        state: {
          init() { return { enabled: true }; },
          apply(tr, value) {
            const meta = tr.getMeta(myPluginKey);
            return meta ? { ...value, ...meta } : value;
          }
        },
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name === "section") {
                decorations.push(
                  Decoration.node(pos, pos + node.nodeSize, { class: "my-section" })
                );
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.my-section { border-left: 3px solid #ccc; padding-left: 8px; }`
    };
  };
  ```

  **Exemplo: criar um plug-in de decoração de widget (texto de exibição embutido)**

  ```js
  const xrefPluginKey = new guides.editor.prosemirror.state.PluginKey("xrefDisplay");
  
  const createXrefPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  
    return {
      plugin: new Plugin({
        key: xrefPluginKey,
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name.includes("xref")) {
                const display = node.attrs?.xmlAttrs?.placeholdertext;
                if (display) {
                  decorations.push(
                    Decoration.widget(pos + 1, () => {
                      const el = document.createElement("span");
                      el.textContent = `[${display}]`;
                      el.setAttribute("contenteditable", "false");
                      return el;
                    }, { key: `xref-${pos}` })
                  );
                }
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.xref-display-text { color: #0074d9; pointer-events: none; }`
    };
  };
  ```

## Inserção de CSS no editor

O editor DITA do Guides carrega seus estilos de conteúdo no modo de autor de uma clientlib com a categoria `apps.guides.dita_editor.content`. Essa clientlib tem uma declaração `embed` que obtém automaticamente qualquer clientlib registrado na categoria:

```
apps.guides.xml_editor.dita_content_overrides
```

Para inserir CSS personalizado na área de conteúdo do editor, crie um nó clientlib do AEM com esta categoria. Nenhuma fiação adicional é necessária, o Guides a seleciona automaticamente quando a página do editor é carregada.

**Estrutura do nó clientlib do AEM (`/apps/my-extension/clientlibs/editor-content-overrides/.content.xml`)**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:cq="http://www.day.com/jcr/cq/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
    jcr:primaryType="cq:ClientLibraryFolder"
    categories="[apps.guides.xml_editor.dita_content_overrides]"/>
```

Coloque o arquivo CSS (`css.txt` + o arquivo `.css`) dentro dessa pasta. Ele será incorporado automaticamente à folha de estilos de conteúdo do editor.

**Exemplo: substituir estilos de cabeçalho de seção no modo de autor**

```css
/* /apps/my-extension/clientlibs/editor-content-overrides/css/content.css */

/* Increase section title font size in author mode */
.section > title {
  font-size: 1.4em;
  font-weight: bold;
  color: #333;
}

/* Highlight note blocks */
.note {
  border-left: 4px solid #0074d9;
  padding-left: 12px;
  background: #f0f7ff;
}
```

>[!NOTE]
>
>Este CSS segmenta somente a superfície do autor herdada baseada no CKEditor. Ela não tem efeito no novo editor (ProseMirror), que usa um DOM de sombra.


### Novo Editor: `css` em `registerPlugin`

O Novo Editor é renderizado em um **DOM de sombra**, que o isola de todos os estilos de nível de página, incluindo o AEM `clientlibs`. Para inserir CSS na superfície do novo autor do editor, passe uma cadeia de caracteres `css` como parte da `PluginConfig` retornada pela fábrica de plug-ins.

O CSS é inserido como uma tag `<style>` diretamente na raiz de sombra do editor sempre que uma instância do editor é criada.

**Exemplo: inserir estilos ao lado de um plug-in de decoração**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: createMyPlugin(), // your ProseMirror plugin
    css: `
      /* Styles scoped to the New Editor shadow DOM */
      .section > .title-node {
        font-size: 1.4em;
        font-weight: bold;
        color: #333;
      }

      .note-node {
        border-left: 4px solid #0074d9;
        padding-left: 12px;
        background: #f0f7ff;
      }
    `
  }));
});
```

**Exemplo: plug-in somente CSS (sem lógica de decoração)**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no-op plugin
    css: `
      /* Custom author-mode typography */
      [data-xml-element="codeblock"] {
        font-family: monospace;
        background: #f5f5f5;
        padding: 8px;
        border-radius: 4px;
      }
    `
  }));
});
```

>[!NOTE]
>
> Esse CSS só se aplica dentro do DOM de sombra do Novo editor. Isso não afeta o restante da página nem o editor herdado.


## Extensões do Menu de Contexto (`contextMenuWidget`)

As extensões podem adicionar itens ao menu de contexto de clique com o botão direito do mouse/navegação estrutural do editor declarando um campo `contextMenuWidget` em sua configuração de extensão. Isso informa à estrutura o menu do editor a ser direcionado.

### IDs de widget

| ID do widget | Editor |
|---|---|
| `dita_editor_menu` | Superfície do autor herdada do CKEditor (navegação estrutural + menu de contexto do elemento) |
| `markup_editor_menu` | Navegação estrutural do novo editor (ProseMirror) e menu de contexto do elemento |

Ambos os widgets são montados na página simultaneamente. A estrutura corresponde cada extensão ao menu correto com base nesse campo.

> As extensões também podem direcionar ambos os editores passando uma matriz: `contextMenuWidget: ["dita_editor_menu", "markup_editor_menu"]`

### Editor herdado: `dita_editor_menu`

Use isso para extensões que devem aparecer no menu de contexto do CKEditor herdado.

```js
const myContextMenuExtension = {
  id: "dita_author_view_menu",
  contextMenuWidget: "dita_editor_menu",
  view: {
    items: [
      {
        displayName: "My Custom Action",
        data: { eventid: "myCustomAction" },
        icon: "textSpaceAfter",
        target: {
          key: "displayName",
          value: "Wrap Element",   // insert after this existing menu item
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    myCustomAction() {
      console.log("Custom action triggered");
    },
  },
};
```

### Novo Editor: `markup_editor_menu`

Use isso para extensões que devem aparecer no menu de contexto Novo editor (navegação estrutural e clique com o botão direito do mouse nos elementos). O controlador recebe eventos via `handleExtensionEvent`, que roteia manipuladores locais para o controlador `markup_editor_menu` e despacha eventos globais por meio do manipulador de eventos do aplicativo.

```js
const myMarkupContextMenu = {
  id: "dita_author_view_menu",
  contextMenuWidget: "markup_editor_menu",
  view: {
    items: [
      {
        displayName: "Edit Cross Reference",
        data: { eventid: "editCrossReference" },
        icon: "link",
        target: {
          key: "displayName",
          value: "Cut",
          viewState: "prepend",
        },
      },
      {
        displayName: "Remove Cross Reference",
        data: { eventid: "removeCrossReference" },
        icon: "deleteOutline",
        target: {
          key: "displayName",
          value: "Edit Cross Reference",
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    editCrossReference() {
      // Use guides.editor APIs to read context
      const ancestorXpaths = guides.editor.runUtil("getAncestorXpaths", true);
      // open dialog or take action...
    },
    removeCrossReference() {
      guides.editor.runCommand("unwrapNode");
    },
  },
};
```

## Bibliotecas de utilitário

- `guides.util.lodash`:The biblioteca do utilitário lodash, mesma instância agrupada com o editor.

  ```js
  const uniqueIds = guides.util.lodash.uniq(ids);
  ```

- `guides.util.async`: biblioteca de utilitários assíncronos para uso de extensão.

  ```js
  guides.util.async.parallel([task1, task2], callback);
  ```

## Referência completa da API

| API | Descrição |
|---|---|
| `filePath` | Obter o caminho de arquivo do documento ativo |
| `version` | Obter a cadeia de caracteres de versão do editor carregado |
| `appState(key)` | Ler um valor do modelo de aplicativo |
| `focus()` | Focaliza o editor ativo |
| `canInsertXmlElement(tag, insertAfter?)` | Verificar se um elemento pode ser inserido no cursor |
| `selectCurrentBlockElement()` | Selecionar o elemento de bloco atual |
| `getValidElementNamesForInsertion(args)` | Listar nomes de elementos válidos para inserção |
| `updateAttributeByXpath(args)` | Atualizar um atributo por XPath |
| `runCommand(name, ...args)` | Executar um comando do editor nomeado |
| `canRunCommand(name, ...args)` | Verificar se um comando pode ser executado |
| `runUtil(name, ...args)` | Invocar um utilitário editor nomeado |
| `addDecoration(id, selector, options)` | Adicionar ou substituir uma regra de decoração nomeada em elementos correspondentes |
| `removeDecoration(id)` | Remover uma regra de decoração por ID |
| `batchDecorations(changes)` | Aplicar várias alterações de decoração de adição/remoção em um despacho |
| `clearDecorations()` | Remover todas as regras de decoração ativas |
| `getDecorations()` | Obter IDs de todas as decorações ativas no momento |
| `registerPlugin(factory)` | Registrar uma fábrica de plug-ins ProseMirror (também o mecanismo de injeção de CSS DOM de sombra) |
| `prosemirror.state` | Pacote `prosemirror-state` |
| `prosemirror.model` | Pacote `prosemirror-model` |
| `prosemirror.view` | Pacote `prosemirror-view` |
| `prosemirror.transform` | Pacote `prosemirror-transform` |
| `prosemirror.commands` | Pacote `prosemirror-commands` |
| `prosemirror.keymap` | Pacote `prosemirror-keymap` |
| `prosemirror.history` | Pacote `prosemirror-history` |
| `prosemirror.tables` | Pacote `prosemirror-tables` |
| `prosemirror.dropcursor` | Pacote `prosemirror-dropcursor` |
| `prosemirror.collab` | Pacote `prosemirror-collab` |
| `prosemirror.markdown` | Pacote `prosemirror-markdown` |
