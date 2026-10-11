---
title: Configurar a geração de PDF de um único tópico
description: Saiba como Configurar a geração de PDF de um único tópico
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: a456027a-56a4-48c0-a79b-2f423692abc2
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%
---
# Configurar a geração de PDF de um único tópico para o Cloud Service

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

Depois de executar as etapas fornecidas acima, se você escolher o mesmo perfil de pasta em Preferências do usuário no Editor, verá a opção para geração de PDF no modo de visualização de um tópico.

**Tópico pai:**[ Personalizar editor](customize-overview.md)
