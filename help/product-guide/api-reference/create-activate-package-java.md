---
title: API baseada em Java para criar e ativar pacotes
description: Saiba mais sobre a API baseada em Java para criar e ativar pacotes
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
feature: Java-Based API Packages
role: Developer
level: Experienced
source-git-commit: 1bb422427822e7f369e0c1be7de6b12ec012075e
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 1%

---

# API baseada em Java para criar e ativar pacotes {#id175UB30E05Z}

A seguinte API baseada em Java permite criar e ativar pacotes do CRX. Essa API está disponível no formato de um pacote. Você deve incluir esse pacote no código para usar essas APIs.

Detalhes do pacote:

- ID do grupo: **com.adobe.fmdita**

- ID do artefato: **api**

- Versão: **3.3**

- Pacote: **com.adobe.fmdita.api.crxactivate**

- Detalhes da classe:

  ```JAVA
  public class CRXActivator
  ```

  A classe **`CRXActivator`** contém um método para criar pacotes CRX e replicá-los na instância de publicação.


## Criar e ativar pacotes

O método `activate` cria um pacote do CRX na instância do autor e o replica na instância de publicação, se necessário. Pressupõe-se que os parâmetros de replicação do AEM já tenham sido configurados na instância do autor. Esse método cria o pacote do CRX com base em uma lista de regras fornecidas como parâmetros de entrada em uma cadeia de caracteres JSON.
>[!NOTE]
>
> Erros encontrados durante o processo de criação ou ativação são gravados em `outputstream`.

### Exemplo com dois parâmetros

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

### Exemplo com o terceiro parâmetro opcional

```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream,
  String activationTarget, 
  Session session
) 
throws GuidesApiException
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `json` | String | Sequência JSON que determina o pacote do CRX a ser criado. Use o formato a seguir para criar a cadeia de caracteres JSON: <br>- `activate`: É do tipo Booleano \(`true`/`false`\). Determina se o pacote do CRX criado na instância do autor é replicado para a instância de publicação. <br> - `rules`: É do tipo Matriz JSON. Uma matriz de regras JSON, que são processadas sequencialmente para criar o pacote do CRX. <br> - `rootPath`: É do tipo String. O caminho base no qual as consultas de nó/propriedade são executadas. Se nenhuma consulta de nó/propriedade estiver presente, o caminho raiz e todos os nós presentes no caminho raiz serão incluídos no pacote do CRX. <br> - `nodeQueries`: É do tipo Matriz Regex. Uma matriz de expressões regulares usadas para incluir arquivos específicos no caminho raiz. <br> - `propertyQueries`: É do tipo Matriz JSON. Uma matriz de Objetos JSON com cada Objeto JSON que consiste em uma consulta XPath a ser executada no caminho raiz e o nome de uma propriedade presente em cada nó JCR após a execução da consulta. O valor da propriedade em cada nó JCR deve ser um caminho ou uma matriz de caminhos. Os caminhos presentes nessa propriedade são adicionados ao pacote do CRX. |
| `outputstream` | java.io.OutputStream | Isso é usado para gravar o resultado de vários estágios, como execução de consulta, inclusão de arquivo, criação de pacote do CRX ou ativação. Qualquer erro encontrado durante o processo de criação ou ativação é gravado no `outputstream`. Isso é útil para depuração. |
| `session` | String | Uma sessão JCR válida com permissão de ativação. |
| `activationTarget` | String | (*Opcional*) `preview` ou `publish` para o Cloud Service e `publish` para o Software Local <br> - Para o Cloud Service, se o parâmetro contiver um valor inválido, a ativação do pacote falhará. <br> - Para Software Local, se o parâmetro contiver um valor inválido, o erro será registrado e a publicação será feita usando o valor padrão, `publish`. |

**Exceção**:

Lança `java.io.IOException` e `java.io.IllegalArgumentException`


Se você não definir o parâmetro opcional `activationTarget`, ele será ativado usando o agente de publicação padrão para o Cloud Service e para o Software local.


**Exemplo**:
O exemplo a seguir mostra como criar uma consulta JSON:

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
- Os caminhos presentes na propriedade `fileReference` dos nós em /content/output/sites/hierarchy\_ditamap estão incluídos no pacote.
