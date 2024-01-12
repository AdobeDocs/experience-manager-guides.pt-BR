---
title: Recurso de publicação de PDF nativo | Usar JavaScript para trabalhar com conteúdo ou estilo
description: Saiba como criar folhas de estilos de uso e criar estilos para o seu conteúdo.
exl-id: 2f301f6a-0d1c-4194-84c2-0fddaef8d3ec
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%

---

# Usar JavaScript para trabalhar com conteúdo ou estilo

O recurso Publicação de PDF nativo permite executar o JavaScript para manipular o conteúdo ou estilo aplicado no conteúdo antes que o PDF final seja gerado. Esse recurso oferece controle total sobre como a saída final é gerada. Por exemplo, você pode adicionar informações de avisos legais à saída PDF, que reside em outro PDF. Usando o JavaScript, você pode adicionar as informações de aviso legal depois que o PDF for criado para o conteúdo base, mas antes que o PDF final seja gerado.\
Para oferecer suporte à execução do JavaScript, o recurso Publicação de PDF nativo fornece as seguintes funções de retorno de chamada:

* `window.pdfLayout.onBeforeCreateTOC(callback)`: Essa função de retorno de chamada é executada antes que o índice seja gerado.
* `window.pdfLayout.onBeforePagination(callback)`: essa função de retorno de chamada é executada após a geração do índice, mas antes de as quebras de página serem adicionadas no PDF.
* `window.pdfLayout.onAfterPagination(callback)`: Essa função de retorno de chamada é executada após o índice e as quebras de página serem adicionadas no PDF.

>[!NOTE]
>
>Internamente, uma sequência de execução é mantida para essas funções de chamada. Primeiro, onBeforeCreateTOC é executado, seguido por onBeforePagination e, por fim, onAfterPagination é executado.

Com base no tipo de conteúdo ou na modificação de estilo que deseja executar, você pode escolher qual função de retorno de chamada usar. Por exemplo, se você deseja adicionar conteúdo, é recomendável fazer isso antes que o índice seja gerado. Da mesma forma, se você quiser fazer algumas atualizações de estilo, elas poderão ser feitas antes ou depois da paginação.

No exemplo a seguir, a posição dos títulos das figuras é alterada de para acima das imagens para abaixo das imagens. Para isso, é necessário ativar a opção de execução JavaScript na predefinição. Para fazer isso, execute as seguintes etapas:

1. Abra a predefinição para edição.
1. Vá para a **Avançado** guia.
1. Selecione o **Ativar JavaScript** opção.
1. Salve a predefinição e feche.

Em seguida, crie um arquivo JavaScript com o seguinte código e salve-o na pasta Resources do seu modelo:

```css
...
/*
* DITA only allows the figure title to be placed above images 
* This JavaScript code is used to move the figure title below the image
* */
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onBeforeCreateTOC(function() {
        var titleNodes = document.querySelectorAll('.fig > .title')
        for (var i = 0; i < titleNodes.length; i++) {
            var titleNode = titleNodes[i]
            var figNode = titleNode.parentNode
            var imageNode = figNode.querySelector('.image')
            if(imageNode && imageNode.parentNode !== figNode) {
              imageNode = imageNode.parentNode
            }
            if (figNode && imageNode && imageNode.parentNode === figNode) {
                figNode.insertBefore(imageNode, titleNode)
            }
        }
    })
});
...
```

>[!NOTE]
>
>A variável `window.addEventListener('DOMContentLoaded', function ()` deve ser chamada antes que as funções de retorno de chamada sejam usadas.

Em seguida, esse script deve ser chamado de um arquivo de modelo usado para gerar a saída de PDF. Para nosso exemplo, vamos adicioná-lo no modelo de índice. Certifique-se de que o `<script>` tag é adicionada em um intervalo de tempo `<div>` dentro da tag `<body>` tag. Se você adicioná-lo na variável `<head>` ou fora da `<body>` , o script não será executado.

<img src="./assets/js-added-resources-template.png" width="500">

A saída gerada usando esse código e o modelo exibem o título da figura abaixo da imagem:

<img src="./assets/fig-title-below-image.png" width="500">

## Adicionar uma marca d&#39;água à saída do PDF para documentos de rascunho {#watermark-draft-document}

Também é possível usar o JavaScript para adicionar marcas d&#39;água condicionais. Essas marcas d&#39;água são adicionadas ao documento quando a condição definida é atendida.\
Por exemplo, você pode criar um arquivo JavaScript com o código a seguir para criar uma marca d&#39;água na saída PDF do documento que ainda não foi aprovado. Essa marca d&#39;água não aparecerá se você gerar o PDF para o documento no estado de documento ‘Aprovado’.

```css
...
/*
* This file can be used to add a watermark to the PDF output
* */

window.addEventListener('DOMContentLoaded', function () {
    var watermark = 'Draft'
    var metaTag = document.getElementsByTagName('meta')
    css = "@page {\n  @left-middle {\n    content: \"".concat(watermark, "\";\n    z-index: 100;\n    font-family: sans-serif;\n    font-size: 80pt;\n    font-weight: bold;\n    color: gray(0, 0.3);\n    text-align: center;\n    transform: rotate(-54.7deg);\n    position: absolute;\n    left: 0;\n    top: 0;\n    width: 100%;\n    height: 100%;\n  }\n}")
    head = document.head || document.getElementsByTagName('head')[0], style = document.createElement('style');
    style.appendChild(document.createTextNode(css));
    window.pdfLayout.onBeforePagination(function () {
        for (let i = 0; i < metaTag.length; i++) {
            if (metaTag[i].getAttribute('name') === 'docstate' && metaTag[i].getAttribute('value') !== 'Approved') {
                head.appendChild(style);
            }
        }
    })
});
...
```

A saída de PDF gerada usando esse código exibe uma marca d&#39;água *Rascunho* na página de capa do documento:

<img src="./assets/draft-watermark.png" width="500">
