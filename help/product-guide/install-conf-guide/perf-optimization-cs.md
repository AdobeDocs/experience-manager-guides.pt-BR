---
title: Recomendações para otimização de desempenho do Cloud Service
description: Conheça as recomendações para a otimização do desempenho
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Recomendações para otimização de desempenho do Cloud Service {#id213BD0JG0XA}

Para otimização de desempenho, considere os seguintes pontos:

- Para otimizar a experiência de indexação e conteúdo, consulte [Otimizar Pesquisa e Indexação de Conteúdo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=pt-BR) na documentação do AEM.

- Corrija o Xerces Jar ao usar o DITA-OT personalizado para publicação. Essa é uma configuração obrigatória, dependendo do caso de uso. Essa alteração será necessária somente se você usar DITA-OT personalizado para saída de publicação.

  *Configuração necessária*: substitua o arquivo Xerces Jar do pacote DITA-OT personalizado pelo arquivo OOTB fornecido. O arquivo `xercesImpl-2.11.0.jar` OOTB padrão está disponível no arquivo `/libs/fmdita/dita\_resources/DITA-OT.zip`. Renomeie o arquivo `xercesImpl-2.11.0.jar` para corresponder ao arquivo Xerces Jar antigo que está sendo substituído. Isso pode ser feito em tempo de execução.

  Essa alteração reduz o tempo de publicação e a utilização da memória durante a publicação de mapas DITA com um grande número de tópicos.

