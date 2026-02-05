---
title: Mapeamento de componentes do AEM Sites
description: Saiba como fazer o mapeamento de componentes para o AEM Sites
feature: Installation
role: Admin
level: Experienced
source-git-commit: c7157e04f758d08b6402a969a35d0c231a1ca476
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 0%

---

# Mapeamento de componente para o AEM Sites (usando o mapeamento de componente composto)

O artigo fala sobre os vários aspectos do mapeamento de componentes para sites do AEM (usando o mapeamento de componentes compostos).

## Regras de mapeamento de componentes

Use uma matriz JSON de regras (seu `componentmapping.json`) para converter o HTML em componentes. Mantenha as regras o mais simples, explícitas e específicas possível.

### Direcionar o elemento HTML e sua classe

- Escreva o nome da marca HTML em `name`.
- Inclua a classe CSS aplicada nesse elemento em `class`, se a classe existir.
Exemplo:

  ```html
  <div class ="sample-class">
  <p> Sample html element </p>
  </div>
  ```

  ```json
  {
  "name": "div",
  "class": "sample-class",
  "resourceType": "guides-components/components/table",
  "attributeMap": []
  }
  ```

Ao definir os elementos acima, verifique o seguinte:

- `name` pode ser uma lista separada por vírgulas (por exemplo, `"h1, h2"`).
- `class` deve estar presente no elemento (todas as classes listadas devem corresponder).
- `resourceType` indica que você pretende usar o componente `table`. O pacote `guides-components` é um OOTB fornecido pelos Guias. Você também pode usar outros pacotes de componentes, como `core/wcm/`, conforme necessário.

### Use attributeMap para salvar propriedades no nó JCR

Adicione entradas a `attributeMap` para definir propriedades no nó de saída. Cada entrada produz `attrs[to] = value`.
Padrões comuns:

```json
// copy an attribute
{ "attribute": "src", "to": "image-src" }
// read content or tag name
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "text" }
{ "from": "name",       "to": "type" }  // the tag name, e.g., "h2"
// constant value
{ "value": true, "to": "textIsRich" }
```

Veja abaixo um exemplo de HTML para JSON para um elemento de imagem.

```html
<img src="/content/dam/aemg-docs/tragopan.svg" class="cmp-image__image" itemprop="contentUrl" data-cmp-hook-image="image" alt="">
```

```json
{
    "name": "img",
    "resourceType": "core/wcm/components/image/v2/image",
    "attributeMap": [
      {
        "from": "src",
        "to": "fileReference"
      },
      {
        "value": ["fileReference"],
        "to": "path-attributes"
      }
    ]
  }
```

### Normalizar caminhos por meio de uma entrada dedicada

Se você quiser normalizar (tornar absoluto) valores, declare quais chaves de atributo devem ser normalizadas usando:

```json
{
  "value": ["text"],
  "to": "path-attributes"
}
```

Cuidar dos seguintes pontos importantes:

- Coloque a lista de nomes de propriedades que você deseja normalizar em `value` (por exemplo, `["text"]` ou `["href", "src"]`).
- O sistema normalizará quaisquer valores encontrados nesses nomes de propriedade ao criar o componente final.


### Extrair valores do HTML antes de dividir em componentes

Use `from` para especificar como ler um valor do elemento antes que o documento seja dividido em componentes separados:

- `"textContent"`: texto sem formatação do elemento
- `"outerHTML"`: o elemento e sua marcação interna
- `"innerHTML"`: somente marcação interna do elemento
- Qualquer outra cadeia de caracteres: tratada como um nome de atributo (por exemplo, `"src"`, `"href"`)


Exemplos:

```json
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "snippet" }
{ "from": "src",        "to": "image#src" }
```

### Exemplo completo mínimo em componentmapping.json

```json
[
  {
    "name": "h1, h2",
    "class": "topic-title",
    "resourceType": "core/wcm/components/title/v2/title",
    "attributeMap": [
      { "from": "textContent", "to": "text" },
      { "from": "name",        "to": "type" }
    ]
  },
  {
    "name": "img",
    "class": "hero",
    "resourceType": "weretail/components/content/heroimage",
    "attributeMap": [
      { "from": "src", "to": "image#src" },
      { "value": ["image#src"], "to": "path-attributes" }
    ]
  },
  {
    "name": "#element",
    "resourceType": "core/wcm/components/text/v2/text",
    "attributeMap": [
      { "from": "outerHTML", "to": "text" },
      { "value": true,        "to": "textIsRich" }
    ]
  }
]
```

Defina o elemento e a classe como destino, use `attributeMap` para definir as propriedades do nó, adicione uma entrada `path-attributes` para normalizar caminhos e escolha a `from` correta para os valores que deseja extrair. O `heroimage` usado acima é um componente em um site `we-retail`.

**Observação**: é importante discutir o rich text padrão e identificar os elementos para os quais ele é utilizado.

## Criar um componente personalizado

Saiba como criar um componente de tabela personalizado que exibe imagens em suas células. Essa abordagem garante um design limpo e reutilizável para conteúdo dinâmico. Ele aborda o que você vai criar, por que ele é eficaz, os principais pré-requisitos, design de alto nível e muito mais.

### O que você vai criar

Um componente de tabela personalizado que aceita o conteúdo de tabela do HTML e substitui cada `<img>` dentro dele pela saída do componente de imagem principal do AEM. Isso permite reutilizar os recursos da Imagem principal (imagens responsivas, tratamento alternativo, acessibilidade), mantendo o controle total sobre a marcação da tabela.
Usando essa abordagem, você pode criar outros componentes personalizados para seu site do AEM (usando o mapeamento de componentes compostos).

### Por que essa abordagem

- **Reutilizar**: aproveite o comportamento maduro da imagem principal em vez de reimplementá-la.
- **Consistência**: as imagens na tabela se comportam da mesma forma que as imagens em qualquer outro lugar do site.
- **Lado do servidor**: imagens são renderizadas no servidor para desempenho, SEO e acessibilidade.

### Pré-requisitos

- O AEM SDK está em execução e esse projeto está com check-out.
- Componentes principais instalados na sua instância do AEM.
- Maven disponível para build e implantação.

### Design de alto nível

- O autor fornece o HTML para a tabela na caixa de diálogo do componente.
- Um Modelo Sling analisa a HTML, encontra `<img>` tags e, para cada imagem, chama um serviço que renderiza o componente de Imagem principal no lado do servidor.
- O modelo troca o `<img>` original pela HTML de imagem principal capturada e passa o HTML concluído para o HTL para saída.

A tabela é gerada uma vez, já contendo a marcação da Imagem principal. Nenhuma manipulação de DOM do lado do cliente é necessária.

### Estrutura de pastas e arquivos de chave (neste repositório)

- HTL do componente e clientlibs: `ui.apps/src/main/content/jcr_root/apps/guides-components/components/table/`
   - `table.html` (renderizador HTL)
   - `_cq_editConfig.xml` (atualizar ouvintes)
   - `clientlibs/` com `css.txt`, `js.txt`, `css/table.css`, `js/table.js`
- Modelo do Sling: `core/src/main/java/com/adobe/guides/aem/components/core/models/TableModel.java`
- Serviço de renderização de imagem: `core/src/main/java/com/adobe/guides/aem/components/core/services/ImageComponentRenderer.java`

### Etapas de implementação

**Definir o componente Tabela (nó do componente)**

Criar o componente em `apps/guides-components/components/table`. Se você ainda não tiver um, adicione um mínimo de `.content.xml` como abaixo para registrá-lo no painel lateral.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
          jcr:primaryType="cq:Component"
          jcr:title="Table"
          componentGroup="Guides - Custom"/>
```

Indica ao AEM que este é um componente disponível para os autores adicionarem às páginas.

**Renderizar com HTL e incluir estilos**

Use um modelo Sling e gere a saída do HTML processado. Inclua a categoria clientlib para CSS/JS.

```html
<sly data-sly-use.model="com.adobe.guides.aem.components.core.models.TableModel"
     data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html">
</sly>
<sly data-sly-call="${clientLib.css @ categories='guides-components.table'}"></sly>
<sly data-sly-test="${wcmmode.edit && !model.hasContent}">
  <div class="cq-placeholder" data-emptytext="${component.title}"></div>
</sly>
<div data-sly-test="${model.hasContent}"
     class="gu-table-wrapper ${model.enableResponsive ? 'gu-table--responsive' : ''} gu-table--style-${model.tableStyle}"
     id="${model.componentId}">
  ${model.processedTableHtml @ context='unsafe'}
</div>
```

O modelo retorna o HTML completo com a imagem principal já renderizada, portanto, o HTL apenas a imprime.

**Adicionar o Modelo do Sling para processar o HTML e renderizar a Imagem principal**

O modelo lê campos de diálogo, analisa a tabela HTML, encontra cada `<img>` e o substitui pela Imagem principal HTML por um serviço.

A seguir estão alguns dos conhecimentos importantes sobre `TableModel`:

- Lê `tableHtml`, `enableResponsive`, `tableStyle` das propriedades do recurso.
- Usa o JSoup para analisar e editar o HTML com segurança.
- Chama `ImageComponentRenderer` para renderizar a Imagem principal e capturar a HTML.
- Preserva as classes e o estilo CSS do `<img>` original.
- Normaliza caminhos DAM (remove `/jcr:content/renditions/*`).

```java
@Model(adaptables = {Resource.class, SlingHttpServletRequest.class},
       defaultInjectionStrategy = DefaultInjectionStrategy.OPTIONAL)
public class TableModel {
  @ValueMapValue private String tableHtml;
  @ValueMapValue private boolean enableResponsive;
  @ValueMapValue private String tableStyle;
  @OSGiService private ImageComponentRenderer imageRenderer;
  // ...
  @PostConstruct
  protected void init() {
    // parse HTML, for each <img> build image props (fileReference, alt, title)
    // call imageRenderer.renderImageComponent(...)
    // replace <img> with returned Core Image HTML
  }
  public String getProcessedTableHtml() { /* return final HTML */ }
}
```

Isso centraliza a lógica no servidor e reutiliza o comportamento da Imagem principal.

**Renderizar Imagem Principal por meio de um serviço (inclusão no lado do servidor)**

`ImageComponentRenderer` renderiza o componente de Imagem principal e captura a saída. É

- envolve um recurso que força `core/wcm/components/image/v2/image`.
- usa `RequestDispatcher#include` para renderizá-lo.
- captura a resposta como uma cadeia de caracteres.

```java
@Component(service = ImageComponentRenderer.class)
public class ImageComponentRenderer {
  private static final String IMAGE_RESOURCE_TYPE = "core/wcm/components/image/v2/image";
  public String renderImageComponent(Resource base, Map<String,Object> props,
                                     SlingHttpServletRequest req, SlingHttpServletResponse resp) {
    // create wrapped resource with IMAGE_RESOURCE_TYPE and props
    // dispatcher.include(...) with a response wrapper to capture HTML
    // return captured HTML
  }
}
```

Isso permite que você **insira** a Imagem principal onde for necessário, não apenas como um componente secundário.

**Bibliotecas de clientes**

Crie uma clientlib para estilos pequenos ou JS futuro. O HTL acima carrega a categoria `guides-components.table`.

```java
clientlibs/css.txt
  #base=css
  table.css
clientlibs/js.txt
  #base=js
  table.js
  
```

Isso mantém os estilos/scripts modulares e detectáveis.

**Campos de diálogo (entradas do autor)**

Adicione uma caixa de diálogo com pelo menos estas propriedades:

- **HTML de tabela**: `./tableHtml` (textarea); o HTML da tabela.
- **Habilitar responsivo**: `./enableResponsive` (caixa de seleção); alterna uma classe de wrapper responsivo.
- **Estilo de tabela**: `./tableStyle` (select); aplica uma classe modificadora de estilo.

Eles mapeiam 1:1 para as propriedades do Modelo Sling e controlam a renderização.

**Permitir o componente em modelos**

No Editor de Modelo, edite a política de Contêiner de Layout > Componentes Permitidos > habilite o componente Tabela em **Guias - Personalizado**.

Os Autores não podem adicionar componentes até que as políticas os permitam.

## Dicas de criação

- Colar HTML válido para a tabela. O modelo limpa e ajusta URLs de imagem.
- Usar caminhos de ativos DAM para imagens; as representações são normalizadas para o caminho do ativo original.
- Forneça texto alternativo na HTML quando possível; caso contrário, as imagens serão marcadas como decorativas.

## Restrições

- O serviço força a Imagem principal v2. Para alternar versões, atualize `IMAGE_RESOURCE_TYPE`.
- Para renderização sintética, o modelo substitui as `.coreimg.` URLs geradas pela Imagem principal por caminhos diretos do DAM e remove `srcset` para evitar URLs com falha.
- Todas as renderizações ocorrem uma vez no servidor; o JavaScript é opcional.

## Referência rápida (implementação)

- HTML: `ui.apps/.../components/table/table.html`
- Clientlibs: `ui.apps/.../components/table/clientlibs/`
- Modelo: `core/.../models/TableModel.java`
- Serviço: `core/.../services/ImageComponentRenderer.java`

Este padrão mostra como compor um componente personalizado com um Componente principal do lado do servidor, mantendo sua marcação ao reutilizar a lógica Principal.
