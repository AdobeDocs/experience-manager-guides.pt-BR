---
title: Atualização do AEM Guides para Cloud Service
description: Saiba como atualizar o AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: 9d48a7c4-384d-4ad4-a1d3-4c50d97e5d5b
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 0%
---
# Atualização do AEM Guides para Cloud Service {#id213BD050YPH}

Execute as seguintes etapas para atualizar o AEM Guides:

1. Acesse o repositório Git do Cloud Manager.

1. Atualize o arquivo `dox/dox.installer/pom.xml`.

1. Atualize o valor da variável `dox.version` para os detalhes de versão fornecidos pelo Adobe.

1. Confirme as alterações e execute o pipeline do Cloud Manager para implantar o pacote atualizado.


>[!NOTE]
>
> Para obter mais detalhes sobre como usar o pipeline de CI/CD, consulte [Usar o pipeline de CI/CD no Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html?lang=pt-BR).

## Limpar cache do navegador

Após concluir o processo de atualização, todos os usuários devem limpar o cache do navegador antes de usar a versão atualizada do AEM Guides.
