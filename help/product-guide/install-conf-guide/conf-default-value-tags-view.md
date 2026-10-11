---
title: Configurar valor padrão para a exibição de tags
description: Saiba como Configurar o valor padrão para a exibição de tags
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: d54e3a3c-9f61-43cf-a925-12e4ce948a55
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
source-wordcount: '210'
ht-degree: 0%
---
# Configurar valor padrão para a exibição de tags {#id223GN0M0NDC}

O AEM Guides permite configurar o estado padrão para a Exibição de tags no editor, o que ajuda a manter a Exibição de tags ativada ou desativada por padrão para a sessão de um novo usuário.Execute as seguintes etapas para configurar o valor padrão para a Exibição de tags:

1. Baixe o arquivo de configuração da interface do usuário fazendo logon no Adobe Experience Manager como administrador.
1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Selecione a guia **Configuração do editor XML** e clique no ícone **Editar** na parte superior.
1. Na seção **Configuração da interface do Editor de XML**, clique no ícone **Baixar** para baixar o arquivo `ui_config.json` no sistema local.
1. No arquivo `ui_config.json`, altere o estado de exibição das marcas padrão alterando a seção defaultValues como mostrado abaixo:

   ```
   "defaultValues":
               {
               "tagsView": true
               }
   ```

1. Salve o arquivo e faça upload dele.

>[!NOTE]
>
> A preferência do usuário no Editor para ativar/desativar a Visualização de tags tem precedência sobre este valor padrão. Portanto, se um usuário ativar a Visualização de tags no Editor, ela permanecerá ativada mesmo nas sessões.

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor](customize-overview.md)
