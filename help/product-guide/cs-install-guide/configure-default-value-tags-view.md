---
title: Configurar valor padrão para a exibição de tags
description: Saiba como Configurar o valor padrão para a exibição de tags
exl-id: 3ab75101-4c23-4e45-bfcf-76c1f5b92c96
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Configurar valor padrão para a exibição de tags {#id223GN0M0NDC}

O AEM Guides permite configurar o estado padrão para a Exibição de tags no Editor da Web, o que ajuda a manter a Exibição de tags ativada ou desativada por padrão para a sessão de um novo usuário.Execute as seguintes etapas para configurar o valor padrão para a Exibição de tags:

1. Baixe o arquivo de configuração da interface do usuário fazendo logon no Adobe Experience Manager como administrador.
1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecionar **Guias** na lista de ferramentas e clique no botão **Perfis de pasta**.
1. Clique no link **Perfil global** bloco.
1. Selecione o **Configuração do editor XML** e clique na guia **Editar** ícone na parte superior.
1. No **Configuração da interface do Editor de XML** clique na guia **Baixar** ícone para baixar o `ui_config.json` no sistema local.
1. No `ui_config.json` altere o estado de exibição das tags padrão alterando a seção defaultValues como mostrado abaixo:

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

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
