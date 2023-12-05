---
title: API baseada em Java para criar e ativar pacotes
description: Saiba mais sobre a API baseada em Java para criar e ativar pacotes
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# API baseada em Java para criar e ativar pacotes {#id175UB30E05Z}

A seguinte API baseada em Java permite criar e ativar pacotes CRX. Essa API está disponível no formato de um pacote. Você deve incluir esse pacote no código para usar essas APIs.

Detalhes do pacote:

- ID do grupo: **com.adobe.fmdita**

- ID do artefato: **api**

- Versão: **3.3**

- Pacote: **com.adobe.fmdita.api.crxactivate**

- Detalhes da classe:

  ```JAVA
  public class CRXActivator
  ```

  A variável **`CRXActivator`** A classe contém um método para criar pacotes CRX e replicá-los na instância de publicação.


## Criar e ativar pacotes

A variável `activate` O método cria um pacote CRX na instância do autor e o replica na instância de publicação, se necessário. Pressupõe-se que os parâmetros de replicação do AEM já tenham sido configurados na instância do autor. Esse método cria o pacote CRX com base em uma lista de regras fornecidas como parâmetros de entrada em uma sequência de caracteres JSON.
>[!NOTE]
>
> Os erros encontrados durante o processo de criação ou ativação são gravados na `outputstream`.

**Sintaxe**:

```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream, 
  Session session
) 
throws GuidesApiException
```

**Parâmetros**: |Nome|Tipo|Descrição| |—|—|—| |`json`Cadeia de caracteres|Cadeia de caracteres JSON que determina o pacote CRX a ser criado. Use o formato a seguir para criar a cadeia de caracteres JSON: <br>- `activate`: É do tipo Booleano \(`true`/`false`\). Determina se o pacote CRX criado na instância do autor é replicado para a instância de publicação. <br> - `rules`: é do tipo Matriz JSON. Uma matriz de regras JSON que são processadas sequencialmente para criar o pacote CRX. <br> - `rootPath`: É do tipo String. O caminho base no qual as consultas de nó/propriedade são executadas. Se nenhuma consulta de nó/propriedade estiver presente, o caminho raiz e todos os nós presentes no caminho raiz serão incluídos no pacote CRX. <br> - `nodeQueries`: é do tipo Matriz Regex. Uma matriz de expressões regulares usadas para incluir arquivos específicos no caminho raiz. <br> - `propertyQueries`: é do tipo Matriz JSON. Uma matriz de Objetos JSON com cada Objeto JSON que consiste em uma consulta XPath a ser executada no caminho raiz e o nome de uma propriedade presente em cada nó JCR após a execução da consulta. O valor da propriedade em cada nó JCR deve ser um caminho ou uma matriz de caminhos. Os caminhos presentes nessa propriedade são adicionados ao pacote CRX.| |`outputstream`|java.io.OutputStream|Usado para gravar o resultado de vários estágios, como execução de consulta, inclusão de arquivos, criação de pacotes CRX ou ativação. Qualquer erro encontrado durante o processo de criação ou ativação é gravado no `outputstream`. Isso é útil para depuração.| |`session`|String|Uma sessão JCR válida com permissão de ativação.|

**Exceção**: Lançamentos ``java.io.IOException``.

**Exemplo**: o exemplo a seguir mostra como criar uma consulta JSON:

```JSON
{
  "activate": true,
  "rules": [
    {
      "rootPath": "/content/dam/nested",
      "nodeQueries": [
        ".*\\.jpg",
        ".*\\.png",
        ".*\\.gif"        
      ]
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap"
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap",
      "propertyQueries": [
        {
          "query": "//*[@fileReference]",
          "property": "fileReference"
        }
      ]
    }
  ]
}
```

O exemplo de consulta JSON consiste nas seguintes regras:

- Somente as imagens .png, .jpg e .gif no caminho /content/dam/nested são incluídas no pacote.
- Todos os nós em /content/output/sites/hierarchy\_ditamap estão incluídos no pacote.
- Os caminhos presentes na variável `fileReference` a propriedade dos nós em /content/output/sites/hierarchy\_ditamap está incluída no pacote.
