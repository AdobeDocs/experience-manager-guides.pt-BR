---
title: API baseada em Java para criar e ativar pacotes
description: Saiba mais sobre a API baseada em Java para criar e ativar pacotes
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
feature: Java-Based API Packages
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/g5Mp7tMM9JaAYwNmMyPmaFEcI0fx66vrX8ry97lIUF8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 618
ht-degree: 0%

---

# API baseada em Java para criar e ativar pacotes {#id175UB30E05Z}

>[!NOTE]
>
> Você pode usar APIs baseadas em Java disponíveis no Experience Manager Guides para criar plug-ins personalizados e estender workflows prontos para uso. Este artigo será arquivado em novembro de 2024.
> Exiba [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obter a documentação mais recente e detalhada sobre como usar a API baseada em Java.


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
| `activationTarget` | String | (*Opcional*) `preview` ou `publish` para Cloud Service e `publish` para Software Local <br> - Para Cloud Service, se o parâmetro contiver um valor inválido, a ativação do pacote falhará. <br> - Para Software Local, se o parâmetro contiver um valor inválido, o erro será registrado e a publicação será feita usando o valor padrão, `publish`. |

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
