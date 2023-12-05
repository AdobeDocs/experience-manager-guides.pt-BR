---
title: Integrar editores de XML baseados em desktop
description: Saiba como integrar editores XML baseados em desktop
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Integrar editores de XML baseados em desktop {#id181GB01G0HS}

Há muitos editores de XML disponíveis no mercado e você já pode estar usando um. O Adobe FrameMaker é um dos editores de XML mais eficientes, que vem com o conector AEM. Usando o conector AEM no FrameMaker, você pode se conectar facilmente ao repositório AEM, aos arquivos de check-out e check-in e editar os arquivos diretamente no FrameMaker. Você também pode configurar os Guias do AEM para iniciar o FrameMaker no Editor da Web. Após abrir o arquivo no FrameMaker, você pode editá-lo e devolvê-lo ao repositório AEM.

## Ativar edição de arquivos no FrameMaker a partir do Editor da Web

Você pode usar o FrameMaker ou qualquer outro editor DITA para criar e atualizar conteúdo DITA. No entanto, se sua organização usar o FrameMaker como editor DITA, você poderá dar aos usuários a opção de abrir documentos DITA diretamente no FrameMaker usando o AEM.

Por padrão, os usuários não veem a variável **Abrir no FrameMaker** na barra de ferramentas do AEM. Execute as seguintes etapas para adicionar esse botão à barra de ferramentas do AEM:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacote.

   ![](assets/open-in-fm-toolbar.png){width="550" align="left"}

1. Selecione o **Mostrar botão Abrir no FrameMaker** opção.

1. Clique em **Salvar**.


Quando você habilita o **Mostrar botão Abrir no FrameMaker** e, em seguida, a **Abrir no FrameMaker** é exibido ao selecionar qualquer arquivo DITA no repositório AEM. Quando essa opção é *não ativado*, o **Abrir no FrameMaker** O botão é exibido somente quando você seleciona um arquivo .fm ou .book no repositório.
