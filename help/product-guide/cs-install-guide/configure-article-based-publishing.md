---
title: Instalar pacotes para publicação baseada em artigo
description: Saiba como instalar pacotes para publicação baseada em artigo
exl-id: d83fc1a9-0822-47f0-8099-22a74b9ced2a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/ZX3-rirhXTcufDkFQOF12vj3uh28gSfIpxFwlOQF-Yk
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: afb45297-4313-4f67-818e-bc0b03abe086id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 374
ht-degree: 0%

---

# Instalar pacotes para publicação baseada em artigo {#id21BNL02052Z}

O AEM Guides fornece um poderoso recurso de publicação baseado em artigos integrado ao Editor da Web. Com esse recurso, você pode publicar um ou mais tópicos simultaneamente. Depois de abrir um mapa no Editor de mapa, você pode navegar até a guia Saídas para criar uma predefinição e, em seguida, escolher um ou mais tópicos para gerar a saída. Você pode usar o recurso de publicação com base em artigo para gerar de forma incremental a saída de um ou mais tópicos ou publicar seu conteúdo em uma plataforma da base de conhecimento, artigo por artigo. Para obter mais detalhes, consulte *Publicação baseada em artigo da seção Editor da Web* no Guia do usuário.

Para criar um site do AEM para publicar a saída baseada em artigo, execute as seguintes etapas:

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

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
