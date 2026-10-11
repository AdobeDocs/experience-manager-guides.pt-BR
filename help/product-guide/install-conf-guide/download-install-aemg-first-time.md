---
title: Baixe e instale o AEM Guides pela primeira vez
description: Saiba como baixar e instalar o AEM Guides pela primeira vez
feature: Introduction, Installation
role: Admin
level: Experienced
exl-id: 1c4a93c2-e477-4466-8390-3fda21ead9ff
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: c5fd2af0-6cbb-4746-ab0d-40ecb093af12
    internal-label: Introduction
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 3%
---
# Baixe e instale o AEM Guides pela primeira vez {#id213BCL00KEV}

Execute as seguintes etapas para baixar e instalar o AEM Guides pela primeira vez:

>[!IMPORTANT]
>
> Se você quiser usar o Livefyre juntamente com o AEM Guides, instale as versões do Livefyre anteriores à 3.0 antes de instalar o AEM Guides. Se você estiver usando o Livefyre versão 3.0 ou superior, essa restrição não existe.

1. Baixe o AEM Guides do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).

   >[!NOTE]
   >
   >Antes de instalar o Experience Manager Guides, verifique se o sistema atende aos [requisitos técnicos](../install-conf-guide/aemg-technical-requirements.md).

1. Faça logon na instância do AEM e navegue até o Gerenciador de pacotes da CRX. O URL padrão para acessar o gerenciador de pacotes é:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   O Gerenciador de pacotes gerencia os pacotes na instalação local do AEM. Para obter mais informações sobre como trabalhar com o Gerenciador de Pacotes, consulte [Como trabalhar com pacotes](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/package-manager.html) na documentação do AEM.

   ![](assets/package-manager.png){width="650"}

1. Para carregar o pacote do AEM Guides, clique em **Carregar Pacote**.

1. Na caixa de diálogo Carregar pacote, navegue até o arquivo AEM Guides que você baixou na Etapa 1 e clique em **OK**.

   O pacote é carregado na instância do AEM.

1. Para instalar o pacote, clique em **Instalar**.

   ![](assets/install-package.png){width="650"}

1. Na caixa de diálogo Instalar Pacote, clique em **Instalar**.

1. Para começar a usar o AEM Guides, clique no botão Página Inicial ![](assets/home-button.png) no canto superior esquerdo do Gerenciador de Pacotes do CRX.


>[!NOTE]
>
> Execute o procedimento de instalação em todas as instâncias dos servidores AEM na sua configuração.
