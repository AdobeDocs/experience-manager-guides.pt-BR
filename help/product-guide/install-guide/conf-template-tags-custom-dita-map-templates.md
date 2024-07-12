---
title: Configurar modelo de mapa DITA personalizado
description: Saiba como configurar o modelo de mapa DITA personalizado
exl-id: ea8a6687-1a7b-45c7-8cbc-161f9e88a8be
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '331'
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
