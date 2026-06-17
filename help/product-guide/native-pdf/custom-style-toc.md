---
title: Recurso de publicação nativo do PDF | Aplicar estilo personalizado em entradas de índice e conteúdo de tópico
description: Saiba como criar folhas de estilos de uso e criar estilos para o seu conteúdo.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/cqknNhuPThhuNTsLZzwnrUzPJguIPs4J-3rX6PVR2V8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: febac97b369bad427f0f650f2cdc69b0ca6c9f69
workflow-type: tm+mt
source-wordcount: 460
ht-degree: 0%

---

# Aplicar estilo personalizado em entradas de índice e conteúdo de tópico

Você pode aplicar estilos personalizados a entradas de índice, cabeçalhos de tópicos ou tópicos individuais usando o atributo `outputclass` em elementos de mapa com suporte, como `<topicref>` e `<topichead>`. Para aplicar formatação personalizada a um tópico inteiro, estenda a definição de estilo do atributo `outputclass` no CSS.

## Estilo de um tópico referenciado por meio de `<topicref>`

Você pode aplicar um `outputclass` em um elemento `<topicref>` para estilizar a entrada do índice, o título do tópico ou o conteúdo completo do tópico no PDF gerado.

Por exemplo, para identificar um tópico que exija revisão, adicione um atributo outputclass ao elemento `<topicref>` correspondente no mapa DITA e defina os estilos associados no CSS.

No exemplo a seguir, o tópico *Histórico de voos* recebeu um atributo `outputclass` com o valor de `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

A classe `new-topic` pode ser usada para definir estilos para:

* A entrada principal no sumário ou minisumário
* O título do tópico no conteúdo principal
* Todo o conteúdo do tópico, incluindo o título

A definição CSS a seguir altera a cor do texto da entrada do índice e o título do tópico:

```css
.new-topic {
  color:#CC5309
}
```

Essa definição controla a cor do texto no índice e o título do tópico. A seguinte saída do PDF mostra a cor diferente aplicada na entrada do índice:

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

O título do tópico também é estilizado com a mesma cor.

<img src="./assets/pdf-output-topic-title.jpg" width="500">

Se você quiser que a entrada do sumário e o título do tópico tenham estilos diferentes, poderá defini-los separadamente, conforme mostrado abaixo:

```css
...
/*for styling TOC entry */
.new-topic {
  color:#CC3509
}

/* for styling topic's title */
.new-topic.title {
  color:#092ACC
}
...
```

Para aplicar estilos a todo o conteúdo do tópico, anexe o sufixo `-content` ao nome da classe. O exemplo a seguir adiciona uma barra de alteração ao conteúdo do tópico:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color:#A609CC;
}
...
```

Usando os atributos de estilo acima, uma barra de alteração é adicionada à esquerda do tópico *Histórico do voo*, conforme mostrado abaixo:

<img src="./assets/pdf-output-topic-content.jpg" width="500">

## Aplicar estilos a `topichead` elementos

Você pode usar o atributo `outputclass` em um elemento `<topichead>` para aplicar estilos diferentes à entrada do índice e ao cabeçalho gerado para o `topichead`.

Por exemplo, se você definir o seguinte `topichead` no mapa DITA:

```xml
<topichead navtitle="Getting Started" outputclass="new-topichead">
    ...
</topichead>
```

A classe `new-topichead` é aplicada à entrada de cabeçalho de tópico no índice e ao cabeçalho gerado para o cabeçalho de tópico.

Se quiser aplicar um estilo diferente ao cabeçalho, defina uma classe separada para ele, de modo semelhante a como `<topicref>` suporta estilos separados para a entrada de índice e o título do tópico:

```css
...
/* Style for the topichead TOC entry */
.new-topichead {
  color: #CC5309;
}

/* Style for the topichead heading */
.new-topichead.title {
  color: #092ACC;
}...
```

Se quiser estilizar o conteúdo associado ao cabeçalho de tópico, anexe o sufixo `- content` ao nome da classe:

```css
.new-topichead-content {
    border-left: 2px solid #cccccc;
    padding-left: 8px;
}
```



## Remover linhas vazias do sumário

Se você não tiver definido o título para nenhum tópico, linhas vazias serão exibidas no índice para esses tópicos.

Para remover as linhas vazias do sumário e do mini sumário, adicione o seguinte estilo no `layout.css`:

```css
.toc-body a:empty,
.chaptoc-body a:empty {
    display: none;
} 
```

