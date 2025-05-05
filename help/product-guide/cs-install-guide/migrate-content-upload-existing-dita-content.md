---
title: Fazer upload de conteúdo DITA existente
description: Saiba como fazer upload de conteúdo DITA existente
exl-id: 2b385eef-00a7-4c25-9e78-367a0c9e44ba
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Fazer upload de conteúdo DITA existente {#id176FF000JUI}

Provavelmente, você teria um repositório de conteúdo DITA existente que gostaria de usar com o AEM Guides. Para esse conteúdo existente, você pode usar qualquer um dos métodos compatíveis explicados em [Adicionar ativos digitais ao Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=pt-BR).

## Configurar padrão de nome de arquivo UUID

Ao importar conteúdo, não é necessário que os nomes de arquivo sejam baseados na UUID. Em um sistema que usa nomes de arquivo baseados em UUID, é obrigatório que todos os arquivos sejam referenciados usando seus UUIDs em vez de seus nomes de arquivo originais. Se um arquivo importado não tiver nomes de arquivos baseados em UUID, você poderá configurar o sistema para adicionar uma UUID à propriedade do arquivo. Essa UUID é então usada para se referir a esses arquivos, nos quais a UUID não é usada para nomear os arquivos.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar o padrão de nome de arquivo UUID:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Cadeia de caracteres especificando o regex do padrão de nome de arquivo UUID. <br> Se um arquivo não seguir o padrão especificado, uma UUID será adicionada à propriedade do arquivo e todas as referências ao arquivo serão atualizadas com a UUID atribuída ao arquivo. <br> **Valor padrão**: `"^GUID-(?<id>.*)"` |

## Usar comandos curl

Você também pode usar comandos curl para criar uma pasta no DAM, fazer upload de arquivos e adicionar metadados ao conteúdo carregado.

**Criar uma pasta**

Execute o seguinte comando para criar uma pasta no repositório AEM:

```
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Especifique os seguintes parâmetros para criar uma pasta:

- `<username>:<passowrd>`: especifique o nome de usuário e a senha para acessar o repositório AEM. Esse usuário deve ter os privilégios de criação de pasta.

- `jcr:primaryType=sling:Folder`: Especifique este parâmetro *como está* para criar um recurso do tipo pasta.

- `<server folder path>`: Caminho completo da pasta incluindo o nome da nova pasta que você deseja criar no repositório AEM. Por exemplo, se você especificar o caminho como `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, a pasta `AEM-Guides` será criada dentro da pasta `projects` no DAM.


**Carregar um arquivo**

Execute o seguinte comando para carregar um arquivo no repositório AEM:

```
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Especifique os seguintes parâmetros para fazer upload de um arquivo:

- `<username>:<passowrd>`: especifique o nome de usuário e a senha para acessar o repositório AEM. Este usuário deve ter privilégios de gravação no `server folder path`.

- ``local file path``: caminho de arquivo completo no sistema local que você deseja carregar.

- `<server folder path>`: Complete o caminho da pasta no servidor AEM onde você deseja carregar o arquivo.


**Adicionar metadados**

Execute o seguinte comando para adicionar metadados em um arquivo:

```
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Especifique os seguintes parâmetros para adicionar informações de metadados:

- `<username>:<passowrd>`: especifique o nome de usuário e a senha para acessar o repositório AEM. Este usuário deve ter privilégios de gravação no ``metadata node path``.

- ``-F<attribute name>=<value>``: `<attribute name>` é o nome do atributo de metadados, como `audience` e `<value>` poderia ser `internal`. Você pode especificar vários pares nome-valor do atributo separados por espaço.

- `<metadata node path>`: Caminho completo da pasta incluindo o nome do arquivo e seu nó de metadados. Por exemplo, se você especificar o caminho como `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, as informações de metadados especificadas serão definidas no arquivo `intro.xml`.


**Tópico pai:**&#x200B;[ Migrar conteúdo existente](migrate-content.md)
