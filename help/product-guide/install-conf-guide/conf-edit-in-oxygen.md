---
title: Configurar a opção para editar no Oxygen
description: Saiba como configurar a opção para editar no plug-in do conector Oxygen.
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 41ecbbb2-81c3-473d-b48b-7370a74a6474
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Configure a opção para editar no Oxygen for Cloud Service

O AEM Guides também permite que os usuários editem seus tópicos DITA e mapas DITA no plug-in do conector Oxygen.

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar a opção **Editar no Oxygen**:



| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Booleano \(true/false\). **Valor padrão**: falso |

>[!NOTE]
>
> Essa configuração é desativada por padrão e a opção não está disponível no Editor.

**Tópico pai:**[ Personalizar editor](customize-overview.md)
