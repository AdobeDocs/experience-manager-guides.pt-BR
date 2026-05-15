---
title: Usar rótulos
description: Descubra o uso de rótulos para diferentes versões de um arquivo no Adobe Experience Manager Guides. Saiba como adicionar ou excluir um rótulo a uma versão de um tópico.
exl-id: d116906d-b469-4a97-b0af-4fadbe15222b
feature: Authoring, Features of Web Editor, Publishing
role: User
TQID: https://experienceleague.adobe.com/sOFJReXzhdWNvsDCcM-s5c5gN-YzV7juLkbGWxbz4bw
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 0%

---

# Usar rótulos {#id164JBG0M0T1}

O Adobe Experience Manager Guides permite adicionar rótulos a diferentes versões de um arquivo. Você pode usar esses rótulos para especificar a versão que deseja incluir em uma linha de base para publicação. Para obter mais informações sobre como usar rótulos para criar uma linha de base, consulte [Trabalhar com Linha de Base](generate-output-use-baseline-for-publishing.md#).

Por exemplo, se você quiser usar a *versão 1.0* de um tópico na *versão 1.0* e na *versão 1.1* do mesmo tópico na *versão 2.0*, poderá adicionar o rótulo *versão 1.0* na *versão 1.0* e na *versão 2.0* na *versão 1.1*.

Após adicionar os rótulos, é possível criar uma linha de base e especificar qual versão do tópico deve ser incluída para publicação usando essa linha de base. Para exibir qual versão deve ser incluída ou excluída em uma linha de base, é possível usar a opção Histórico de Versões.

## Adicionar um rótulo do Editor

Execute as seguintes etapas para adicionar um rótulo ao seu tópico do Editor:

1. No painel Repositório, navegue até um tópico e abra-o no Editor.
1. Selecione **Rótulo de versão** na lista suspensa **Menu**.

   A caixa de diálogo **Gerenciamento de Rótulos de Versão** é exibida.

1. Na caixa de diálogo **Gerenciamento de Rótulos de Versão**, selecione uma versão à qual deseja adicionar um rótulo.
1. Selecione um rótulo para a versão selecionada e selecione **Adicionar rótulo**.

   ![](images/version-label-management-dialog-new.png){width="650"}

   >[!NOTE]
   >
   > Não é possível adicionar o mesmo rótulo às diferentes versões de um tópico. Entretanto, é possível adicionar vários rótulos à mesma versão de um tópico.
1. Confirme para aplicar os rótulos no prompt de confirmação.

   Os rótulos são exibidos no Histórico de Versões do tópico selecionado.

   ![](images/label-comparison-version-history.png){width="650"}

   >[!NOTE]
   >
   > Usando uma linha de base, é possível adicionar um rótulo a vários tópicos. Para obter mais informações sobre como adicionar rótulos usando a linha de base, exiba [Adicionar rótulos a uma Linha de Base](generate-output-use-baseline-for-publishing.md#id184KD0T305Z).

Para excluir um rótulo de versão de um tópico, use o ícone **Remover** fornecido em relação a cada rótulo adicionado na caixa de diálogo Gerenciamento de Rótulos de Versão.

![](images/remove-version-label.png)


## Trabalhar com rótulos da interface do usuário do Assets

Também é possível adicionar rótulos a um tópico e excluí-los, conforme necessário, da interface do usuário do Assets.

Execute as seguintes etapas para adicionar um rótulo a um tópico da interface do usuário do Assets:

1. Na interface do Assets, selecione um tópico e abra-o.
1. Selecione o ícone do seletor do painel esquerdo e selecione **Histórico de versões**.
1. Na lista suspensa Histórico de versões, selecione uma versão à qual deseja adicionar um rótulo.
1. Insira um rótulo para a versão selecionada e pressione Enter. Por exemplo, *2.6 Versão*.

   >[!NOTE]
   >
   > Não é possível adicionar o mesmo rótulo às diferentes versões de um tópico. Entretanto, é possível adicionar vários rótulos à mesma versão de um tópico.

   Os rótulos são exibidos no Histórico de Versões do tópico selecionado. A captura de tela a seguir exibe os rótulos *x.x Versão* e *Guia do Usuário* adicionados à versão destacada do tópico.

   ![](images/labels.png){width="300"}

>[!NOTE]
>
> Usando uma linha de base, é possível adicionar um rótulo a vários tópicos. Para obter mais informações sobre como adicionar rótulos usando a linha de base, exiba [Adicionar rótulos a uma Linha de Base](generate-output-use-baseline-for-publishing.md#id184KD0T305Z).

Para excluir um rótulo de versão de um tópico, use o botão **Excluir** fornecido em relação a cada rótulo no painel Histórico de Versão.

![](images/delete-labels.png){width="300"}


**Tópico pai:**[ Introdução ao Editor](web-editor.md)
