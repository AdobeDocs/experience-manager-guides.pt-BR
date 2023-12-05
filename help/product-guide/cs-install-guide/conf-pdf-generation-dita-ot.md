---
title: Configurar a geração de PDF de um único tópico
description: Saiba como configurar a geração de PDF de um único tópico
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Configurar a geração de PDF de um único tópico {#id22ADC70M0XA}

Com os Guias AEM, você pode gerar o PDF de tópicos individuais ou um arquivo de mapa inteiro. Você pode publicar seus tópicos em um formato PDF usando o método PDF nativo ou DITA-OT. Use o método PDF nativo para gerar uma saída de PDF repleta de recursos com base no W3C CSS3 e nos padrões de mídia paginada CSS. Você pode usar o método DITA-OT para gerar uma saída de PDF para um mapa a partir do painel de mapa.

>[!NOTE]
>
> O PDF nativo é o método padrão para gerar um PDF na versão atual das Guias do AEM.

Para ativar a geração de PDF antiga por meio do DITA-OT a partir do modo de visualização de tópico, execute as seguintes etapas:

1. Faça logon no Adobe Experience Manager como administrador e baixe o arquivo de configuração da interface.

1. Para fazer isso, clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecionar **Guias** na lista de ferramentas e clique no botão **Perfis de pasta**.
1. Clique no link **Perfil global** bloco.
1. Selecione o **Configuração do editor XML** e clique em **Editar** ícone na parte superior
1. Clique em **Baixar** ícone para baixar o arquivo ui\_config.json no sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.
1. No `ui_config.json` , localize a seguinte configuração:

   ```
   {
                           "component": "button",
                           "variant": "action",
                           "quiet": true,
                           "icon": "filePDF",
                           "title": "Download as PDF",
                           "on-click": "EDITOR_SAVE_AS_PDF"
                           }
   ```

   e substitua-o por

   ```
   {
                           "component": "button",
                           "icon": "filePDF",
                           "variant": "action",
                           "quiet": true, "title": "Export as PDF",
                           "on-click": "DOWNLOAD_TOPIC_PDF",
                           "show" : ["@isPreviewMode", "@isXmlMode"]
                           }
   ```

1. Salve o arquivo e faça upload dele.

Depois de executar as etapas fornecidas acima, se você escolher o mesmo perfil de pasta em Preferências do usuário no Editor da Web, verá a opção para geração de PDF no modo de visualização de um tópico.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
