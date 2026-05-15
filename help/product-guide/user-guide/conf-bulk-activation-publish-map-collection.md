---
title: Ativar saída
description: Ative a saída de mapas DITA no AEM Guides. Saiba como ativar o conteúdo na instância de publicação.
exl-id: 4da644b9-8c5f-4976-a212-960085b693b8
feature: Publishing, Bulk Activation
role: User
TQID: https://experienceleague.adobe.com/ujkifru-aKa2oYvrE8EKUEE3Sai8NqQ9lx9BA2ZUw9U
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 469
ht-degree: 1%

---

# Ativar saída {#id214GGF00V5U}

Depois de criar uma coleção de mapas para ativação em massa, a próxima etapa é ativar o conteúdo na instância de publicação. Para ativar o conteúdo, execute as seguintes etapas:

1. Selecione o logotipo do Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. No painel **Ferramentas**, selecione **Guias**.

1. Selecione o bloco **Painel de publicação em massa**.

   O Painel de publicação em massa é exibido com uma lista de coleções de mapas de ativação em massa. Você também pode acessar este painel no painel esquerdo da [Página inicial do Adobe Experience Manager Guides](intro-home-page.md).

1. Selecione a coleção que você deseja publicar e selecione **Abrir**.

   ![](images/bulk-activation-collection-open.png)

1. \(*Opcional*\) Aplique os filtros necessários a partir do painel esquerdo para filtrar o mapa com base em sua \(status\), predefinição de saída ou linguagem modificada.

   >[!NOTE]
   >
   >Gere a saída do mapa usando a predefinição de saída antes de ativá-la na coleção de mapas.


Veja as diferentes maneiras de ativar sua coleção com base em sua configuração.

<details>
<summary> Cloud Services </summary>

![publicação-coleção-em-massa no serviço de nuvem](images/bulk-activation-collection-quick-publish-CS.png){width="650"}

Você pode ativar a saída para as instâncias de **Visualização** ou **Publicação**.

**Visualização**

* Para ativar a saída de mapas selecionados, selecione a saída de mapa pré-gerada e selecione **Publicar em** > **Visualizar**.
* Para ativar a saída de todos os mapas DITA com suas predefinições configuradas, marque a caixa de seleção ao lado da coluna **Mapa** e selecione **Publicar em** > **Publicar**.


**Publicar**

* Para ativar a saída de mapas selecionados, selecione a saída de mapa pré-gerada e selecione **Publicar em** > **Publicar**.

* Para ativar a saída de todos os mapas DITA com suas predefinições configuradas, marque a caixa de seleção ao lado do Mapa (coluna) e selecione **Publicar em** > **Publicar**.


>[!NOTE]
> 
> A caixa de seleção de uma saída de mapa é ativada somente se você tiver gerado a saída de um mapa.

Uma mensagem de sucesso é exibida quando a saída do mapa é colocada em fila para publicação.

Depois que a saída é ativada para os arquivos de mapa selecionados, a guia histórico de auditoria é atualizada e a saída ativada mais recente é exibida na parte superior. A coluna **Publicado** é atualizada com a data e hora da publicação.

</details>

<details>    
<summary>  Software local </summary>


Siga uma das seguintes opções:

* Para ativar a saída de mapas selecionados, selecione a saída de mapa pré-gerada e selecione **Publicação Rápida**.
* Para ativar a saída de todos os mapas DITA com suas predefinições configuradas, marque a caixa de seleção ao lado do Mapa (coluna) e selecione **Publicação rápida.**
  ![publicação-coleção-em-massa](images/bulk-activation-collection-quick-publish.png){width="650"}

  >[!NOTE]
  > 
  >A caixa de seleção de uma saída de mapa é ativada somente se você tiver gerado a saída de um mapa.


Uma mensagem de sucesso é exibida quando a saída do mapa é colocada em fila para publicação.

Depois que a saída é ativada para os arquivos de mapa selecionados, a guia histórico de auditoria é atualizada e a saída ativada mais recente é exibida na parte superior. A coluna **Publicado** é atualizada com a data e hora da publicação.

**Tópico pai: **[Ativação em massa de conteúdo publicado](conf-bulk-activation.md)
