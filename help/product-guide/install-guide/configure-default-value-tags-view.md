---
title: Configurar valor padrão para a exibição de tags
description: Saiba como Configurar o valor padrão para a exibição de tags
exl-id: 52214459-74b8-47ec-982b-6176145348a8
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configurar valor padrão para a exibição de tags {#id223GN0M0NDC}

O AEM Guides permite configurar o estado padrão para a Exibição de tags no Editor da Web, o que ajuda a manter a Exibição de tags ativada ou desativada por padrão para a sessão de um novo usuário. Execute as seguintes etapas para configurar o valor padrão para a Exibição de tags:

1. Baixe o arquivo de configuração da interface do usuário fazendo logon no Adobe Experience Manager como administrador.
1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Selecione a guia **Configuração do editor XML** e clique no ícone **Editar** na parte superior.
1. Na seção **Configuração da interface do Editor de XML**, clique no ícone **Baixar** para baixar o arquivo `ui_config.json` no sistema local.
1. No arquivo `ui_config.json`, altere o estado de exibição das marcas padrão alterando a seção defaultValues como mostrado abaixo:

   ```json
   "defaultValues":
                   {
                   "tagsView": true
                   }
   ```

1. Salve o arquivo e faça upload dele.

>[!NOTE]
>
> A preferência do usuário no Editor da Web para ativar/desativar a Visualização de tags tem precedência sobre esse valor padrão. Portanto, se um usuário ativar a Exibição de tags no Editor da Web, ela permanecerá ativada mesmo nas sessões.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
