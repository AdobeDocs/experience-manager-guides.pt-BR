---
title: Configurar o salvamento automático de arquivos no Editor da Web
description: Saiba como configurar o salvamento automático de arquivos no Editor da Web
exl-id: 4d99c3d8-cf6a-4cf3-aaec-9009a0376c1e
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 1%

---

# Configurar o salvamento automático de arquivos no Editor da Web {#id199CC0J0M5Z}

Um dos recursos mais comuns no editor baseado em navegador é a capacidade de salvar dados após um período específico. O Editor da Web do AEM Guides também oferece suporte ao salvamento automático de arquivos de tópico e de mapa no intervalo de tempo especificado. Quando esse recurso é acionado, a cópia de trabalho do tópico ou mapa é salva. Não é criada uma nova versão do tópico ou mapa. Para criar uma nova versão, é necessário clicar no ícone Salvar revisão na barra de ferramentas do Editor da Web.

O recurso de salvamento automático não está habilitado por padrão e você precisa habilitá-lo usando o arquivo de configuração.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(property\) para configurar o intervalo de tempo de salvamento automático e de salvamento automático do arquivo:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Booleano \(true/false\).<br> **Valor padrão**: falso |
| `xmleditor.autosaveinterval` | Especifique o intervalo de tempo em segundos para acionar o recurso de salvamento automático. |  |

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](conf-web-editor.md)
