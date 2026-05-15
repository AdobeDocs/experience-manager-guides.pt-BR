---
title: Configurar a geração de PDF de um único tópico
description: Saiba como Configurar a geração de PDF de um único tópico
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/DinL1ZwovhmP61iQOQkW6XR-ALahlONxOU4e5UXpSGY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 0%

---

# Configurar a geração de PDF de um único tópico {#id22ADC70M0XA}

Com a AEM Guides, você pode gerar a PDF de tópicos individuais ou um arquivo de mapa inteiro. Você pode publicar seus tópicos em um formato PDF usando o PDF nativo ou o método DITA-OT. Use o método nativo do PDF para gerar uma saída de PDF repleta de recursos com base no W3C CSS3 e nos padrões de mídia paginada CSS. Você pode usar o método DITA-OT para gerar uma saída PDF para um mapa no painel de mapa.

>[!NOTE]
>
> O PDF nativo é o método padrão para gerar uma PDF na versão atual do AEM Guides.

Para ativar a geração antiga do PDF por meio do DITA-OT a partir do modo de visualização de tópico, execute as seguintes etapas:

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
