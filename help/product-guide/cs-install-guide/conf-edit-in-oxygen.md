---
title: Configurar a opção para editar no Oxygen
description: Saiba como configurar a opção para editar no plug-in do conector Oxygen.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 1%

---

# Configurar a opção para editar no Oxygen

O AEM Guides também permite que os usuários editem seus tópicos DITA e mapas DITA no plug-in do conector Oxygen.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar a opção **Editar no Oxygen**:



| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Booleano \(true/false\). **Valor padrão**: falso |

>[!NOTE]
>
> Essa configuração é desativada por padrão e a opção não está disponível no Editor da Web.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
