---
title: Ativar novo mecanismo do PDF
description: Saiba como ativar o novo mecanismo do PDF no Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: f89becea89888f7dec81e18c9220dcabda8f4e7d
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 4%
---

# Configurar o mecanismo nativo do PDF v2

O novo mecanismo de publicação do PDF Nativo, ou seja, o _Mecanismo do PDF Nativo v2_, fornece recursos de renderização do PDF atualizados e correções para _Problemas do mecanismo do PDF Nativo v1_.

>[!BEGINTABS]
>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](../install-conf-guide/download-install-config-override.md) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

| PID | Chave de propriedade | Valor de propriedade |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Valor padrão: `v1` |

>[!TAB No local]


Para implantações no local, sua disponibilidade depende das versões do AEM e do Java.

O _Mecanismo nativo do PDF v2_ requer o **Java 17 ou posterior**.

- **AEM 6.5:** o mecanismo de publicação nativo do PDF v2 não tem suporte porque o AEM 6.5 é executado no Java 8.
- **AEM 6.5 LTS:** o mecanismo de Publicação nativo do PDF v2 está habilitado por padrão. Nenhuma configuração adicional é necessária.

Se preferir voltar para o _Native PDF engine v2_ com o AEM 6.5 LTS, desinstale o pacote do PDF publisher:
`/crx/packmgr/index.jsp#/etc/packages/com.adobe.guides/pdf-publisher-package-3.0.0.zip` do Gerenciador de pacotes do CRX.

>[!ENDTABS]

