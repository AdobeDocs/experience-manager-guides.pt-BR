---
title: Recommendations para otimização de desempenho
description: Conheça o Recommendations para otimização de desempenho
exl-id: 92ac1f81-2f51-44b0-82c3-56b39e8f3027
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Recommendations para otimização de desempenho {#id213BD0JG0XA}

Para otimização de desempenho, considere os seguintes pontos:

- Para otimizar a experiência de conteúdo e indexação, consulte [Otimizar a pesquisa e a indexação de conteúdo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=pt-BR) na documentação do AEM.

- Corrija o Xerces Jar ao usar o DITA-OT personalizado para publicação. Essa é uma configuração obrigatória, dependendo do caso de uso. Essa alteração será necessária somente se você usar DITA-OT personalizado para saída de publicação.

  *Configuração necessária*: substitua o arquivo Xerces Jar no pacote DITA-OT personalizado pelo arquivo OOTB fornecido. O arquivo padrão OOTB xercesImpl-2.11.0.jar está disponível no arquivo /libs/fmdita/dita\_resources/DITA-OT.zip. Renomeie o arquivo xercesImpl-2.11.0.jar para corresponder ao arquivo Xerces Jar antigo que está sendo substituído. Isso pode ser feito em tempo de execução.

  Essa alteração reduz o tempo de publicação e a utilização da memória durante a publicação de mapas DITA com um grande número de tópicos.


**Tópico pai:**[ Baixar e instalar](download-install.md)
