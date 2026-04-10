---
title: Instalar o Adobe Experience Manager
description: Saiba como instalar o Adobe Experience Manager
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Instalar o Adobe Experience Manager {#id213BCI020E8}

O AEM Guides é um plug-in que é instalado sobre o Adobe Experience Manager. A instalação do AEM exige a compreensão de alguns conceitos básicos do AEM e cenários de implantação recomendados. Os recursos de link a seguir ajudarão você a começar a instalação do AEM:

- [Conceitos Básicos do AEM](https://helpx.adobe.com/br/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

- [Implantações recomendadas do AEM](https://helpx.adobe.com/br/experience-manager/6-5/sites/deploying/using/recommended-deploys.html)

>[!IMPORTANT]
>
> Se você estiver usando o Java 11 com o AEM 6.5.x, poderá enfrentar um problema - *O JDK 11 causa`NoClassDefFoundError`*. Consulte o artigo [JDK 11 cause NoClassDefFoundError \| AEM 6.5](https://helpx.adobe.com/experience-manager/kb/jdk-11-causes-noclassdeffounderror---aem-6-5.html) para resolver esse problema.

Depois de identificar a estratégia de implantação que funciona melhor para sua organização, execute o processo de instalação conforme descrito na seção *[Introdução](https://helpx.adobe.com/br/experience-manager/6-5/sites/deploying/using/deploy.html#GettingStarted)* da documentação do AEM.

Se você planeja atualizar sua instância do AEM, siga a sequência fornecida:

1. Desinstale o AEM Guides.
1. Atualize sua instância do AEM.
1. Reinstale o AEM Guides.

>[!IMPORTANT]
>
> Há várias recomendações de otimização de desempenho que você pode considerar para melhorar o desempenho do seu sistema. Consulte [Recomendações para otimização de desempenho](./perf-optimization-on-prem.md) para obter detalhes.
