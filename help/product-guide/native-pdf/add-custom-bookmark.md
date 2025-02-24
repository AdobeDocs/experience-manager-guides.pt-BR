---
title: Recurso de publicação nativo do PDF | Adicionar um marcador personalizado na saída do PDF
description: Saiba como criar folhas de estilos de uso e criar estilos para o seu conteúdo.
exl-id: 6e6dbba3-da41-4066-b7b2-735a3d92b70a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 1c96f25c3b970d04d23e8faf94a8f39095f6bd2c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Adicionar um marcador personalizado na saída do PDF

Geralmente, o índice em um mapa DITA é replicado como marcadores na saída final do PDF, incluindo o título **Conteúdo** que abre a página do índice quando selecionada. Esse índice é criado a partir dos títulos do tópico ou da seção no mapa DITA.

Às vezes, você pode adicionar um marcador personalizado em um conteúdo específico na saída do PDF para facilitar a navegação. Isso pode ser feito adicionando um atributo `outputclass` no elemento e aplicando o seguinte atributo a ele:

`bookmark-level: 3`

Aqui, o `bookmark-level` é um atributo e o número `3` é o valor que indica o nível na hierarquia de marcadores onde o marcador é adicionado. No exemplo a seguir, o tópico de primeiro nível &quot;Contatos&quot; tem uma tabela, &quot;Lista de contatos&quot;, na qual adicionamos um atributo `outputclass` com o valor de `custom-bookmark`.


<img src="./assets/custom-bookmark-attribute.png" width="500">

A seguinte definição da classe `custom-bookmark` é adicionada ao arquivo CSS:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

Na saída do PDF, a tabela *Lista de contatos* é adicionada no segundo nível da lista de marcadores do PDF, conforme mostrado abaixo:

![](assets/custom-bookmark-in-pdf-output.png) {width="300" align="left"}

>[!NOTE]
>
>Você deve escolher o nível correto de adição do marcador personalizado. Se você especificar um número menor que o marcador do tópico pai, o marcador personalizado assumirá a posição do marcador pai e todos os outros marcadores serão exibidos como filhos. Isso pode levar a uma estrutura inesperada de marcadores.

**Removendo o título Conteúdo dos marcadores de saída do PDF**

Se você não quiser incluir o título **Conteúdo** na saída do PDF, poderá removê-lo colocando o **Conteúdo** no elemento `<p>` em vez do elemento `<h1>`.

O processo passo a passo para remover o título Conteúdo dos marcadores é o seguinte:

1. Abra o modelo do PDF que você está usando para a saída do PDF.
2. Abra a **página de índice** em **Layouts de página**.
A página do índice é exibida à direita.
3. Alterne para o modo **Source** e altere o elemento onde o Conteúdo está localizado de `<h1>` para `<p>`.

Antes da alteração:

```
<h1 class="toc-title">Contents</h1>
```

Após a alteração:

```
<p class="toc-title">Contents</p>
```

Salve as alterações e gere a saída novamente.





