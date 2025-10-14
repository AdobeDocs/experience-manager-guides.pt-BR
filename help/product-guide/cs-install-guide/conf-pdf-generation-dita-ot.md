---
title: Configurar a geração de PDF de um único tópico
description: Saiba como configurar a geração de PDF de um único tópico
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Configurar a geração de PDF de um único tópico {#id22ADC70M0XA}

Com a AEM Guides, você pode gerar o PDF de tópicos individuais ou um arquivo de mapa inteiro. Você pode publicar seus tópicos em um formato PDF usando o método PDF nativo ou DITA-OT. Use o método PDF nativo para gerar uma saída de PDF repleta de recursos com base no W3C CSS3 e nos padrões de mídia paginada CSS. Você pode usar o método DITA-OT para gerar uma saída de PDF para um mapa a partir do painel de mapa.

>[!NOTE]
>
> PDF nativo é o método padrão para gerar um PDF na versão atual do AEM Guides.

Para ativar a geração de PDF antiga por meio do DITA-OT a partir do modo de visualização de tópico, execute as seguintes etapas:

1. Faça logon no Adobe Experience Manager como administrador e baixe o arquivo de configuração da interface.

1. Para fazer isso, clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Selecione a guia **Configuração do editor XML** e clique no ícone **Editar** na parte superior
1. Clique no ícone **Baixar** para baixar o arquivo ui\_config.json em seu sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.
1. No arquivo `ui_config.json`, localize a seguinte configuração:

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

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](conf-web-editor.md)
