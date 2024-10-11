---
title: Configurar modelo de mapa DITA personalizado
description: Saiba como configurar um modelo de mapa DITA personalizado
exl-id: a0eeb43c-06e4-4922-a005-704e8929063f
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 83971ee35a19cf0146ddd034b1ae7a345f587663
workflow-type: tm+mt
source-wordcount: '489'
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


Na próxima vez que você criar um novo mapa, seu modelo será exibido na página Blueprint. Para obter mais informações sobre como criar um mapa DITA, consulte Uso do guia as a Cloud Service do Adobe Experience Manager Guides.

>[!TIP]
>
> Consulte a seção *Modelos personalizados* no guia de práticas recomendadas para obter práticas recomendadas sobre o uso de modelos de mapa personalizados.


## Personalizar o número de referências em um mapa DITA

Você pode configurar o limite para processamento assíncrono com base no número de referências no mapa DITA. Por padrão, mapas com mais de 5 referências serão criados por operações assíncronas, enquanto mapas com menos referências continuarão usando operações síncronas.


Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para especificar o número de referências no modelo de mapa DITA para manter o processo síncrono:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| com.adobe.fmdita.xmleditor.config.XmlEditorConfig | xmleditor.asyncmapcreation | > 0 <br> **Valor padrão**: 5 |

Ao criar um mapa DITA com referências de tópico grandes usando um modelo personalizado, a criação do mapa falhará no servidor da nuvem se o tempo total de processamento exceder 60 segundos.

Para evitar isso, configure a **criação assíncrona do mapa dita** em XmlEditorConfig que permite que as tarefas sejam executadas em paralelo e reduza os tempos de processamento para mapas DITA maiores.

**Tópico pai:** [Configurar tópico e modelos de mapa](conf-template-tags.md)
