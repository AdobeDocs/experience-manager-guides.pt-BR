---
title: Introdução
description: Introdução ao Guia de referência de API do AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: 00a926e82f7d848e0c8041de758f20e79758b01b
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%

---

# Introdução {#id1761C0007W7}

O Adobe Experience Manager Guides \(mais tarde conhecido como *AEM Guides*\) é uma solução corporativa completa que permite que o Adobe Experience Manager \(AEM\) tenha recursos de CCMS (solução de gerenciamento de conteúdo de componentes) para a criação e entrega de conteúdo baseado em DITA. Os clientes podem acessar os fluxos de trabalho do AEM Guides de forma programática usando as APIs do AEM Guides para integrá-los a outros aplicativos corporativos. Essas APIs também podem ser usadas pelos parceiros da Adobe para aprimorar a proposta de valor do AEM Guides, estendendo sua funcionalidade ou integrando-a a outros aplicativos ou serviços.

## APIs do AEM Guides

As APIs do AEM Guides estão disponíveis em dois formatos: HTTP e Java. Essas APIs expõem as principais funções do AEM Guides para os desenvolvedores de aplicativos. Usando essas funções, os desenvolvedores podem criar seus próprios plug-ins para estender os workflows prontos para uso. As APIs estão disponíveis para gerenciar saídas para conteúdo DITA, trabalhar com mapas DITA, adicionar atributos condicionais a perfis em nível de pasta e converter documentos do HTML e do Words para o formato DITA.

## Instalar os JARs no repositório local do Apache Maven {#install-jar-local}

Para usar os arquivos JAR expostos pelo AEM Guides, é necessário instalá-los no repositório local do Apache Maven. Execute as seguintes etapas para instalar os JARs no repositório Maven do local:

1. Extraia o conteúdo do arquivo de pacote \(.zip\) do AEM Guides no sistema local.

2. No prompt de comando, navegue até a seguinte pasta no caminho do conteúdo extraído:

   ```
   \jcr_root\libs\fmdita\osgi-bundles\install
   ```

3. Execute o seguinte comando para instalar o pacote de API no repositório Maven local:

   ```
   mvn install:install-file -Dfile=api-X.x.jar -DgroupId=com.adobe.fmdita -DartifactId=api -Dversion=X.x -Dpackaging=jar**
   ```

   >[!NOTE]
   >
   > No comando acima, X.x deve ser substituído pelo número da versão real nos parâmetros Dfile e Dversion.

4. \(*Opcional*\) Instale a dependência no repositório do projeto Maven local. Você pode fazer isso criando uma pasta em seu projeto Maven e executando o comando `mvn install` fornecido na etapa anterior com o seguinte parâmetro adicional:

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   Em seguida, para expor a pasta do repositório local do projeto para o processo de compilação Maven, adicione um elemento `repository` no arquivo pom.xml pai, como mostrado abaixo:

   ```XML
   <repositories>
      <repository>
         <id>project-repository</id>
         <url>file://${project.basedir}/repository</url>
      </repository>
   </repositories>
   ```


Esse processo instala os JARs da API no repositório Maven local.

## Uso do JAR da API de serviço em um projeto Maven

Depois de instalar os JARs de API no repositório Maven local, execute as seguintes etapas para usar o JAR em seus projetos:

1. Adicione o JAR à sua base de código e confirme-o no repositório de base de código em uma pasta, como &quot;dependências&quot;. Observe que o nome da pasta depende da sua hierarquia de base de código.

2. Configure os arquivos pom.xml do projeto da seguinte maneira:

   Arquivo pom.xml do projeto pai:

   >[!IMPORTANT]
   >
   > No trecho de código a seguir, X.x deve ser substituído pelo número da versão real e pelo nome de arquivo do JAR da API. Essas informações serão as mesmas fornecidas na Etapa 3 do [processo de instalação](#install-jar-local).

   ```XML
   <plugin>
   
       <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
       <version>2.5.2</version>
   
       <configuration>
   
               <groupId>com.adobe.fmdita</groupId>
   
               <artifactId>api</artifactId>
   
               <version>X.x</version>
   
               <file>${basedir}/dependencies/fmdita/api-X.x.jar</file>
   
               <packaging>jar</packaging>
   
               <generatePom>true</generatePom>
   
       </configuration>
   
       <executions>
   
           <execution>
   
               <id>inst_fmdita</id>
   
                   <goals>
   
                       <goal>install-file</goal>
   
                   </goals>
   
                   <phase>clean</phase>
   
           </execution>
   
       </executions>
   </plugin>
   ```

   Arquivo pom.xml do módulo filho:

   ```XML
   <plugin>
      <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
      <configuration>
   
         <groupId>com.adobe.fmdita</groupId>
   
         <artifactId>api</artifactId>
   
         <version>3.6</version>
   
         <file>${basedir}/../dependencies/fmdita/api-3.6.jar</file>
   
         <packaging>jar</packaging>
   
         <generatePom>true</generatePom>
   
      </configuration>
   
      <executions>
   
         <execution>
   
            <id>inst_fmdita</id>
   
            <goals>
   
               <goal>install-file</goal>
   
            </goals>
   
            <phase>clean</phase>
   
         </execution>
   
      </executions>
   
   </plugin>
   ```


## Configurar e usar o JAR da API de serviço do repositório Maven público

Execute as seguintes etapas para configurar e usar os JARs da API de serviço do repositório Maven público em seus projetos:

1. Para usar o JAR da API de serviço em um projeto, configure o repositório Maven público do AEM Guides no arquivo pom.xml.
2. Configure o repositório Maven público no arquivo settings.xml do Maven da seguinte maneira:

   ```XML
   <repository>
      <id>fmdita-public</id>
      <name>fmdita-public</name>
      <url>https://repo.aem-guides.com/repository/fmdita-public</url>
   </repository>
   ```

3. Depois que o repositório for configurado, adicione o JAR da API de serviço como uma dependência de projeto no arquivo pom.xml do projeto.

   >[!NOTE]
   >
   > Use a mesma versão do JAR da API que o pacote do AEM Guides que você instalou no servidor.

4. Configure a dependência do Maven conforme mostrado abaixo:

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


Depois que o JAR da API de serviço é adicionado como uma dependência de projeto no arquivo pom.xml do projeto, você pode criar e usar APIs Java da AEM Guides em seu projeto.

## Uso do JAR da API do repositório central Maven para o AEM Guides as a Cloud Service

Para o AEM Guides as a Cloud Service, o JAR da API foi implantado no Maven Central. Você pode usar o JAR da API sem qualquer configuração.

>[!NOTE]
>
> A convenção de nomenclatura do jar de API foi atualizada de acordo com a convenção de nomenclatura dos complementos em nuvem.

Para usar o JAR da API, é necessário adicionar a dependência ao pom.xml do projeto, conforme mostrado abaixo:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-dox-sdk-api</artifactId>
   <version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Como os pacotes no JAR de API ainda são os mesmos, nenhuma alteração de código é necessária para usar esse JAR de API nos projetos de nuvem existentes.

### APIs baseadas em Java

Você pode usar APIs baseadas em Java disponíveis no Experience Manager Guides para criar plug-ins personalizados e estender workflows prontos para uso. Exiba [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obter a documentação mais recente e detalhada sobre como usar a API baseada em Java.



## Recursos adicionais

Veja a seguir uma lista de outros recursos úteis do AEM Guides, que estão disponíveis na página [Aprendizagem e Suporte](https://helpx.adobe.com/br/support/xml-documentation-for-experience-manager.html):

- Guia do usuário
- Guia de instalação e configuração
- Guia de início rápido
- [Página de Arquivamento da Ajuda](https://helpx.adobe.com/br/xml-documentation-for-experience-manager/archive.html) \(acesse a documentação de versão mais antiga\)
