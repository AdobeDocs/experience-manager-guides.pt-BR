---
title: Configurar a opção para editar no Oxygen
description: Saiba como configurar a opção para editar no plug-in do conector Oxygen.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '107'
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
> Essa configuração é desativada por padrão e a opção não está disponível no Editor da Web.

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](customize-overview.md)
