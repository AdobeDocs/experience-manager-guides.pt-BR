---
title: Configurar o assistente de IA no modo Agente
description: Saiba como configurar o Assistente de IA do agente no Experience Manager Guides
source-git-commit: 5ed0a5191e1852dd65e0461f02d520b195f7cc39
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 1%
---

# Configurar o assistente de IA no modo Agente para o Cloud Service

Como administrador, você pode configurar o Assistente de IA no modo Agente para sua organização na Experience Manager Guides. As etapas de configuração variam dependendo se a configuração do Unified Shell está ativada em seu ambiente do AEM as a Cloud Service e se os usuários estão conectados por meio de autenticação SSO ou Não SSO. Este artigo descreve o processo de configuração de cada cenário.

## Pré-requisitos

Sua organização deve ser integrada ao **CX Enterprise Coworker** antes de configurar o Assistente de IA no modo Agente.

## Configurar o AI Assistant com base no seu ambiente

Use a tabela a seguir para identificar qual caminho de configuração se aplica aos usuários e, em seguida, siga as etapas correspondentes.

| Shell unificado | Tipo de logon | Configuração necessária |
|---|---|---|
| Habilitado | SSO | Nenhuma configuração adicional. Tudo funciona imediatamente |
| Habilitado | Não-SSO | Adicionar a configuração IMS ao ambiente |
| Desabilitado | SSO | Adicionar a configuração IMS ao ambiente |
| Desabilitado | Não-SSO | Adicionar a configuração IMS ao ambiente |

### Usuários com o shell unificado ativado

**Logon de SSO**

Se o Unified Shell estiver habilitado e seus usuários fizerem logon por meio do SSO, nenhuma configuração adicional será necessária. O Assistente de IA no modo Agente funciona automaticamente assim que sua organização é integrada ao CX Enterprise Coworker.

**Logon sem SSO**

Se o Unified Shell estiver habilitado, mas seus usuários fizerem logon sem SSO, você deverá [Adicionar a configuração IMS ao ambiente](#add-ims-configuration-to-the-environment) abaixo.

### Usuários com o Unified Shell desativado

Se o Unified Shell estiver desabilitado, você deverá [Adicionar a configuração do IMS ao ambiente](#add-ims-configuration-to-the-environment) para ambos:

- Logon de SSO
- Logon sem SSO

## Adicionar a configuração IMS ao ambiente

Execute as seguintes etapas para adicionar a configuração IMS ao ambiente:

1. Abra o Experience Manager e selecione seu programa que contenha o ambiente que você deseja configurar.

2. Alterne para a guia **Ambientes**.

3. Selecione o nome do ambiente que deseja configurar. Você será direcionado à página **Informações do ambiente**.

4. Alterne para a guia **Configuração**.

5. Cole os detalhes do serviço JSON (baixado quando você criou a configuração IMS no Adobe Developer Console) no campo **Value** correspondente a `SERVICE_ACCOUNT_DETAILS`. Certifique-se de usar o mesmo nome e a configuração esperados pelo ambiente.

>[!NOTE]
>Se você ainda não criou as credenciais do OAuth/IMS para seu ambiente, faça isso primeiro no Adobe Developer Console antes de concluir esta etapa.

![configuração da conta de serviço ims](assets/ims-service-account-config.png){width="800"}

## Ativar o modo Agente

Depois que a configuração do seu ambiente for concluída, entre em contato com a equipe de sucesso do cliente para ativar o modo Agente.

Com o modo Agente habilitado para o seu ambiente, navegue até **Configurações do Workspace** e habilite a opção **Agente** na guia **Geral** da seção **Assistente de IA**.
