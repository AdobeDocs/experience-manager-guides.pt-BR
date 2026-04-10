---
title: Instalar pacotes para publicação baseada em artigo
description: Saiba como instalar pacotes para publicação baseada em artigo
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Instalar pacotes para publicação baseada em artigo {#id21BNL02052Z}

O AEM Guides fornece um poderoso recurso de publicação baseado em artigos integrado ao Editor da Web. Com esse recurso, você pode publicar um ou mais tópicos simultaneamente. Depois de abrir um mapa no Editor de mapa, você pode navegar até a guia Saídas para criar uma predefinição e, em seguida, escolher um ou mais tópicos para gerar a saída. Você pode usar o recurso de publicação com base em artigo para gerar de forma incremental a saída de um ou mais tópicos ou publicar seu conteúdo em uma plataforma da base de conhecimento, artigo por artigo. Para obter mais detalhes, consulte *Publicação baseada em artigo da seção Editor da Web* no Guia do usuário.

As guias a seguir fornecem instruções para criar um site do AEM para publicar saída baseada em artigos com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Baixe o **Pacote de Conteúdo de Componentes do XML Documentation para Cloud Service** do seu [Portal de Distribuição de Software Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Abra o Gerenciador de pacotes do AEM. A URL padrão para acessar o gerenciador de pacotes é: `https://<hostname>/crx/packmgr/index.jsp`
1. Carregue o pacote de conteúdo dos componentes do XML Documentation para Cloud Service e instale-o.
1. Baixe o arquivo `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` do seu [Portal de Distribuição de Software Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Na Navegação Global, selecione **Sites**.
1. Na interface do usuário do Sites, clique no botão **Criar** no canto superior direito.
1. Selecione o **Site do modelo** na lista suspensa **Criar**.
1. Clique no botão **Importar** e selecione o `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` baixado no sistema. Depois que o modelo de site for importado, ele será listado na parte inferior.

   >[!NOTE]
   >
   > É necessário importar o arquivo ZIP somente pela primeira vez. Depois de importado, o modelo de site fica disponível na lista.

   Selecione o **modelo da Base de Dados de Conhecimento para a publicação baseada em Artigo** para criar o site do AEM e clique em **Avançar** no canto superior direito.

1. Insira o **Título do site** e o **Nome do site** e clique em **Criar** no canto superior direito. Um site do AEM é criado usando o modelo de site Tragopan. \(O site do Tragopan é um exemplo de site da AEM da base de conhecimento com modelos para uma categoria, seção e páginas de artigo.\)

   >[!NOTE]
   >
   > É possível criar vários sites do AEM usando o mesmo modelo.


Você pode usar o site do AEM para publicar seu artigo usando as predefinições de saída do Editor da Web.

>[!TAB No local]

Para habilitar a publicação baseada em artigos, baixe e instale os seguintes pacotes do Portal de distribuição de software da Adobe. Instale-os para criar um site Tragopan. \(O site do Tragopan é um exemplo de site da AEM da base de conhecimento com modelos para uma categoria, seção e páginas de artigo.\) Atualize o site do Tragopan para gerar a saída do site do AEM usando as predefinições de saída do Editor da Web.

- Modelo da knowledge base para publicação baseada em artigo
- Pacote de componentes para publicação baseada em artigo

>[!ENDTABS]


**Tópico pai:**[ Personalizar editor da Web](customize-overview.md)
