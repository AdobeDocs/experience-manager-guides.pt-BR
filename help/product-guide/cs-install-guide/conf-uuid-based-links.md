---
title: Configurar a exibição de links baseados em UUID
description: Saiba como Configurar a exibição de links baseados em UUID
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%

---

# Configurar a exibição de links baseados em UUID {#id2035G20M0QN}

Por padrão, ao criar um link usando a opção Inserir referência ou Inserir conteúdo de reutilização no Editor da Web, o link é criado usando a UUID do conteúdo referenciado. A propriedade **Link** \(no painel Propriedades\) do conteúdo referenciado pode ser configurada para mostrar o caminho de arquivo relativo do conteúdo referenciado ou da UUID. Por padrão, a UUID do conteúdo referenciado é mostrada no painel Propriedades.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para mostrar o caminho relativo ou a UUID do conteúdo referenciado no Editor da Web:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Booleano \(true/false\). Se quiser mostrar o caminho relativo do conteúdo vinculado, defina essa propriedade como false. <br> **Valor padrão**: verdadeiro |

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
