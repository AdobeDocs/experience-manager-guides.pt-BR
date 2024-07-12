---
title: Recurso nativo do PDF Publish | Trabalhar com estilos de barras de alteração personalizados
description: Saiba como aplicar estilos a barras de alteração.
exl-id: a81ec56c-ccbb-4599-a696-8edef7a73cdd
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Trabalhar com estilos de barras de alteração personalizados

Uma barra de alteração é uma linha vertical que identifica visualmente o conteúdo novo ou revisado. O AEM Guides permite exibir uma barra de alterações à esquerda do conteúdo alterado em tópicos e também nos tópicos alterados no índice da saída do PDF.

Para obter mais detalhes sobre como mostrar a barra de alterações, consulte a configuração *Criar PDF com Barra de Alterações entre Versões Publicadas* em [Saída do PDF Publish](../web-editor/native-pdf-web-editor.md).

## Conteúdo alterado nos tópicos

A barra de alterações aparece à esquerda do conteúdo nos tópicos que foram inseridos, alterados ou excluídos.

Você pode modificar os estilos a seguir para mostrar o conteúdo alterado e entre eles com as barras de alteração.


>[!NOTE]
>
>Esses estilos fazem parte do arquivo `layout.css` e você pode editá-los conforme necessário.

Por exemplo, você pode usar o atributo de cor no estilo `.inserted-block` para definir a forma como o conteúdo inserido aparece na saída de PDF publicada.


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

Da mesma forma, você pode usar o estilo `.deleted-block` para definir a forma como o conteúdo excluído aparece na saída de PDF publicado.

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

Você pode usar os estilos `.inserted-change-bar` e `.deleted-change-bar` para modificar a aparência das barras de alteração que aparecem à esquerda do conteúdo atualizado.

Por exemplo, você pode usar o atributo `-ro-change-bar-color` no estilo `.inserted-change-bar` para mostrar a barra de alterações inserida na cor verde. Você também pode usar o atributo `-ro-change-bar-color` no estilo `.deleted-change-bar` para mostrar a barra de alterações excluída na cor vermelha.

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

Você também pode adicionar uma barra de alteração à esquerda dos tópicos alterados no índice da saída do PDF. Você pode usar o atributo `-ro-change-bar-color` no estilo `.changed-topic` para adicionar uma barra de alteração na cor de sua escolha para os tópicos atualizados na lista do índice.

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
