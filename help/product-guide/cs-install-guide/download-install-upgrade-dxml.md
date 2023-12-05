---
title: Atualizar guias do AEM
description: Saiba como atualizar guias de AEM
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---

# Atualizar guias do AEM {#id213BD050YPH}

1. Acesse o repositório Git do Cloud Manager.

1. Atualize o arquivo dox/dox.installer/pom.xml.

1. Atualize o valor da variável dox.version para os detalhes de versão fornecidos pelo Adobe.

1. Confirme as alterações e execute o pipeline do Cloud Manager para implantar o pacote atualizado.


>[!NOTE]
>
> Para obter mais detalhes sobre o uso do pipeline de CI/CD, consulte [Usar o pipeline de CI/CD no Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Limpar cache do navegador

Após concluir o processo de atualização, todos os usuários devem limpar o cache do navegador antes de usar a versão atualizada dos Guias do AEM.

**Tópico pai:**[ Baixar e instalar](download-install.md)
