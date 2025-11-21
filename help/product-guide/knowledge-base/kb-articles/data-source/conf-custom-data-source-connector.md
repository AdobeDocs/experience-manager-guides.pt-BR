---
title: Configurar um conector personalizado para as fontes de dados
description: Saiba como configurar um conector personalizado para as fontes de dados.
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: ef7ab117-7541-4e89-9ba4-22254a17efc0
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1521'
ht-degree: 0%

---

# Configurar conectores de fonte de dados personalizados

O Experience Manager Guides permite personalizar os conectores de acordo com suas necessidades e usá-los com diferentes fontes de dados. Para personalizar um conector, você precisa implementar a interface do conector e suas funções importantes e, em seguida, configurar a interface. Você também pode fornecer os recursos junto com os conectores personalizados.


- [Personalizar um conector para o Experience Manager Guides](#customize-connector)
- [Implementar a interface do conector](#implement-interface)
- [Funções importantes](#important-functions)
- [Tipos de implementações de conector padrão](#default-connectors)
   - [Interface de configuração](#config-interface)
   - [Tipos de implementações de configurações padrão](#default-config-types)
   - [Implementações de configuração concretas](#concrete-config-implementation)
   - [Recursos adicionais](#resources)



## Personalizar um conector para o Experience Manager Guides {#customize-connector}

Você pode personalizar ou configurar um conector para uma fonte de dados usando as interfaces predefinidas e classes abstratas. O código-fonte inteiro está disponível em [https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions](https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions).


Consulte [![javadoc](https://javadoc.io/badge2/com.adobe.aem.addon.guides/konnect-definitions/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem.addon.guides/konnect-definitions) para obter as definições do konnect.

## Implementar a interface do conector {#implement-interface}

Execute as seguintes etapas para implementar a interface e suas funções de acordo com seus requisitos:

1. Defina uma maneira padronizada para os conectores se integrarem a um sistema, permitindo a execução de queries, a validação de conexões e a recuperação de metadados.
1. Facilite a integração da interface do usuário fornecendo os métodos padrão para configurar modelos, logotipos, consultas e outras configurações.
1. Verifique se os conectores foram devidamente validados e podem manipular erros (`KonnectException`) ao interagir com fontes de dados.

A interface atua como um blueprint para a implementação de vários tipos de conectores de dados, garantindo que os conectores atendam a quaisquer requisitos operacionais e de integração específicos em um ecossistema de software maior.

## Funções importantes {#important-functions}

Implemente as seguintes funções importantes:

| Método | Obrigatório | Descrição |
|---|---|---|
| getLogoUrl |  | <ul><li> Esse método retorna o URL usado como o logotipo do conector. <li> Por padrão, retorna uma string vazia, indicando que nenhum URL de logotipo é fornecido, a menos que seja substituído. <br><b> Observações Adicionais</b>: <br> <ul><li> Se você fornecer um URL de logotipo e um nome de classe de logotipo, o URL do logotipo será usado para exibi-lo na interface do usuário. <li> Se você especificar o URL do logotipo por meio das definições de configuração, ele substituirá o URL definido na implementação do método. |
| validateConnection | Sim | <ul><li> Use esse método para validar se o conector pode estabelecer uma conexão com sua fonte de dados. <li> Usa um objeto `ConfigDto` como parâmetro, que contém as definições de configuração, como credenciais de conexão e URLs de ponto de extremidade. <li> O método retornará true se a validação (teste de conexão) for bem-sucedida, indicando que o conector pode se conectar à sua fonte de dados. |
| executar | sim | <ul><li>Use esse método para executar uma única consulta para o conector, interagindo com uma fonte de dados. <li> Os conectores que oferecem suporte a essa operação lidam com a execução da consulta, analisam a resposta e a convertem em uma cadeia de caracteres JSON, se necessário. <li> Encapsule a consulta a ser executada neste método em um objeto `QueryInfoDto`, que contém detalhes como a cadeia de caracteres de consulta e parâmetros. <li> O método retorna uma string JSON que representa a resposta da execução da consulta. <br><b> Notas adicionais</b>: <li>As implementações desse método variam dependendo do conector específico e de sua interação com a fonte de dados. <li> Use o `KonnectException` para manipular quaisquer exceções ou erros que ocorram durante a execução ou conexão com a fonte de dados. |
| executeWithLimit | sim | <ul><li> Use este método para a mesma finalidade de `execute()`, mas com a funcionalidade adicional de aplicar uma consulta de limitação, normalmente para mostrar as visualizações nos componentes da interface do usuário. <li> Os conectores que oferecem suporte a essa operação lidam com a execução da consulta, analisam a resposta e a convertem em uma cadeia de caracteres JSON, se necessário. <li> Encapsule a consulta a ser executada neste método em um objeto `QueryInfoDto`, semelhante ao método anterior. <br><b> Notas adicionais</b>: <ul><li> `QueryResultDto` é uma classe personalizada ou objeto de transferência de dados que encapsula o resultado da execução da consulta, incluindo metadados sobre a consulta e seu status de execução. |
| getSampleQuery | | <ul><li>Esse método retorna uma amostra da sequência de consulta que pode ser exibida na interface, por exemplo, na caixa de diálogo em que os usuários podem inserir ou editar consultas. <li>Por padrão, retorna uma string vazia, indicando que nenhuma consulta de exemplo é fornecida, a menos que seja substituída. <br><b> Notas adicionais</b>: <ul> <li> Se você não definir uma consulta de exemplo e o método retornar uma string vazia, nenhuma consulta de exemplo será exibida na caixa de diálogo Inserir consulta da interface. |
| getTemplates | | <ul> <li> Esse método retorna uma lista de templates associados ao conector. <li> Por padrão, retorna uma lista vazia, indicando que nenhum template é fornecido, a menos que seja substituído. |
| getLogoClassName | | <ul> <li> Esse método retorna o nome da classe como o logotipo do conector. Por padrão, retorna uma string vazia, indicando que nenhum nome de classe de logotipo é fornecido, a menos que seja substituído. <br><b> Notas adicionais</b>: <ul><li> Se você fornecer um URL de logotipo e um nome de classe de logotipo, o URL do logotipo será usado para exibi-lo na interface do usuário. <li> Se você especificar o nome de classe do logotipo por meio das definições de configuração, ele substituirá o nome de classe definido na implementação do método. |
| habilitado | sim | <ul><li> Este método verifica se um `connector` está habilitado. <li> Por padrão, o método retorna false, o que significa que o conector não é habilitado, a menos que seja substituído por uma classe que esteja implementando esse método. |
| getDescription | | <ul><li>Use esse método para retornar uma string de descrição que pode ser exibida na interface. <li> Por padrão, retorna uma string vazia, indicando que nenhuma descrição é fornecida, a menos que seja substituída. |
| getAuthor | | <ul><li> Esse método fornece uma maneira de recuperar o nome do autor que criou ou é responsável pelo conector. <li> Normalmente, ajuda a identificar e reconhecer o criador ou mantenedor do conector em um sistema ou estrutura. |
| getName | sim | <ul><li>Esse método fornece uma maneira de recuperar o nome exclusivo atribuído a um conector. <li>O nome retornado é fundamental para identificar o conector em um contexto de interface do usuário (UI), especialmente se as configurações do conector não especificarem um nome explicitamente. <li>Esse nome é usado em vários componentes da interface do usuário para exibir ou gerenciar conectores de maneira simples. |
| getGroup | sim | <ul> <li>Este método fornece uma maneira de recuperar o nome do grupo associado a um conector. <li>Os nomes de grupo normalmente são usados para organizar ou categorizar conectores em grupos lógicos com base em sua funcionalidade, finalidade ou tipo. <li> Isso facilita o gerenciamento e a apresentação de conectores na interface do usuário de configuração. |
| getDefaultTemplatePath |  | <ul><li> Esse método retorna o caminho padrão para os templates associados a esse conector. <li> Por padrão, retorna uma string vazia, indicando que nenhum caminho padrão é definido, a menos que seja substituído. |
| getLogoSvg |  | <ul><li>Use este método para retornar a representação SVG do logotipo do conector. <li> Por padrão, ele retorna uma string vazia, indicando que nenhum dado do SVG é fornecido, a menos que seja substituído. |
| getMaxNoRowsForPreviewQuery | | <ul><li>Esse método retorna o número máximo de linhas consultadas ou exibidas na visualização da interface do usuário. <li> Por padrão, retorna o valor de DEFAULT_LIMIT_PREVIEW, uma constante que representa o limite padrão para linhas de visualização. |
| getConfigClass | sim | <ul><li>Este método fornece informações sobre as classes que implementam a interface Config e são compatíveis com esse conector. <li> Ele permite que o aplicativo ou a estrutura descubra e trabalhe dinamicamente com configurações compatíveis com o conector. |

## Tipos de implementações de conector padrão {#default-connectors}

A biblioteca *konnect-definitions* fornece implementações de conector abstrato e com funções predefinidas para executar consultas. Essas implementações de conectores atuam como modelos que podem ser estendidos diretamente e usados como estão. Se uma implementação personalizada for necessária, suas funções poderão ser substituídas.

Além de implementar os conectores padrão, você também pode implementar uma das seguintes classes abstratas padrão:

- Conector rest
- Conector de arquivo
- GraphQL Connector
- Conector SQL
- Conector NoSQL


Se um conector se encaixar em um desses tipos, estenda o conector para a classe base correspondente. Caso contrário, crie-o do zero implementando a interface do conector.

## Interface de configuração {#config-interface}

A interface do `Config` foi projetada para configurar uma fonte de dados com um método de autenticação específico, oferecendo controle preciso sobre como você cria a conexão.

A interface `Config` oferece flexibilidade na maneira como os detalhes de autenticação são tratados e implementados. Diferentes implementações podem oferecer várias maneiras de autenticar fontes de dados. Um conector usa uma instância de Configuração para executar e validar consultas em uma fonte de dados, formando um fluxo de trabalho completo.
Um conector usa uma instância `Config` para executar e validar consultas em uma fonte de dados, formando um fluxo de trabalho completo.

Uma implementação de configuração define como a autenticação é tratada para se conectar a uma fonte de dados. Essa configuração é usada por uma implementação de conector para interagir com a fonte de dados, garantindo que as consultas sejam executadas e validadas corretamente.

Em geral, a interface `Config` é uma parte essencial do fluxo de trabalho para conexão com fontes de dados, concentrando-se especificamente na configuração de autenticação.

### Tipos de implementações de configurações padrão {#default-config-types}

Há três tipos de implementações de configuração abstrata padrão para Autenticação:

- RestConfig
- SqlConfig
- NoSqlConfig

Se uma configuração se alinha a um desses tipos, ela pode estender a classe base correspondente. Caso contrário, ele poderá ser criado do zero ao implementar a interface de configuração do.

### Implementações de configuração concretas {#concrete-config-implementation}

A biblioteca *konnect-definitions* é fornecida com implementações predefinidas da interface de Configuração para algumas configurações de autenticação amplamente usadas. Você pode usar essas configurações diretamente no conector ou definir novas configurações usando a interface de Configuração. Essas implementações incluem:

- Configuração de autenticação da chave de API
- Configuração básica baseada em token de autenticação
- Configuração básica de autenticação
- Configuração do token do portador
- Configuração de Senha de Nome de Usuário para SQL
- Configuração de autenticação de cadeia de conexão para NoSQL

### Recursos adicionais{#resources}

O Experience Manager Guides também permite fornecer recursos personalizados para logotipos e modelos junto com a implementação. Você pode manter esses recursos na pasta `resources`.
Para que possam ser usadas pelo conector, é obrigatório implementar estas funções de conector:


- `getLogoSvg` - Retorna o logotipo SVG como uma cadeia de caracteres.

- `getTemplates` - Retorna a lista de modelos no formato especificado.
