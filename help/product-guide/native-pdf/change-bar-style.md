---
title: Recurso de publicação de PDF nativo | Trabalhar com estilos de barras de alteração personalizados
description: Saiba como aplicar estilos a barras de alteração.
exl-id: a81ec56c-ccbb-4599-a696-8edef7a73cdd
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Trabalhar com estilos de barras de alteração personalizados

Uma barra de alteração é uma linha vertical que identifica visualmente o conteúdo novo ou revisado. Guias do AEM permitem mostrar uma barra de alteração à esquerda do conteúdo alterado em tópicos e também os tópicos alterados no índice da saída de PDF.

Para obter mais detalhes sobre como mostrar a barra de alterações, consulte *Criar PDF com barra de alterações entre versões publicadas* configuração em [Publicar saída do PDF](../web-editor/native-pdf-web-editor.md).

## Conteúdo alterado nos tópicos

A barra de alterações aparece à esquerda do conteúdo nos tópicos que foram inseridos, alterados ou excluídos.

Você pode modificar os estilos a seguir para mostrar o conteúdo alterado e entre eles com as barras de alteração.


>[!NOTE]
>
>Esses estilos fazem parte do `layout.css` e você poderá editá-los conforme necessário.

Por exemplo, você pode usar o atributo de cor na variável `.inserted-block` estilo para definir a forma como o conteúdo inserido aparece na saída de PDF publicada.


```css
...
.inserted-block { 
  color: #2ECC40; 
  display: inline; 
  -ro-comment-content: " "; 
  -ro-comment-style: underline; 
  -ro-comment-title: "Inserted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

Da mesma forma, você pode usar o `.deleted-block` estilo para definir a forma como o conteúdo excluído aparece na saída de PDF publicada.

```css
...
.deleted-block { 
  display: inline; 
  color: #FF6961; 
  text-decoration: line-through; 
  -ro-comment-content: " "; 
  -ro-comment-style: strikeout; 
  -ro-comment-title: "Deleted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

Você pode usar `.inserted-change-bar` e `.deleted-change-bar` estilo para modificar a aparência das barras de alteração que aparecem à esquerda do conteúdo atualizado.

Por exemplo, você pode usar `-ro-change-bar-color` atributo em `.inserted-change-bar` estilo para mostrar a barra de alterações inserida na cor verde. Também é possível usar `-ro-change-bar-color` atributo em `.deleted-change-bar` estilo para mostrar a barra de alterações excluída em vermelho.

```css
...
.inserted-change-bar { 
  -ro-change-bar-color: #2ECC40; 
} 

.deleted-change-bar { 
  -ro-change-bar-color: #FF6961; 
  } 
...
```

<img src="./assets/changed-bar-content.png" alt="Conteúdo do tópico de barra alterado" width="500">

## Tópico alterado no Sumário

Você também pode adicionar uma barra de alteração à esquerda dos tópicos alterados no índice da saída do PDF. Você pode usar `-ro-change-bar-color` atributo no `.changed-topic` Estilo para adicionar uma barra de alterações na cor de sua escolha para os tópicos atualizados na lista do índice.

Por exemplo, é possível adicionar uma barra de alteração de cor verde.

```css
...
.changed-topic { 
 -ro-change-bar-color: #2ECC40; 
}  
...
```


Isso mostra uma barra de alteração verde em relação a todos os tópicos do índice onde algumas atualizações foram feitas. Você pode clicar no tópico alterado no índice e exibir as alterações detalhadas.

<img src="./assets/changed-bar-TOC.png" alt="Índice da barra alterada" width="500">
