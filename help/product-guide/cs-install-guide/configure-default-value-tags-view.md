---
title: Configurar valor padrão para a exibição de tags
description: Saiba como Configurar o valor padrão para a exibição de tags
exl-id: 3ab75101-4c23-4e45-bfcf-76c1f5b92c96
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/e-BZ7-itZXflsqHW9-5Vo6ktr9RS73xdIWMZh4BU2MU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 215
ht-degree: 0%

---

# Configurar valor padrão para a exibição de tags {#id223GN0M0NDC}

O AEM Guides permite configurar o estado padrão para a Exibição de tags no Editor da Web, o que ajuda a manter a Exibição de tags ativada ou desativada por padrão para a sessão de um novo usuário.Execute as seguintes etapas para configurar o valor padrão para a Exibição de tags:

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

1.) Salve o arquivo e faça upload dele.

>[!NOTE]
>
> A preferência do usuário no Editor da Web para ativar/desativar a Visualização de tags tem precedência sobre esse valor padrão. Portanto, se um usuário ativar a Exibição de tags no Editor da Web, ela permanecerá ativada mesmo nas sessões.

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](conf-web-editor.md)
