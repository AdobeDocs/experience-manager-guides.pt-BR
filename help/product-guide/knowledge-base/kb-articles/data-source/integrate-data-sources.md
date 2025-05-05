---
title: Arquitetura da integração de fontes de dados externas no AEM Guides
description: Saiba mais sobre a arquitetura da Integração de fontes de dados externas no AEM Guides.
source-git-commit: b0cf652023770eda24ea27ff105ed6dc2cdd1f08
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# Integração de fontes de dados externas

Os dados de sistemas externos podem ser facilmente integrados à instância do Experience Manager Guides. A conexão com fontes de dados externas pode melhorar significativamente a funcionalidade e a usabilidade do sistema de gerenciamento de conteúdo.


Você pode conectar e buscar dados de fontes externas com eficiência usando a integração de dados. Com esse recurso, você não precisa depender da equipe de TI para obter os dados e, em seguida, copiá-los e colá-los manualmente ou atualizar constantemente as alterações no sistema externo.

Esse recurso garante a sincronização com a origem original e permite atualizações harmoniosas na documentação sem depender de operações manuais de copiar e colar. Também ajuda a manter a consistência dos dados entre o Experience Manager Guides e a fonte de dados externa.

Além disso, depois de buscar o conteúdo de fontes de dados externas, você pode criá-lo no formato DITA e também reutilizar o conteúdo integrado.


## Estrutura de integração da fonte de dados

A estrutura de integração de uma fonte de dados abrange principalmente dois componentes principais: as fontes de dados externas e sua integração na instância do Experience Manager Guides.

### Fontes de dados externas

Estas são algumas das fontes de dados que você pode conectar pelo Experience Manager Guides:

- Bancos de Dados Relacionais (RDBMS)
   - PostgreSQL, MySQL, Microsoft SQL Server, MariaDB e SQLite
- Bancos de Dados Não Relacionais
   - MongoDB, Apache Cassandra, Apache CouchDB e Redis
- Gerenciamento de informações do produto (PIM) / Gerenciamento do ciclo de vida do produto (PLM)
   - Pimcore, Salsify, Akeneo e Informatica
- Sistemas de gerenciamento de produtos
   - JIRA e placas DevOps do Microsoft Azure (ADO)
- Sistemas OLAP (Online Analytical Processing, processamento analítico online) e Analytics

### Integração no Experience Manager Guides



Com o uso de um conector autenticado, os dados são transferidos de um sistema externo e geram dados no Experience Manager Guides.
![Arquitetura](assets/konnect-architecture.png)


### Integração no Experience Manager Guides

Execute as seguintes etapas para integrar o conteúdo ao Experience Manager Guides:

1. **Configurar o conector de fonte de dados**
   - O conector da fonte de dados serve como interface para estabelecer conectividade com as fontes de dados externas. Você deve configurar o conector para estabelecer a conexão e incluir os métodos de autenticação, como `Basic Auth` ou `API key Auth`. Todos os detalhes de configuração, incluindo informações criptografadas, são armazenados com segurança no Adobe Experience Manager.
   - A camada do conector é projetada para ser extensível, permitindo que você crie suas implementações para conexão com vários sistemas que não são fornecidos prontos para uso pela Experience Manager Guides.

     ![Camada de conector](assets/data-source-connector-layer.jpg)
   >[!NOTE]
   >
   > Acesse o módulo de definição do Konnect e implemente a interface do Conector para criar um conector personalizado. Saiba mais sobre como [configurar conectores de fonte de dados personalizados](./conf-custom-data-source-connector.md).

1. **Personalizar os modelos do Velocity**

   - O Experience Manager Guides é compatível com o Velocity (https://velocity.apache.org/), um mecanismo de modelo altamente robusto para transformar os dados de arquivos JSON em conteúdo DITA. A Velocity oferece flexibilidade para navegar pelas estruturas JSON com qualquer nível de aninhamento.
   - O exemplo a seguir mostra como integrar modelos do velocity e dados obtidos do Jira para gerar tabelas ou listas ordenadas facilmente.
      - Resposta do Jira

        ```
        {
            "expand": "schema,names",
            "total": 5,
            "hostname": "https://jira.corp.adobe.com",
            "maxResults": "200",
            "issues": [
                {
                    "key": "DXML-12756",
                    "fields": {
                        "description": "Implement the snippet generator in External Data Source integration",
                        "summary": "Implement the snippet generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12755",
                    "fields": {
                        "description": "Implement the topic generator in External Data Source integration",
                        "summary": "Implement the topic generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12745",
                    "fields": {
                        "description": "Implement the ability to register a new connector",
                        "summary": "Implement the ability to register a new connector"
                    }
                }
            ],
            "startAt": 0
        }
        ```

      - Modelos

        ![Mecanismo de modelo](assets/data-source-TemplatingEngine.png){width="800" align="left"}
      - Dados gerados a partir da mesma fonte de dados, mas com modelos diferentes

        ![Dados Gerados](assets/data-source-templates-topics.png){width="800" align="left"}

1. **Gerar conteúdo usando os modelos**
   - Você pode gerar o conteúdo a partir dos modelos criados.
   - Você pode gerar vários tipos de conteúdo:
      - Trecho: este é um conteúdo utilizável único. Você pode gerar os dados do conector no modelo definido e, em seguida, incorporá-los na tag desejável.
      - Tópico DITA: Gere vários tópicos para usar como estão no conteúdo ou podem ser reutilizados como um *Componente Reutilizável*.
      - Tópico DITA + Mapa: Você também pode gerar um mapa completo com o tópico e, em seguida, usar os dados para publicação direta ou usá-los como um *Componente reutilizável* em outros dados.


1. **Publish o conteúdo integrado**
   - A publicação é o recurso OOTB do Experience Manager Guides e você pode publicar diretamente todos os dados gerados a partir do sistema externo como saída do PDF ou do site AEM.

>[!MORELIKETHIS]
>
> Os documentos a seguir fornecem mais detalhes sobre a configuração dos conectores e o uso deles em sua instância.
> - [Configurar um conector de fonte de dados](../../../install-guide/conf-data-source-connector-tools.md)
> - [Gerar conteúdo usando trechos ou tópicos](../../../user-guide/web-editor-content-snippet.md)