---
title: Atualizar o AEM Guides
description: Saiba como atualizar o AEM Guides
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '98'
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
