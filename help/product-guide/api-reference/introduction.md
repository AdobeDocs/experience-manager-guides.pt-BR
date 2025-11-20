---
title: Introdução
description: Introdução ao Guia de referência de API do AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: bf7838690d7632cd74fef0db3aaf7bdc48a50a2c
workflow-type: tm+mt
source-wordcount: '622'
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

    &quot;XML
    &lt;dependency>
    &lt;groupId>com.adobe.aem&lt;/groupId>
    &lt;artifactId>aem-dox-sdk-api&lt;/artifactId>
    &lt;version>${RELEASE}&lt;/version>
    &lt;/dependency>
    
    &quot;

>[!NOTE]
>
> Use a mesma versão do JAR da API que o pacote do AEM Guides instalado no servidor.

**Configurar e usar o JAR da API do repositório central Maven (no local)**

>[!INFO]
>
>Consulte [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) para obter a documentação mais recente e detalhada sobre como usar a API baseada em Java para a instalação do Experience Manager Guides no local.

Para configurar e usar os JARs da API de serviço para implantações locais, adicione o JAR da API de serviço como uma dependência do projeto no arquivo `pom.xml` do projeto, conforme mostrado abaixo:

    &quot;XML
    &lt;dependência>
    &lt;groupId>com.adobe.aem&lt;/groupId>
    &lt;artifactId>aem-guides-sdk-api&lt;/artifactId>
    &lt;versão>${RELEASE}&lt;/versão>
    &lt;/dependency>
    
    &quot;

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

## Recursos adicionais

Veja a seguir uma lista de outros recursos úteis do AEM Guides, que estão disponíveis na página [Aprendizagem e Suporte](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html):

- Guia do usuário
- Guia de instalação e configuração
- Guia de início rápido
- [Página de Arquivamento da Ajuda](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(acesse a documentação de versão mais antiga\)
