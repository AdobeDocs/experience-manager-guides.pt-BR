---
title: Introdução
description: Introdução ao Guia de referência de API para guias do AEM
role: Developer
feature: Introduction
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
source-git-commit: 26d0b3fd6b6d34fb2a86417179c8be672d40ad86
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 0%

---

# Introdução {#id1761C0007W7}

Guias do Adobe Experience Manager \(mais tarde referidos como *Guias do AEM*\) é uma solução corporativa completa que permite que o Adobe Experience Manager \(AEM\) tenha recursos de solução de gerenciamento de conteúdo de componentes \(CCMS\) para a criação e entrega de conteúdo baseado em DITA. Os clientes podem acessar os fluxos de trabalho dos Guias AEM de forma programática usando as APIs dos Guias AEM para integrá-los a outros aplicativos corporativos. Essas APIs também podem ser usadas por parceiros de Adobe para aprimorar a proposta de valor dos Guias de AEM, estendendo sua funcionalidade ou integrando-a a outros aplicativos ou serviços.

## APIs de guias de AEM

As APIs dos Guias do AEM estão disponíveis em dois formatos: HTTP e Java. Essas APIs expõem as principais funções dos Guias do AEM para os desenvolvedores de aplicativos. Usando essas funções, os desenvolvedores podem criar seus próprios plug-ins para estender os workflows prontos para uso. As APIs estão disponíveis para gerenciar saídas para conteúdo DITA, trabalhar com mapas DITA, adicionar atributos condicionais a perfis em nível de pasta e converter documentos HTML e Words para o formato DITA.

## Instalar os JARs no repositório local do Apache Maven {#install-jar-local}

Para poder usar os arquivos JAR expostos pelos Guias AEM, é necessário instalá-los no repositório Apache Maven local. Execute as seguintes etapas para instalar os JARs no repositório Maven do local:

1. Extraia o conteúdo do arquivo \(.zip\) do pacote de Guias do AEM no sistema local.

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

4. \(*Opcional*\) Instale a dependência no repositório local do projeto Maven. Você pode fazer isso criando uma pasta em seu projeto Maven e executando o `mvn install` comando fornecido na etapa anterior com o seguinte parâmetro adicional:

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   Em seguida, para expor a pasta do repositório local do projeto para o processo de compilação Maven, adicione um `repository` elemento no arquivo pom.xml principal como mostrado abaixo:

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

1. Para usar o JAR da API de serviço em um projeto, configure o repositório Maven público dos Guias do AEM no arquivo pom.xml.
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
   > Use a mesma versão do JAR da API que o pacote AEM Guides que você instalou no servidor.

4. Configure a dependência do Maven conforme mostrado abaixo:

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


Depois que o JAR da API de serviço for adicionado como uma dependência de projeto no arquivo pom.xml do projeto, você poderá criar e usar APIs Java dos Guias de AEM no seu projeto.

## Uso do JAR da API do repositório central Maven para o AEM Guides as a Cloud Service

Para Guias do AEM as a Cloud Service, o JAR da API foi implantado no Maven Central. Você pode usar o JAR da API sem qualquer configuração.

>[!NOTE]
>
> A convenção de nomenclatura do jar de API foi atualizada de acordo com a convenção de nomenclatura dos complementos em nuvem.

Para usar o JAR da API, é necessário adicionar a dependência ao pom.xml do projeto, conforme mostrado abaixo:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-guides-sdk-api</artifactId>
   <version>2022.5</version>
</dependency>
```

>[!NOTE]
>
> Como os pacotes no JAR de API ainda são os mesmos, nenhuma alteração de código é necessária para usar esse JAR de API nos projetos de nuvem existentes.

## Recursos adicionais

Veja a seguir uma lista de outros recursos úteis dos Guias do AEM, que estão disponíveis no [Aprendizagem e suporte](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) página:

- Guia do usuário
- Guia de instalação e configuração
- Guia de início rápido
- [Página de arquivamento da ajuda](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(acesse a documentação de versão mais antiga\)
