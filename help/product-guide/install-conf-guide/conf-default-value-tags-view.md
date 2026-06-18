---
title: Configurar valor padrão para a exibição de tags
description: Saiba como Configurar o valor padrão para a exibição de tags
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: d54e3a3c-9f61-43cf-a925-12e4ce948a55
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
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
