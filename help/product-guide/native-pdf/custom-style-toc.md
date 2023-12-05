---
title: Recurso de publicação de PDF nativo | Aplicar estilo personalizado em entradas de índice e conteúdo de tópico
description: Saiba como criar folhas de estilos de uso e criar estilos para o seu conteúdo.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Aplicar estilo personalizado em entradas de índice e conteúdo de tópico

Às vezes, você pode aplicar um estilo personalizado às entradas do índice ou a um tópico específico. Isso pode ser feito associando um `outputclass` atributo com o `<topicref>` elemento no mapa DITA. Além disso, caso você queira aplicar um formato personalizado a um tópico inteiro, isso também pode ser obtido estendendo a definição de estilo do atributo no CSS.

Vamos ver um exemplo de um novo tópico que você deseja enviar para revisão. Para facilitar a identificação do tópico atualizado, é necessário adicionar um `outputclass` atributo para o `<topicref>` no mapa DITA e defina um estilo personalizado para o mesmo no CSS.

No exemplo a seguir, a variável *Histórico de voos* o tópico recebeu um `outputclass` atributo com o valor de `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

A definição de classe do `new-topic` em um CSS pode permitir a definição do estilo para os seguintes itens:
* A entrada principal no sumário ou minisumário
* O título do tópico no conteúdo principal
* Todo o conteúdo do tópico, incluindo o título

Vamos ver como cada um desses cenários pode ser definido no CSS. Na seguinte definição CSS da variável `new-topic` classe, a cor do texto foi alterada.

```css
…
.new-topic {
  color: #CC5309
}
…
```

Essa definição controla a cor do texto no índice e o título do tópico. A saída de PDF a seguir mostra a cor diferente aplicada na entrada de índice:

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

O título do tópico também é estilizado com a mesma cor.

<img src="./assets/pdf-output-topic-title.jpg" width="500">

Se você quiser que a entrada do sumário e o título do tópico tenham estilos diferentes, poderá defini-los separadamente, conforme mostrado abaixo:

```css
...
/*for styling TOC entry */
.new-topic {
  color: #CC3509
}

/* for styling topic's title */
.new-topic.title {
  color: #092ACC
}
...
```

Por fim, também é possível aplicar estilos a todo o conteúdo do tópico. Para isso, é necessário adicionar um sufixo &quot;`-content`&quot; para o nome da classe. No exemplo a seguir, uma barra de alteração foi adicionada em todo o conteúdo do tópico:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color: #A609CC;
}
...
```

Usando os atributos de estilo acima, uma barra de alteração é adicionada à esquerda do *Histórico de voo* tópico, conforme mostrado abaixo:

<img src="./assets/pdf-output-topic-content.jpg" width="500">
