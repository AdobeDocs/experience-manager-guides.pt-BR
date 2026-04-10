---
title: Configurar o prompt para salvar como uma nova versão ao fechar
description: Saiba como Configurar o prompt para salvar como uma nova versão ao fechar
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 1%

---

# Configurar o prompt para salvar como uma nova versão ao fechar {#id222HBI00XXA}

Quando o usuário tenta fechar um arquivo aberto no Editor da Web usando o botão **Fechar** na guia do arquivo ou a opção **Fechar** no menu Opções, uma caixa de diálogo é exibida se o arquivo tiver dados não salvos ou uma versão não salva. O usuário será solicitado a salvar o arquivo como uma nova versão se a versão não for salva.

As guias a seguir fornecem instruções com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar um prompt para salvar como uma nova versão ao fechar:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Booleano \( verdadeiro/ falso\). <br>  **Valor padrão**: verdadeiro |

Quando esta configuração está habilitada, a caixa de seleção **Salvar como uma Nova Versão** é marcada por padrão na caixa de diálogo.

Para obter mais detalhes, consulte a seção *Cenários de fechamento e salvamento de arquivos* no guia Uso do Adobe Experience Manager Guides as a Cloud Service.

>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Selecione a opção **Solicitar nova versão ao fechar**.

1. Clique em **Salvar**.


A caixa de seleção **Salvar como uma Nova Versão** não está habilitada por padrão e você precisa habilitá-la no configMgr.

Quando essa opção é selecionada, a caixa de seleção **Salvar como uma nova versão** é selecionada por padrão na caixa de diálogo.

Para obter mais detalhes, consulte a seção *Cenários de fechamento e salvamento de arquivos* no guia Uso do Adobe Experience Manager Guides as a Cloud Service.

>[!ENDTABS]