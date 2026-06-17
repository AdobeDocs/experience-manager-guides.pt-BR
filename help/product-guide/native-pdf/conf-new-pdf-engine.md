---
title: Ativar novo mecanismo do PDF
description: Saiba como ativar o novo mecanismo do PDF no Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 2%

---


# Configurar o mecanismo nativo do PDF v2

O novo mecanismo de publicação do PDF Nativo, ou seja, o _Mecanismo do PDF Nativo v2_, fornece recursos de renderização do PDF atualizados e correções para _Problemas do mecanismo do PDF Nativo v1_.

Use as instruções fornecidas em [Substituições de configuração](../install-conf-guide/download-install-config-override.md) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

| PID | Chave de propriedade | Valor de propriedade |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Valor padrão: `v1` |