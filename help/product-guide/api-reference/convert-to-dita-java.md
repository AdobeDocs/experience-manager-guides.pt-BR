---
title: APIs baseadas em Java para fluxo de trabalho de conversão
description: Saiba mais sobre as APIs baseadas em Java para fluxo de trabalho de conversão
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/gAntb7T-OGlwRNInxAsV8orxL3H9qL19Dsjwf5FZ14I'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: c2674c69-1bed-41fa-ba40-ab1a5382af59
    internal-label: Java Based API Conversion Workflow
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 3%
---
# APIs baseadas em Java para fluxo de trabalho de conversão {#id175UB30E05Z}

>[!NOTE]
>
> Você pode usar APIs baseadas em Java disponíveis no Experience Manager Guides para criar plug-ins personalizados e estender workflows prontos para uso. Este artigo será arquivado em novembro de 2024.
> Exiba [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obter a documentação mais recente e detalhada sobre como usar a API baseada em Java.




As seguintes APIs baseadas em Java permitem converter documentos do HTML e do Word para o formato DITA. Essas APIs estão disponíveis no formato de um pacote. Você deve incluir esse pacote no código para usar essas APIs.

**Detalhes do pacote**:

- ID do grupo: **com.adobe.fmdita**

- ID do artefato: **api**

- Versão: **3.2**

- Pacote: **com.adobe.fmdita.api.conversion**

- Detalhes da classe:

  ```JAVA
  public class ConversionUtils extends Object
  ```

  A classe **ConversionUtils** contém métodos para converter documentos do HTML e do Word para o formato DITA.


## Converter documentos do HTML

O método `convertHtmlToDita` converte documentos HTML no formato DITA.

**Sintaxe**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `session` | javax.jcr.Session | Uma sessão JCR válida. |
| `inputFile` | String | Caminho absoluto dos arquivos HTML de origem no repositório do AEM. |
| `destPath` | String | Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos. |
| `createRev` | Booleano | Especifique se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos. |

**Exceção**:
Lança `RepositoryException`.

## Converter documentos do Word

O método ``convertWordToDita`` converte documentos do Word no formato DITA.

**Sintaxe**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `session` | javax.jcr.Session | Uma sessão JCR válida. |
| `inputFile` | String | Caminho absoluto dos arquivos de origem do Word no repositório do AEM. |
| `destPath` | String | Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos. |
| `style2tagMap` | String | Caminho absoluto do arquivo de mapeamento de estilo que será usado para conversão. |
| `createRev` | Booleano | Especifique se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos. |

**Exceção**:
Lança `RepositoryException`.
