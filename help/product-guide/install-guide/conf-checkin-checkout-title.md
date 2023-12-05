---
title: Configurar título para os ícones de check-in e check-out
description: Saiba como configurar o título para ícones de check-in e check-out
exl-id: a8888a17-e819-4fa2-bb6f-cafe1002803a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Configurar o título para os ícones Fazer check-in e Check-out

O AEM Guides permite configurar o título para os ícones Check-in e Check-out no Editor da Web. Execute as seguintes etapas para configurar o título para os ícones Fazer check-in e Fazer check-out:

1. Baixe o arquivo de configuração da interface do usuário fazendo logon no Adobe Experience Manager como administrador.
1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecionar **Guias** na lista de ferramentas e clique no botão **Perfis de pasta**.
1. Clique no link **Perfil global** bloco.
1. Selecione o **Configuração do editor XML** e clique na guia **Editar** ícone na parte superior.
1. No **Configuração da interface do Editor de XML** clique na guia **Baixar** ícone para baixar o `ui_config.json` no sistema local.
1. No `ui_config.json` alterar o título na seção &quot;barra superior&quot;. Você pode alterar os seguintes valores:

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Salve o arquivo e faça upload dele.
