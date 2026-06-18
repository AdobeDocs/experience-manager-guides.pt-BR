---
title: Configurar prompt para fazer check-in de um arquivo ao fechar
description: Saiba como configurar o prompt para fazer check-in de um arquivo ao fechar
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 6b1b5894-0d55-4230-83cf-6b219e969116
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Configurar prompt para fazer check-in de um arquivo ao fechar {#id222HC040PE8}

Quando o usuário tenta fechar um arquivo aberto no Editor usando o botão **Fechar** na guia do arquivo ou a opção **Fechar** no menu Opções, uma caixa de diálogo é exibida se o arquivo tiver dados não salvos ou uma versão não salva. O usuário será solicitado a desbloquear o arquivo se ele estiver bloqueado.

As guias a seguir fornecem instruções para configurar o prompt para fazer check-in de um arquivo na opção fechar por padrão no Editor com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar um prompt para fazer check-in de um arquivo ao fechar:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booleano\ ( true/ false\).<br> **Valor padrão**: falso |

Quando esta configuração está habilitada, a caixa de seleção **Desbloquear o Arquivo** é marcada por padrão na caixa de diálogo.

Para obter mais detalhes, consulte a seção *Cenários de fechamento e salvamento de arquivos* no guia Uso do Adobe Experience Manager Guides as a Cloud Service.

>[!TAB No local]

>[!NOTE]
>
>A caixa de seleção **Desbloquear o Arquivo** não está habilitada por padrão e você precisa habilitá-la no configMgr. Execute as seguintes etapas para ativar a opção por padrão no Editor:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Selecione a opção **Solicitar check-in ao fechar**.

1. Clique em **Salvar**.


Quando esta configuração está habilitada, a caixa de seleção **Desbloquear o Arquivo** é marcada por padrão na caixa de diálogo.

Para obter mais detalhes, consulte a seção *Cenários de fechamento e salvamento de arquivos* no guia Uso do Adobe Experience Manager Guides as a Cloud Service.

>[!ENDTABS]

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor](customize-overview.md)
