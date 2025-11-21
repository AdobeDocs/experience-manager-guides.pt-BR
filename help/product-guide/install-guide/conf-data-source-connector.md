---
title: Configurar um conector de fonte de dados
description: Saiba como configurar um conector de fonte de dados
exl-id: bd1188e1-0e1d-4e70-928a-10251c3d529d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Configurar um conector de fonte de dados

O AEM Guides fornece conectores prontos para uso para bancos de dados JIRA e SQL (MySQL, PostgreSQL, SQL Server, SQLite). Você também pode adicionar outros conectores estendendo as interfaces padrão. A configuração a seguir ajuda a adicionar facilmente as várias fontes de dados. Depois de adicionado, você pode exibir as fontes de dados no Editor da Web.

Execute as seguintes etapas para configurar um conector de origem de dados e, em seguida, usá-lo no Editor da Web:

## Configurar um conector

Você pode configurar um conector pronto para uso carregando um arquivo JSON. Você pode usar os seguintes arquivos de configuração de exemplo para configurar conectores para bancos de dados Jira e SQL (MySQL, PostgreSQL, SQL Server, SQLite).

Um exemplo de arquivo de configuração para a autenticação básica do Jira com nome de usuário e senha:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "username": "jirausername",
            "password": "jirapassword",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

Por exemplo, salve como `jira.json`.

Um exemplo de arquivo de configuração para a autenticação básica do Jira com token:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "token": "jiraauthtoken",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

Por exemplo, salve como `jira.json`.

Um exemplo de arquivo de configuração para a autenticação básica do Jira com o token com a palavra-chave &quot;Básico&quot; presente nele:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "token": "Basic jiraauthtoken",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

Por exemplo, salve como `jira.json`.

Um exemplo de arquivo de configuração para a autenticação básica do MySql:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MySqlConnector",
    "configName": "MySQL",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "com.mysql.jdbc.Driver",
            "connectionString": "jdbc:mysql://host.corp.adobe.com:3306/plm"
        }
    }
}
```

Por exemplo, salve como `mysql.json`.

Um exemplo de arquivo de configuração para a autenticação básica do PostgreSQL:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.PostgreSqlConnector",
    "configName": "PostgreSQL",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "org.postgresql.Driver",
            "connectionString": "jdbc:postgresql://host:port/database"
        }
    }
}
```

Por exemplo, salve como `postgres.json`.

Um exemplo de arquivo de instalação para a autenticação básica do MS SQL Server:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MsSqlServerConnector",
    "configName": "MSSQLServer",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
            "connectionString": "jdbc:sqlserver://10.10.10.10\\SQLEXPRESS01:1433;database=TutorialDB;encrypt=false;trustServerCertificate=true"
        }
    }
}
```

Por exemplo, salve como `mssqlserver.json`.

Um exemplo de arquivo de configuração para a autenticação básica do SQLite:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.SqliteConnector",
    "configName": "SQLiteServer",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "org.sqlite.JDBC",
            "connectionString": "jdbc:sqlite:sample.db"
        }
    }
}
```

Por exemplo, salve como `sqqlite.json`.

### Personalizar uma configuração de conector

O AEM Guides permite personalizar alguns valores no arquivo de configuração para atender às necessidades do usuário.

| Nome de propriedade | Descrição |
|---|---|
| configName | O usuário pode especificar um nome de configuração para ajudar a identificar o conector |
| templateFolders | Lista de pastas de onde os modelos serão buscados |

Outros campos são personalizados com base na classe de configuração selecionada para executar o Conector.

## Faça upload do arquivo para um local no AEM

Faça upload do arquivo para algum local no AEM Assets.

Por exemplo, `/content/dam/jira.json`

## Criar configuração usando REST API

Você pode registrar a configuração usando a API REST. Para obter mais detalhes, consulte a seção *REST API para registrar um conector de fonte de dados* na Referência de API para Adobe Experience Manager Guides.

Após configurar a fonte de dados, o conector é listado no painel Fontes de dados do Editor da Web. Em seguida, você pode se conectar à fonte de dados e inserir um trecho de conteúdo em seus tópicos. Para obter mais detalhes, exiba [Inserir um trecho de conteúdo da sua fonte de dados](../user-guide/web-editor-content-snippet.md).
