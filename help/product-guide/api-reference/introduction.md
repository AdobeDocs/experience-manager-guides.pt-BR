---
title: Introdução
description: Introdução ao Guia de referência de API do AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/dNO8nZusaPCor506Q-2drrcJGf68mx-Hxo4uaT-cDtM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: f3645292-50bd-4f4a-ac6a-29dcecdf8abe
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: a13143053c75ab65cbcd20a52c8ca3fb953edecf
workflow-type: tm+mt
source-wordcount: 686
ht-degree: 0%

---

# Introdução {#id1761C0007W7}

O Adobe Experience Manager Guides \(mais tarde conhecido como *AEM Guides*\) é uma solução corporativa completa que permite que o Adobe Experience Manager \(AEM\) tenha recursos de CCMS (solução de gerenciamento de conteúdo de componentes) para a criação e entrega de conteúdo baseado em DITA. Os clientes podem acessar os fluxos de trabalho do AEM Guides de forma programática usando as APIs do AEM Guides para integrá-los a outros aplicativos corporativos. Essas APIs também podem ser usadas pelos parceiros da Adobe para aprimorar a proposta de valor do AEM Guides, estendendo sua funcionalidade ou integrando-a a outros aplicativos ou serviços.

## APIs do AEM Guides

As APIs do AEM Guides estão disponíveis em dois formatos:

- [APIs baseadas em Java](#java-based-apis)
- [APIs baseadas em REST](#rest-based-apis)

Essas APIs expõem as principais funções do AEM Guides para os desenvolvedores de aplicativos. Usando essas funções, os desenvolvedores podem criar seus próprios plug-ins para estender os workflows prontos para uso. As APIs estão disponíveis para gerenciar saídas para conteúdo DITA, trabalhar com mapas DITA, adicionar atributos condicionais a perfis em nível de pasta e converter documentos do HTML e do Words para o formato DITA.


### APIs baseadas em Java

Você pode usar APIs baseadas em Java disponíveis no Experience Manager Guides para criar plug-ins personalizados e estender workflows prontos para uso.

**Configurar o SDK a partir do repositório central Maven para o AEM Guides as a Cloud Service**

>[!INFO]
>
>Consulte [![javadoc](./images/javadoc-cs-icon.svg)](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) para obter a documentação mais recente e detalhada sobre como usar a API baseada em Java para o Experience Manager Guides as a Cloud Service.

Para configurar e usar os JARs de API de serviço do repositório Maven em seus projetos, adicione a API SDK como uma dependência de projeto no arquivo `pom.xml` do projeto, como mostrado abaixo.

```XML
<dependency>
<groupId>com.adobe.aem</groupId>
<artifactId>aem-dox-sdk-api</artifactId>
<version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Use a mesma versão do JAR da API que o pacote do AEM Guides instalado no servidor.

**Configurar e usar o JAR da API do repositório central Maven (no local)**

>[!INFO]
>
>Consulte [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) para obter a documentação mais recente e detalhada sobre como usar a API baseada em Java para a instalação do Experience Manager Guides no local.

Para configurar e usar os JARs da API de serviço para implantações locais, adicione o JAR da API de serviço como uma dependência do projeto no arquivo `pom.xml` do projeto, conforme mostrado abaixo:

```XML
<dependency>
<groupId>com.adobe.aem</groupId>
<artifactId>aem-guides-sdk-api</artifactId>
<version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Use a mesma versão do JAR da API que o pacote do AEM Guides instalado no servidor.


**Configure e use o JAR da API do repositório Maven público da AEM Guides (no local)**

>[!NOTE]
>
> O repositório público do AEM Guides Maven será descontinuado após a versão 5.3.0 do Experience Manager Guides. O JAR da API só estará disponível no repositório central Maven posteriormente.

Execute as seguintes etapas para usar os JARs da API de serviço do repositório Maven público:

1. Configure o repositório Maven público do AEM Guides no seu arquivo `pom.xml` ou `settings.xml`, conforme mostrado abaixo:

   ```XML
   <repository>
       <id>fmdita-public</id>
       <name>fmdita-public</name>
       <url>https://repo.aem-guides.com/repository/fmdita-public</url>
    </repository>
   ```

1. Depois que o repositório for configurado, adicione o JAR da API de serviço como uma dependência de projeto no arquivo `pom.xml` do projeto.

   ```XML
   <dependency>
       <groupId>com.adobe.fmdita</groupId>
       <artifactId>api</artifactId>
       <version>${RELEASE}</version>
   </dependency>
   ```

   >[!NOTE]
   >
   > Use a mesma versão do JAR da API que o pacote do AEM Guides que você instalou no servidor.

Depois que o JAR da API de serviço for adicionado como uma dependência de projeto no arquivo `pom.xml` do projeto, você poderá criar e usar APIs Java da AEM Guides em seu projeto.


### APIs baseadas em REST

O Experience Manager Guides fornece um conjunto abrangente de APIs baseadas em REST que permitem aos desenvolvedores acessar e interagir com as funcionalidades principais por HTTP.

Essas APIs são ideais para:

- Integração do Experience Manager Guides com outros sistemas corporativos
- Automatização de publicação e fluxos de trabalho de revisão
- Criação de aplicativos e extensões personalizados

Para obter informações detalhadas sobre o uso da API, parâmetros e solicitações de exemplo, exiba os tópicos relevantes na seção **Referência da API** da documentação da Experience Manager Guides.

>[!NOTE]
>
> Você também pode consultar a **documentação do Swagger** para as APIs REST disponíveis publicamente em `https://<aem-author-url>/libs/fmdita/clientlibs/api-docs/index.html`. Atualmente, somente APIs relacionadas ao Assets, Linha de base e Relatórios estão disponíveis na documentação do Swagger.


## Recursos adicionais

Veja a seguir uma lista de outros recursos úteis do AEM Guides, que estão disponíveis na página [Aprendizagem e Suporte](https://helpx.adobe.com/br/support/xml-documentation-for-experience-manager.html):

- Guia do usuário
- Guia de instalação e configuração
- Guia de início rápido
- [Página de Arquivamento da Ajuda](https://helpx.adobe.com/br/xml-documentation-for-experience-manager/archive.html) \(acesse a documentação de versão mais antiga\)
