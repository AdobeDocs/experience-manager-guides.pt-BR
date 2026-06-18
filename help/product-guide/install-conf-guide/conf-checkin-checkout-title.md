---
title: Configurar título para os ícones de check-in e check-out
description: Saiba como configurar o título para ícones de check-in e check-out
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 3032b49e-73d1-44d0-88b4-7e6e9444cac6
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Configurar o título para os ícones de Check-in e Check-out para no local

O AEM Guides permite configurar o título para os ícones Fazer check-in e Fazer check-out no Editor. Execute as seguintes etapas para configurar o título para os ícones Fazer check-in e Fazer check-out:

1. Baixe o arquivo de configuração da interface do usuário fazendo logon no Adobe Experience Manager como administrador.
1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Selecione a guia **Configuração do editor XML** e clique no ícone **Editar** na parte superior.
1. Na seção **Configuração da interface do Editor de XML**, clique no ícone **Baixar** para baixar o arquivo `ui_config.json` no sistema local.
1. No arquivo `ui_config.json`, altere o título na seção &quot;barra superior&quot;. Você pode alterar os seguintes valores:

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Salve o arquivo e faça upload dele.
