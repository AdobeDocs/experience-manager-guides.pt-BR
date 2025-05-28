---
title: Substituições de configuração
description: Saiba como configurar substituições
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
feature: Installation
role: Admin
level: Experienced
source-git-commit: e4b213b5f0efda18fb24f100f3ee8237947890bf
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Substituições de configuração {#id216IFC003XA}

Para fazer atualizações de configuração, a seguinte abordagem genérica deve ser usada:

1. Acesse o repositório Git do Cloud Manager.

1. Crie um novo arquivo JSON no seguinte local:

   src/main/content/jcr\_root/apps/fmditaCustom/config/

1. Nomeie o arquivo no seguinte formato:

   $\{PID\}.cfg.json

   Aqui, o PID é a ID do processo da configuração.

1. Adicione propriedades no arquivo JSON usando o seguinte formato:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Confirme as alterações e execute o pipeline do Cloud Manager para implantar a configuração atualizada.

## Configurar a interface do usuário do Experience Manager Guides

A versão 2025.02.0 do Adobe Experience Manager Guides traz uma interface do usuário renovada e recursos aprimorados para ajudá-lo a trabalhar com mais rapidez e eficiência do que nunca. Isso inclui uma nova página inicial, uma barra de ferramentas do editor mais limpa e organizada, um console de mapas dedicado e recursos aprimorados.

Para garantir uma transição suave e minimizar as interrupções, o Experience Manager Guides fornece uma opção de configuração que permite alternar de volta para a interface antiga ( e vice-versa), conforme necessário.

>[!IMPORTANT]
>
> Essa opção de configuração para alternar entre a interface nova e a antiga era compatível até a versão 2025.4.0. Com a versão 2025.6.0, essa configuração foi preterida e não pode mais ser usada para reverter para a interface antiga.

Execute as seguintes etapas para configurar a interface do usuário do Experience Manager Guides:

1. Abra o Adobe Experience Manager e selecione seu programa que contenha o ambiente que você deseja configurar.
2. Alterne para a guia **Ambientes**.
3. Selecione o nome do ambiente que deseja configurar. Você deve ir para a página **Informações sobre o ambiente**.
4. Alterne para a guia **Configuração**.
5. Selecione **Adicionar/Atualizar**.
6. Adicione os detalhes de configuração da interface do usuário. Certifique-se de usar o mesmo nome e configuração fornecidos na captura de tela a seguir.

   ![](assets/enable-penultimate-ui.png){width="800" align="left"}

   Definir o valor como **true** retém a interface antiga, enquanto **false** ativa a nova interface.



**Tópico pai:**[ Baixar e instalar](download-install.md)
