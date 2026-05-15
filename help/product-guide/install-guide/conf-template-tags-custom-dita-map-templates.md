---
title: Configurar modelo de mapa DITA personalizado
description: Saiba como configurar o modelo de mapa DITA personalizado
exl-id: ea8a6687-1a7b-45c7-8cbc-161f9e88a8be
feature: Template Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/16cGf5xY2tAfhc0qIBZeUhYTes-RrdRp-Kj-MoTuacE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 336
ht-degree: 1%

---

# Configurar modelo de mapa DITA personalizado {#id1774F04F05Z}

O AEM Guides vem com dois modelos de mapa prontos para uso — mapa DITA e mapa de livros. Você pode criar mapas com base nesses modelos ou definir seus próprios modelos de mapa, que podem ser usados para criar novos mapas.

Execute as seguintes etapas para adicionar seus modelos de mapa personalizados:

1. Faça logon no Adobe Experience Manager como administrador.

1. Na interface do usuário do Assets, navegue até a pasta configurada para armazenar os arquivos de modelo de mapa. Por padrão, todos os modelos de mapa são armazenados na pasta /content/dam/dita-templates/maps.

   >[!NOTE]
   >
   > Para configurar um local personalizado para armazenar tópico ou modelos de mapa, consulte [Configurar caminho da pasta de modelo DITA personalizado](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Clique em **Criar** \> **Modelo DITA**.

1. Na página Blueprint, selecione o tipo do modelo de mapa que deseja criar.

   >[!NOTE]
   >
   > Você pode usar o modelo Mapa ou Mapa como base para o novo modelo.

1. Clique em **Avançar**.

1. Na nova página Propriedades do modelo, digite um **Título** e um **Nome** para o modelo.

   >[!NOTE]
   >
   > O nome é sugerido automaticamente com base no Título do template. Se desejar especificar o nome manualmente, certifique-se de que o Nome não contenha espaços, apóstrofo ou chaves e termine com .ditamap.

1. Clique em **Criar**.

   A mensagem Mapa criado é exibida.

   Você pode optar por abrir o modelo para edição no Editor de mapa ou salvar o arquivo de modelo no local de armazenamento do modelo. Depois que o modelo é criado, você pode usar o Editor de mapa para personalizar o modelo de acordo com suas necessidades de criação. Depois que um modelo estiver em vigor, certifique-se de associá-lo a um perfil global ou de nível de pasta.


Na próxima vez que você criar um novo mapa, seu modelo será exibido na página Blueprint. Para obter mais informações sobre como criar um mapa DITA, consulte *Usando o Adobe Experience Manager Guides*.

>[!TIP]
>
> Consulte a seção *Modelos personalizados* no guia de práticas recomendadas para obter práticas recomendadas sobre o uso de modelos de mapa personalizados.

**Tópico pai:** [Configurar tópico e modelos de mapa](conf-template-tags.md)
