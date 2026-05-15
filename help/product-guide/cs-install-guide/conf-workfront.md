---
title: Configurar o Adobe Workfront no Experience Manager Guides
description: Saiba como configurar o Workfront no Experience Manager Guides
feature: Authoring
role: Admin
level: Experienced
exl-id: 1f72642c-e694-47cd-9182-f4f4aaf69655
TQID: https://experienceleague.adobe.com/Yua4Y6xsnec3O-hpTNhSmK4HvsCwaGYbLTxUxEeQAKY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: ae478996-b206-4712-9b0c-dc78a2644453id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f7774ebe-aec9-42b6-97e4-5002acdc712e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 600
ht-degree: 2%

---

# Configurar Adobe Workfront

O Adobe Workfront é uma solução de gerenciamento de trabalho baseada em nuvem que ajuda equipes e organizações a planejar, rastrear e gerenciar seu trabalho com eficiência. A integração entre o Experience Manager Guides e o Adobe Workfront oferece acesso a recursos robustos de gerenciamento de projetos além dos principais recursos do CCMS do Experience Manager Guides, permitindo planejar, alocar e rastrear tarefas com eficiência.

Saiba mais sobre a [integração do Adobe Workfront](../user-guide/workfront-integration.md) no Experience Manager Guides.

## Pré-requisitos

Antes de começar, verifique se:

1. Você tem acesso padrão ao Adobe Workfront e acesso de administrador ao Experience Manager Guides.
2. Você [cria um novo formulário personalizado no Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) necessário para o Experience Manager Guides usando especificamente os campos abaixo:

   | Tipo de campo | Rótulo | Nome | Opções (Mostrar valores ativados) |
   |------------|------|------|-------------------------------|
   | Lista suspensa de seleção única | Tipo de tarefa | tipo-tarefa | Criação (valor = AUTOR), Publicação (valor = PUBLICAR), Tradução (valor = TRADUÇÃO), Revisão (valor = REVISÃO) |
   | Lista suspensa de seleção única | Estado da tarefa | task-state | Criação (valor = AUTOR), Publicação (valor = PUBLICAR), Tradução (valor = TRADUÇÃO), Revisão (valor = REVISÃO) |
   | Texto com formatação | Lista de autores | lista de autores | - |
   | Texto com formatação | Lista de Revisores | lista de revisores | - |
   | Texto em linha única | URL da revisão | url de revisão | - |
   | Texto em linha única | URL da tarefa | url da tarefa | - |
   | Texto em linha única | Assunto do email | assunto do email | - |

>[!NOTE]
>
> * Na tabela acima, as opções representam as opções disponíveis no campo **Tipo de tarefa**. Para cada opção, você precisaria fornecer o **nome da tarefa** e o **valor da tarefa**. O nome e os valores de cada tipo de tarefa devem ser exatamente os mesmos mencionados na tabela acima. Por exemplo, para o tipo de tarefa Autor, forneça **Autoria** como nome e **AUTOR** como seu valor correspondente.
> * Ao trabalhar com serviços no local, sempre verifique se `localhost` foi substituído pelo endereço de servidor correto na configuração do **Day CQ Link Externalizer** para receber corretamente o link da tarefa resolvida nas notificações por email.
> * Ao criar uma tarefa de revisão no Workfront, os usuários (autores ou revisores) devem fazer parte do grupo **workflow-users**. Além disso, como um **Autor**, você deve fazer parte do grupo **autores-de-conteúdo** e **autores**, enquanto como um **Revisor**, você deve fazer parte do grupo **revisores**.


## Introdução

Execute as seguintes etapas para configurar o Adobe Workfront no Experience Manager Guides.

1. Abra o **painel Ferramentas** e selecione **Guias**.
2. Selecione **Configurar Workfront**.

   A página **Configuração do Workfront** é exibida.

   ![](assets/configure-workfront-page.png)

3. Na página **Configuração do Workfront**, digite a URL completa do domínio do Workfront, a ID do cliente e a chave Segredo do cliente da sua organização.

   Para acessar a chave **ID do Cliente** e **Segredo do Cliente** configuradas na sua configuração do Adobe Workfront, navegue até `Setup >> Systems>> oAuth2 Applications`.

   Para obter mais detalhes sobre como configurar o domínio do Adobe Workfront, consulte a seção Fluxo do código de autorização em [Criar aplicativos OAuth2 para integrações do Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/configure-integrations/create-oauth-application#create-an-oauth2-application-using-user-credentials-authorization-code-flow).

4. Selecione **Fazer logon e verificar**.

   Você é redirecionado para a página de logon da Adobe Workfront.
5. Entre usando seu endereço de email do Adobe Workfront e selecione **Permitir acesso** para permitir que o aplicativo Oauth2 acesse sua respectiva conta do Adobe Workfront.

   Você é redirecionado automaticamente para a página de configuração do Workfront no Experience Manager Guides.

6. Na lista suspensa formulário personalizado, selecione o formulário personalizado Adobe Workfront que você criou para o Experience Manager Guides. Exibir [Pré-requisitos](#prerequisites).
7. Selecione **Salvar e fechar** para aplicar e salvar as alterações de configuração do Workfront.

Após a configuração, [adicione usuários ao Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) usando os mesmos endereços de email que eles têm no Experience Manager Guides.
