---
title: Usar rótulos
description: Descubra o uso de rótulos para diferentes versões de um arquivo no AEM Guides. Saiba como adicionar ou excluir um rótulo a uma versão de um tópico.
exl-id: d116906d-b469-4a97-b0af-4fadbe15222b
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# Usar rótulos {#id164JBG0M0T1}

O AEM Guides permite adicionar rótulos a diferentes versões de um arquivo. Você pode usar esses rótulos para especificar a versão que deseja incluir em uma linha de base para publicação. Para obter mais informações sobre como usar rótulos para criar uma linha de base, consulte [Trabalhar com Linha de Base](generate-output-use-baseline-for-publishing.md#).

Por exemplo, se você quiser usar a *versão 1.0* de um tópico na *versão 1.0* e na *versão 1.1* do mesmo tópico na *versão 2.0*, poderá adicionar o rótulo *versão 1.0* na *versão 1.0* e na *versão 2.0* na *versão 1.1*.

Após adicionar os rótulos, é possível criar uma linha de base e especificar qual versão do tópico deve ser incluída para publicação usando essa linha de base. Para ver qual versão deve ser incluída ou excluída em uma linha de base, é possível usar a opção Histórico de versões.

## Adicionar um rótulo

Execute as seguintes etapas para adicionar um rótulo ao seu tópico:

1. Na interface do Assets, selecione um tópico
1. Clique no ícone do seletor do painel à esquerda e selecione **Histórico de versões**.
1. No Histórico de versões, clique em uma versão à qual deseja adicionar um rótulo.

1. Insira um rótulo para a versão selecionada e pressione Enter. Por exemplo, *2.6 Versão*.

   >[!NOTE]
   >
   > Não é possível adicionar o mesmo rótulo às diferentes versões de um tópico. Entretanto, é possível adicionar vários rótulos à mesma versão de um tópico.

   Os rótulos são exibidos no Histórico de Versões do tópico selecionado. A captura de tela a seguir exibe os rótulos *x.x Versão* e *Guia do Usuário* adicionados à versão destacada do tópico.

   ![](images/labels.png){width="300" align="left"}

>[!NOTE]
>
> Usando uma linha de base, é possível adicionar um rótulo a vários tópicos. Para obter mais informações sobre como adicionar rótulos usando a linha de base, consulte [Adicionar rótulos a uma Linha de Base](generate-output-use-baseline-for-publishing.md#id184KD0T305Z).

## Excluir um rótulo

Execute as seguintes etapas para excluir um rótulo:

1. Na interface do usuário do Assets, selecione um tópico que tenha um rótulo adicionado a ele.
1. Clique no ícone do seletor do painel à esquerda e selecione **Histórico de versões**.

   No Histórico de Versões, você verá todas as versões de um tópico e os rótulos anexados a elas. A imagem a seguir mostra um exemplo de diferentes versões de um tópico e uma versão tem rótulos adicionados a ele.

   ![](images/labels.png){width="300" align="left"}

1. Clique no botão Excluir \(**X**\) para excluir o rótulo.

   ![](images/delete-labels.png){width="300" align="left"}


**Tópico pai:**[ Trabalhar com o Editor da Web](web-editor.md)
