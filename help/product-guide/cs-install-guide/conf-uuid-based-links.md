---
title: Configurar a exibição de links baseados em UUID
description: Saiba como Configurar a exibição de links baseados em UUID
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/--RdjezGIsplCdBLF8u-3LvR92rVBcgGmPo8a7GbQys'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
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
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 1%
---
# Configurar a exibição de links baseados em UUID {#id2035G20M0QN}

Por padrão, ao criar um link usando a opção Inserir referência ou Inserir conteúdo de reutilização no Editor da Web, o link é criado usando a UUID do conteúdo referenciado. A propriedade **Link** \(no painel Propriedades\) do conteúdo referenciado pode ser configurada para mostrar o caminho de arquivo relativo do conteúdo referenciado ou da UUID. Por padrão, a UUID do conteúdo referenciado é mostrada no painel Propriedades.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para mostrar o caminho relativo ou a UUID do conteúdo referenciado no Editor da Web:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Booleano \(true/false\). Se quiser mostrar o caminho relativo do conteúdo vinculado, defina essa propriedade como false. <br> **Valor padrão**: verdadeiro |

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](conf-web-editor.md)
