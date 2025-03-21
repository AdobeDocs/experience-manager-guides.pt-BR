---
title: APIs baseadas em Java para fluxo de trabalho de conversão
description: Saiba mais sobre as APIs baseadas em Java para fluxo de trabalho de conversão
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 4%

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

  A classe **ConversionUtils** contém métodos para converter documentos HTML e Word no formato DITA.


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
| `inputFile` | String | Caminho absoluto dos arquivos HTML de origem no repositório AEM. |
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
| `inputFile` | String | Caminho absoluto dos arquivos de origem do Word no repositório AEM. |
| `destPath` | String | Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos. |
| `style2tagMap` | String | Caminho absoluto do arquivo de mapeamento de estilo que será usado para conversão. |
| `createRev` | Booleano | Especifique se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos. |

**Exceção**:
Lança `RepositoryException`.
