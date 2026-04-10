---
title: Integrar editores de XML baseados em desktop
description: Saiba como integrar editores XML baseados em desktop
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Integrar editores de XML baseados em desktop {#id181GB01G0HS}

Há muitos editores de XML disponíveis no mercado e você já pode estar usando um. O Adobe FrameMaker é um dos editores de XML mais eficientes, que vem com o AEM Connector. Usando o conector do AEM no FrameMaker, você pode se conectar facilmente ao repositório do AEM, aos arquivos de check-out e check-in e editar arquivos diretamente no FrameMaker. Você também pode configurar o Experience Manager Guides para iniciar o FrameMaker no Editor da Web. Após abrir o arquivo no FrameMaker, você pode editá-lo e fazer seu check-in no repositório do AEM.

## Ativar a edição de arquivos no FrameMaker a partir do Editor da Web

Você pode usar o FrameMaker ou qualquer outro editor DITA para criar e atualizar conteúdo DITA. No entanto, se sua organização usar o FrameMaker como editor DITA, você poderá dar aos usuários a opção de abrir documentos DITA diretamente no FrameMaker por meio do AEM.

Por padrão, seus usuários não veem o botão **Abrir no FrameMaker** na barra de ferramentas do AEM. Execute as seguintes etapas para adicionar esse botão à barra de ferramentas do AEM:

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



