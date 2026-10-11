---
title: Recomendações para otimização de desempenho do Cloud Service
description: Conheça as recomendações para a otimização do desempenho
feature: Performance Optimization
role: Admin
level: Experienced
exl-id: 6c9684d4-180f-4ccb-bfd6-6c82a8a7b720
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
    internal-label: Performance optimization
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%
---
# Recomendações para otimização de desempenho do Cloud Service {#id213BD0JG0XA}

Para otimização de desempenho, considere os seguintes pontos:

- Para otimizar a experiência de indexação e conteúdo, consulte [Otimizar Pesquisa e Indexação de Conteúdo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=pt-BR) na documentação do AEM.

- Corrija o Xerces Jar ao usar o DITA-OT personalizado para publicação. Essa é uma configuração obrigatória, dependendo do caso de uso. Essa alteração será necessária somente se você usar DITA-OT personalizado para saída de publicação.

  *Configuração necessária*: substitua o arquivo Xerces Jar do pacote DITA-OT personalizado pelo arquivo OOTB fornecido. O arquivo `xercesImpl-2.11.0.jar` OOTB padrão está disponível no arquivo `/libs/fmdita/dita\_resources/DITA-OT.zip`. Renomeie o arquivo `xercesImpl-2.11.0.jar` para corresponder ao arquivo Xerces Jar antigo que está sendo substituído. Isso pode ser feito em tempo de execução.

  Essa alteração reduz o tempo de publicação e a utilização da memória durante a publicação de mapas DITA com um grande número de tópicos.
