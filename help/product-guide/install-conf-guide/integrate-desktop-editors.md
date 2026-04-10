---
title: Integrar editores de XML baseados em desktop
description: Saiba como integrar editores XML baseados em desktop
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 1%

---

# Integrar editores de XML baseados em desktop

Há muitos editores de XML disponíveis no mercado e você já pode estar usando um. O Adobe FrameMaker é um dos editores de XML mais eficientes, que vem com o AEM Connector. Usando o conector do AEM no FrameMaker, você pode se conectar facilmente ao repositório do AEM, aos arquivos de check-out e check-in e editar arquivos diretamente no FrameMaker. Você também pode configurar o Experience Manager Guides para iniciar o FrameMaker no Editor da Web. Após abrir o arquivo no FrameMaker, você pode editá-lo e fazer seu check-in no repositório do AEM.

## Ativar a edição de arquivos no FrameMaker a partir do Editor da Web

Você pode usar o FrameMaker ou qualquer outro editor DITA para criar e atualizar conteúdo DITA. No entanto, se sua organização usar o FrameMaker como editor DITA, você poderá dar aos usuários a opção de abrir documentos DITA diretamente no FrameMaker por meio do AEM.


Por padrão, seus usuários não veem o botão **Abrir no FrameMaker** na barra de ferramentas do AEM.

As guias a seguir fornecem instruções para adicionar esse botão à barra de ferramentas do AEM com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para adicionar este botão na barra de ferramentas do AEM:


| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Booleano \(true/false\). Se você quiser mostrar o botão **Abrir no FrameMaker**, defina essa propriedade como verdadeira. <br> **Valor padrão**: falso |



Se você estiver usando a versão 2409 e a versão de setembro do FrameMaker 2022 - Atualização 3, será necessário habilitar a configuração do **FrameMaker Versão 2022 Atualização 3 ou superior** para que seus usuários transmitam os detalhes do servidor do Experience Manager Guides para o FrameMaker.  Por padrão, está desativado.


| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Booleano \(true/false\). Se você estiver usando a versão de setembro do FrameMaker 2022 - Atualização 3, defina essa propriedade como true. <br> **Valor padrão**: falso |



Ao definir a propriedade *openinframebuttonshow* como true, o botão **Abrir no FrameMaker** é exibido ao selecionar qualquer arquivo DITA no repositório do AEM. Quando esta propriedade não está definida como *true*, o botão **Abrir no FrameMaker** é exibido somente quando você seleciona um arquivo .fm ou .book no repositório

>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.
   ![](assets/open-in-fm-config.png)

1. Selecione a opção **Mostrar botão Abrir no FrameMaker**.

1. Se você estiver usando a versão 4.6 e a versão de setembro do FrameMaker 2022 - Atualização 3, será necessário habilitar a configuração do **FrameMaker Versão 2022 Atualização 3 ou superior** para que seus usuários transmitam os detalhes do servidor do Experience Manager Guides para o FrameMaker. Por padrão, está desativado.


1. Clique em **Salvar**.


Ao habilitar a opção **Mostrar Botão Abrir no FrameMaker**, o botão **Abrir no FrameMaker** é exibido ao selecionar qualquer arquivo DITA no repositório do AEM. Quando esta opção está *não habilitada*, o botão **Abrir no FrameMaker** é exibido somente quando você seleciona um arquivo .fm ou .book no repositório.

>[!ENDTABS]
