---
title: Atualizar o AEM Guides
description: Saiba como atualizar o AEM Guides
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/jGMljbRp60Wst7hVLeanMTLHY79Yhqo7yeUCCsLXx3k
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 114
ht-degree: 0%

---

# Atualizar o AEM Guides {#id213BD050YPH}

1. Acesse o repositório Git do Cloud Manager.

1. Atualize o arquivo dox/dox.installer/pom.xml.

1. Atualize o valor da variável dox.version para os detalhes de versão fornecidos pelo Adobe.

1. Confirme as alterações e execute o pipeline do Cloud Manager para implantar o pacote atualizado.


>[!NOTE]
>
> Para obter mais detalhes sobre como usar o pipeline de CI/CD, consulte [Usar o pipeline de CI/CD no Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html?lang=pt-BR).

## Limpar cache do navegador

Após concluir o processo de atualização, todos os usuários devem limpar o cache do navegador antes de usar a versão atualizada do AEM Guides.

**Tópico pai:**&#x200B;[&#x200B; Baixar e instalar](download-install.md)
