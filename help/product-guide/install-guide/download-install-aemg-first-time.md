---
title: Baixe e instale o AEM Guides pela primeira vez
description: Saiba como baixar e instalar o AEM Guides pela primeira vez
exl-id: 830a4381-303c-419c-b87f-9563352a7eeb
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: dbcc625220c9ad1fa60942b2f43c38d3d6778541
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# Baixe e instale o AEM Guides pela primeira vez {#id213BCL00KEV}

Execute as seguintes etapas para baixar e instalar o AEM Guides pela primeira vez em um computador:

>[!IMPORTANT]
>
> Se você quiser usar o Livefyre juntamente com o AEM Guides, instale as versões do Livefyre anteriores à 3.0 antes de instalar o AEM Guides. Se você estiver usando o Livefyre versão 3.0 ou superior, essa restrição não existe.

1. Baixe o AEM Guides do [Portal de Distribuição de Software do Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).

   >[!NOTE]
   >
   >Antes de instalar o Experience Manager Guides, verifique se o sistema atende aos [requisitos técnicos](../install-guide/download-install-technical-requirements.md).

1. Faça logon na instância do AEM e navegue até o Gerenciador de pacotes da CRX. O URL padrão para acessar o gerenciador de pacotes é:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   O Gerenciador de pacotes gerencia os pacotes na sua instalação local do AEM. Para obter mais informações sobre como trabalhar com o Gerenciador de Pacotes, consulte [Como trabalhar com pacotes](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/package-manager.html) na documentação do AEM.

   ![](assets/package-manager.png){width="650" align="left"}

1. Para carregar o pacote do AEM Guides, clique em **Carregar Pacote**.

1. Na caixa de diálogo Carregar pacote, navegue até o arquivo AEM Guides que você baixou na Etapa 1 e clique em **OK**.

   O pacote é carregado para a instância do AEM.

1. Para instalar o pacote, clique em **Instalar**.

   ![](assets/install-package.png){width="650" align="left"}

1. Na caixa de diálogo Instalar Pacote, clique em **Instalar**.

1. Para começar a usar o AEM Guides, clique no botão Página Inicial ![](assets/home-button.png) no canto superior esquerdo do Gerenciador de Pacotes do CRX.


>[!NOTE]
>
> Execute o procedimento de instalação em todas as instâncias de servidores AEM em sua configuração.

**Tópico pai:**&#x200B;[ Baixar e instalar](download-install.md)
