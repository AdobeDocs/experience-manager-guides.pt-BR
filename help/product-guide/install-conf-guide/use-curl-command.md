---
title: Usar comandos curl
description: Saiba como usar comandos curl no conteúdo carregado no Experience Manager Guides.
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 1%

---

# Usar comandos curl

Você também pode usar comandos curl para criar uma pasta no DAM, fazer upload de arquivos e adicionar metadados ao conteúdo carregado.

## Criar uma pasta

Execute o seguinte comando para criar uma pasta no repositório do AEM:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Especifique os seguintes parâmetros para criar uma pasta:

- `<username>:<passowrd>`: especifique o nome de usuário e a senha para acessar o repositório do AEM. Esse usuário deve ter os privilégios de criação de pasta.

- `jcr:primaryType=sling:Folder`: Especifique este parâmetro *como está* para criar um recurso do tipo pasta.

- `<server folder path>`: Caminho completo da pasta incluindo o nome da nova pasta que você deseja criar no repositório do AEM. Por exemplo, se você especificar o caminho como `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, a pasta `AEM-Guides` será criada dentro da pasta `projects` no DAM.


## Carregar um arquivo

Execute o seguinte comando para fazer upload de um arquivo no repositório do AEM:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Especifique os seguintes parâmetros para fazer upload de um arquivo:

- `<username>:<passowrd>`: especifique o nome de usuário e a senha para acessar o repositório do AEM. Este usuário deve ter privilégios de gravação no `server folder path`.

- ``local file path``: caminho de arquivo completo no sistema local que você deseja carregar.

- `<server folder path>`: Complete o caminho da pasta no servidor do AEM onde você deseja carregar o arquivo.


## Adicionar metadados

Execute o seguinte comando para adicionar metadados em um arquivo:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Especifique os seguintes parâmetros para adicionar informações de metadados:

- `<username>:<passowrd>`: especifique o nome de usuário e a senha para acessar o repositório do AEM. Este usuário deve ter privilégios de gravação no ``metadata node path``.

- ``-F<attribute name>=<value>``: `<attribute name>` é o nome do atributo de metadados, como `audience` e `<value>` poderia ser `internal`. Você pode especificar vários pares nome-valor do atributo separados por espaço.

- `<metadata node path>`: Caminho completo da pasta incluindo o nome do arquivo e seu nó de metadados. Por exemplo, se você especificar o caminho como `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, as informações de metadados especificadas serão definidas no arquivo `intro.xml`.