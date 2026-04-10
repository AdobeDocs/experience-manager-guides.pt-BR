---
title: Configurar o salvamento automático de arquivos no Editor da Web
description: Saiba como configurar o salvamento automático de arquivos no Editor da Web
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---

# Configurar o salvamento automático de arquivos no Editor da Web {#id199CC0J0M5Z}

Um dos recursos mais comuns no editor baseado em navegador é a capacidade de salvar dados após um período específico. O Editor da Web do AEM Guides também oferece suporte ao salvamento automático de arquivos de tópico e de mapa no intervalo de tempo especificado. Quando esse recurso é acionado, a cópia de trabalho do tópico ou mapa é salva. Não é criada uma nova versão do tópico ou mapa. Para criar uma nova versão, é necessário clicar no ícone Salvar revisão na barra de ferramentas do Editor da Web.

O recurso de salvamento automático não está habilitado por padrão e você precisa habilitá-lo usando o arquivo de configuração para o Cloud Service e do `configMgr` para No local.

As guias a seguir fornecem instruções para ativar o recurso de salvamento automático no Editor da Web com base na configuração do Experience Manager Guides: Cloud Service ou no local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(property\) para configurar o intervalo de tempo de salvamento automático e de salvamento automático do arquivo:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Booleano \(true/false\).<br> **Valor padrão**: falso |
| `xmleditor.autosaveinterval` | Especifique o intervalo de tempo em segundos para acionar o recurso de salvamento automático. |

>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nas configurações de *XmlEditorConfig*, selecione a opção **Salvar Automaticamente**.

1. No campo **Intervalo de Salvamento Automático**, especifique o intervalo de tempo em segundos para acionar o recurso de salvamento automático.

1. Clique em **Salvar**.

>[!ENDTABS]