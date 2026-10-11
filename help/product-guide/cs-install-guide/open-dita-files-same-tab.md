---
title: Abrir tópico DITA ou mapear arquivos na mesma guia
description: Saiba como Abrir um tópico DITA ou mapear arquivos na mesma guia
exl-id: 466cbea4-c75a-488e-bde2-465cf2c184d5
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/futODy2B62sg-Epb4bnmxHVAOUVoGDoKg5WJWV-7bpM'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
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
source-wordcount: '207'
ht-degree: 0%
---
# Abrir tópico DITA ou mapear arquivos na mesma guia {#id223HH0301J3}

Em alguns workflows, ao clicar em um link de um tópico ou arquivo de mapa, ele é aberto em uma nova guia. Isso pode levar a muitas guias abertas no navegador, o que pode afetar sua produtividade. Você pode alterar esse comportamento de abrir um tópico ou arquivo de mapa em uma nova guia e forçá-lo a abrir na própria guia atual.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para abrir um tópico ou mapear arquivo em uma nova guia:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Booleano \(true/false\). <br> **Valor padrão**: `false` |

Essa configuração afeta os seguintes locais de onde você pode acessar o tópico ou mapear arquivos:

- Criar tópico DITA \(no final do fluxo de trabalho, ao clicar no botão **Abrir tópico**\)

- Criar Mapa DITA \(no final do fluxo de trabalho, ao clicar no botão **Abrir Mapa**\)

- Guia Tópicos no console do mapa DITA

- Guia Linhas de Base no console de mapa DITA

- Guia Relatórios no console de mapa DITA


**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](conf-web-editor.md)
