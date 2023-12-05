---
title: Definir o Editor de mapa avançado como padrão
description: Saiba como definir o Editor de mapa avançado como padrão
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Definir o Editor de mapa avançado como padrão {#id181AI0003PN}

O AEM Guides vem com um Editor de Mapas Básico e um Editor de Mapas Avançado. O Editor de mapa básico fornece todos os recursos necessários para criar seu arquivo de mapa. O Editor de mapa avançado possui muito mais recursos e está integrado ao Editor da Web. O Editor de mapa avançado permite que os autores criem e editem arquivos de mapa DITA com uma interface fácil de usar.

Por padrão, sempre que um novo arquivo de mapa é criado, ele é aberto no Editor de mapa básico. Você pode alterar esse comportamento ativando a configuração para abrir o Editor de mapa avançado por padrão.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para ativar o Editor de mapa básico:

| PID | Chave de propriedade | Valor da propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Booleano \(true/false\). Se você quiser usar o Editor de mapa avançado por padrão, defina essa propriedade como true.<br> **Valor padrão**: falso |

>[!NOTE]
>
> Por padrão, quando um autor cria um arquivo de mapa e opta por abri-lo para edição, o Editor de mapa básico é iniciado. Quando a opção Editar é selecionada para um arquivo de mapa na interface do usuário do Assets, ela também é aberta no Editor de mapa básico.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
