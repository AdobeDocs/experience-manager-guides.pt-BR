---
title: Instalar e configurar o GitLab para Edge Delivery Services
description: Saiba como configurar repositórios do GitLab, tokens de acesso, Cloud Manager, webhooks e Trazer seu próprio Git para publicar conteúdo do Experience Manager Guides no Edge Delivery Services.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e5721ff1d6e2322213ac7bc988fb1d7e721cd148
workflow-type: tm+mt
source-wordcount: '1256'
ht-degree: 3%
---

# Instalar e configurar o GitLab para Edge Delivery Services

Para publicar conteúdo do Experience Manager Guides no Edge Delivery Services (EDS) usando o GitLab, conecte um repositório do GitLab ao seu site EDS através do recurso *Traga seu próprio Git* (BYOG) da Cloud Manager. Este artigo lista as etapas em sequência. Para obter detalhes sobre cada etapa, siga a documentação vinculada.

## Como funciona

- Um **repositório GitHub** cria o site de EDS por meio do aplicativo AEM Code Sync.
- Um **repositório do GitLab** armazena o conteúdo publicado do Experience Manager Guides.
- **Cloud Manager** vincula os dois recebendo eventos de push do GitLab (webhook) e sincronizando-os com o site EDS.

## Pré-requisitos

- Acesso ao GitHub e GitLab (GitLab.com ou auto-hospedado) para criar repositórios e tokens.
- Acesso ao Cloud Manager, com uma função que permite adicionar repositórios (Gerente de implantação ou Proprietário da empresa).
- Função de Administrador do sistema ou Desenvolvedor de API na organização da Adobe para criar a integração de API do Cloud Manager.
- Uma organização `aem.live` registrada no serviço de configuração. Saiba mais em [Configuração do serviço](https://www.aem.live/docs/config-service-setup).

## Sequência de configuração

1. [Criar o site EDS usando GitHub](#1-create-the-eds-site-using-github)
2. [Criar o repositório do GitLab](#2-create-the-gitlab-repository)
3. [Configurar o URL do ponto de montagem](#3-configure-the-mountpoint-url)
4. [Criar tokens de acesso do GitLab](#4-create-gitlab-access-tokens)
5. [Adicionar o repositório GitLab ao Cloud Manager](#5-add-the-gitlab-repository-to-cloud-manager)
6. [Gerar uma chave de API do Cloud Manager](#6-generate-a-cloud-manager-api-key)
7. [Configurar o webhook do GitLab](#7-configure-the-gitlab-webhook)
8. [Adicionar o site de EDS ao Cloud Manager](#8-add-the-eds-site-to-cloud-manager)
9. [Conecte o repositório usando o Bring Your Own Git (Traga seu próprio Git)](#9-connect-the-repository-using-bring-your-own-git)
10. [Configurar o site de EDS para usar o Cloud Manager](#10-configure-the-eds-site-to-use-cloud-manager)
11. [Sincronizar e verificar](#11-sync-and-verify)
12. [Publicar a partir do Experience Manager Guides](#12-publish-from-experience-manager-guides)

### &#x200B;1. Criar o site EDS usando GitHub

Crie um repositório GitHub na matriz do AEM Guides e instale o aplicativo AEM Code Sync nele. Salve o **Live URL** (`https://<branch>--<github-repo>--<github-username>.aem.live`) gerado para mais tarde.

Para etapas, exiba [Criar um repositório GitHub para EDS](./configure-eds.md#create-a-github-repository-for-eds) e [Conectar GitHub à Adobe pela Sincronização de Código AEM](./configure-eds.md#connect-github-to-adobe-via-aem-code-sync).

>[!IMPORTANT]
>
> Não crie o site EDS usando a opção de um clique no Cloud Manager. Os sites criados dessa maneira não fornecem as permissões de administrador necessárias para as etapas posteriores. Saiba mais em [Preparar seu site do Edge Delivery Services](https://www.aem.live/developer/byo-git#1.-prepare-your-edge-delivery-services-site).

### &#x200B;2. Criar o repositório do GitLab

Crie um repositório GitLab separado (por exemplo, `my-eds-gitlab`) do mesmo modelo do AEM Guides. O Experience Manager Guides publica a saída gerada nesse repositório. O EDS espera uma ramificação `main`.

Para criar o repositório, crie um projeto em branco e envie o conteúdo de [aem-guides-boilerplate](https://github.com/adobe/aem-guides-boilerplate) para ele ou importe o boilerplate para um novo projeto. Para ver as etapas, consulte [Criar um projeto](https://docs.gitlab.com/user/project/) e [Importar seu projeto do GitHub para o GitLab](https://docs.gitlab.com/user/project/import/github/) na documentação do GitLab.

### &#x200B;3. Configurar o URL do ponto de montagem

No repositório GitHub, atualize `fstab.yaml` para que a fonte de conteúdo aponte para o repositório GitLab e confirme a alteração para `main`.

```text
https://<worker URL>/gitlab/<git acc domain>/<git username>/<git repo>/main/docs
```

| Parâmetro | Descrição |
|---|---|
| `<worker URL>` | URL do nó de trabalho fornecido pelo Adobe. |
| `<git acc domain>` | Domínio do GitLab, como `gitlab.com`, ou seu domínio auto-hospedado. |
| `<git username>` | Seu nome de usuário do GitLab. |
| `<git repo>` | Nome do repositório GitLab. |
| `main` / `docs` | Pasta raiz e ramificação. Padrões para o Experience Manager Guides. |

### &#x200B;4. Criar tokens de acesso do GitLab

Crie o(s) token(s) de acesso necessário(s) para:

- **Cloud Manager**, para validar e acessar o repositório. Saiba mais em [Adicionar repositórios externos no Cloud Manager](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).
- **perfil de publicação do Experience Manager Guides**, para confirmar a saída publicada. Crie um token de acesso de projeto GitLab com a função **Desenvolvedor** e o escopo `api`. Saiba mais na [documentação do GitLab](https://docs.gitlab.com/ee/user/project/settings/project_access_tokens.html).

>[!NOTE]
>
> Renove os tokens antes que eles expirem. A publicação falhará se o token no perfil de publicação tiver expirado. Para atualizar um token usado pelo Cloud Manager, exiba [Gerenciar tokens de acesso para repositórios externos](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-manager/content/managing-code/manage-access-tokens).

### &#x200B;5. Adicionar o repositório GitLab ao Cloud Manager

No Cloud Manager, vá para **Repositórios** > **Adicionar Repositório**, selecione **Repositório Privado** e valide a propriedade usando o token de acesso. Aguarde até que o status do repositório seja **Pronto**. A opção BYOG só estará disponível depois que pelo menos um repositório externo estiver Pronto.

Para etapas, exiba [Adicionar repositórios externos na Cloud Manager](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).

### &#x200B;6. Gerar uma chave de API do Cloud Manager

Crie uma integração de API na Adobe Developer Console (**Cloud Manager** API, **OAuth Server-to-Server**) e copie a **ID do Cliente (Chave de API)**.

Para etapas, consulte [Criação de um projeto de integração de API](https://developer.adobe.com/experience-cloud/cloud-manager/guides/getting-started/create-api-integration).

### &#x200B;7. Configurar o webhook do GitLab

No Cloud Manager, selecione **Config Webhook** para o repositório e copie a **URL do Webhook** e o **Secret**. Anexe a chave de API à URL (`<webhook URL>&api-key=<CLIENT_ID>`). No GitLab, vá para **Configurações** > **Webhooks**, adicione a URL e o segredo, selecione a ramificação `main` e habilite **Eventos de push**.

Para obter detalhes, exiba [Configurar o repositório externo no Cloud Manager](https://www.aem.live/developer/byo-git#2.-configure-your-external-repository-in-cloud-manager).

### &#x200B;8. Adicionar o site de EDS ao Cloud Manager

No Cloud Manager, vá para **Edge Delivery** > **Adicionar site do Edge Delivery** e insira a URL ativa salva na etapa 1. Conclua a validação de propriedade.

Para etapas, exiba [Adicionar um site do Edge Delivery](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/edge-delivery-sites/add-edge-delivery-site).

### &#x200B;9. Conecte o repositório usando o Bring Your Own Git (Traga seu próprio Git)

No site de EDS no Cloud Manager, selecione **Traga seu próprio Git (BYOG)**, escolha o repositório do GitLab e confirme. Copie e armazene com segurança o segredo gerado. Ele é exibido apenas uma vez e um novo segredo é gerado se você reconfigurar o site.

Para obter detalhes, consulte [Configurar seu site do Edge Delivery no Cloud Manager](https://www.aem.live/developer/byo-git#3.-configure-your-edge-delivery-site-in-cloud-manager).

### &#x200B;10. Configurar o site de EDS para usar o Cloud Manager

Defina a fonte de código do site EDS para o repositório do Cloud Manager, usando a **ID do Programa** (`/program/<PROGRAM_ID>/`) e a **ID do Repositório** (`/repo/<REPO_ID>/`) da URL do webhook. Em seguida, crie um segredo com o nome exato `cm-byog` com o segredo da etapa 9.

Para as chamadas da API de Administração, exiba [Configurar seu site do AEM para usar o Cloud Manager](https://www.aem.live/developer/byo-git#4.-configure-your-aem-site-to-use-cloud-manager).

### &#x200B;11. Sincronizar e verificar

No Cloud Manager, selecione **Sincronizar Código** no menu do site e escolha a ramificação `main`. Em seguida, abra `https://main--<site>--<org>.aem.page` para verificar o site.

Para obter detalhes, exiba [Acionar sua primeira sincronização](https://www.aem.live/developer/byo-git#5.-trigger-your-first-sync) e [Verificar seu site do AEM](https://www.aem.live/developer/byo-git#6.-verify-your-aem-site).

### &#x200B;12. Publicar a partir do Experience Manager Guides

Crie um perfil de publicação de EDS com **tipo de conta Git** definido como **GitLab**, usando o token de acesso ao projeto da etapa 4. Em seguida, selecione esse perfil em uma predefinição de saída do EDS e gere a saída. A saída é confirmada na pasta `docs` do repositório GitLab.

Para etapas, exiba [Criar o perfil de publicação do EDS](./configure-eds.md#create-the-eds-publish-profile-for-github-or-gitlab) e [Criar uma predefinição de Saída para o EDS e gerar a saída](./configure-eds.md#create-an-output-preset-for-eds-and-generate-output).

## Resolução de problemas

- **O site mostra conteúdo antigo após um envio por push:** Verifique se o webhook está entregando eventos para o Cloud Manager e verifique o status do trabalho de sincronização mais recente.
- **Erro de sincronização `Unable to fetch hlxignore: 401`:** O segredo `cm-byog` está incorreto. Recrie-o com o segredo da etapa 9.
- **Repositório vinculado a outro site:** Um repositório do Cloud Manager pode ser vinculado somente a um site de cada vez. Para compartilhar um repositório entre sites, use [Respostas](https://www.aem.live/docs/repoless).

Para obter mais detalhes, consulte [Solução de problemas em Traga seu próprio Git](https://www.aem.live/developer/byo-git#troubleshooting).
