---
title: Configurar a opção para editar no Oxygen
description: Saiba como configurar a opção para editar no plug-in do conector Oxygen.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Configurar a opção para editar no Oxygen

O Guia AEM também permite que os usuários editem seus tópicos DITA e mapas DITA no plug-in do conector Oxygen.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar o **Editar no Oxygen** opção:



| PID | Chave de propriedade | Valor da propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Booleano \(true/false\). **Valor padrão**: falso |

>[!NOTE]
>
> Essa configuração é desativada por padrão e a opção não está disponível no Editor da Web.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
