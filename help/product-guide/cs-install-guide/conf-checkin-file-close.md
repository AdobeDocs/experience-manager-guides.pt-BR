---
title: Configurar prompt para fazer check-in de um arquivo ao fechar
description: Saiba como configurar o prompt para fazer check-in de um arquivo ao fechar
exl-id: 5b09ec46-aea4-4a3f-8bab-42414e31e37d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---

# Configurar prompt para fazer check-in de um arquivo ao fechar {#id222HC040PE8}

Quando o usuário tenta fechar um arquivo aberto no Editor da Web usando o **Fechar** na guia do arquivo ou na guia **Fechar** no menu Opções, uma caixa de diálogo será exibida se o arquivo tiver dados não salvos ou uma versão não salva. O usuário será solicitado a desbloquear o arquivo se ele estiver bloqueado.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar um prompt para fazer check-in de um arquivo ao fechar:

| PID | Chave de propriedade | Valor da propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booleano\\ ( true/ false\).<br> **Valor padrão**: falso |

Quando essa configuração estiver ativada, a variável **Desbloquear o arquivo** é marcada por padrão na caixa de diálogo.

Para obter mais detalhes, consulte *Cenários de fechamento e salvamento de arquivos* no guia as a Cloud Service Usar guias do Adobe Experience Manager.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
