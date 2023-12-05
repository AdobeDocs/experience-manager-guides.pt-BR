---
title: APIs baseadas em Java para fluxo de trabalho de conversão
description: Saiba mais sobre as APIs baseadas em Java para fluxo de trabalho de conversão
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# APIs baseadas em Java para fluxo de trabalho de conversão {#id175UB30E05Z}

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

  A variável **ConversionUtils** classe contém métodos para converter documentos HTML e Word no formato DITA.


## Converter documentos do HTML

A variável `convertHtmlToDita` O método converte documentos HTML no formato DITA.

**Sintaxe**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parâmetros**: |Nome|Tipo|Descrição| |—|—|—| |`session`|javax.jcr.Session|Uma sessão JCR válida.| |`inputFile`|String|Caminho absoluto dos arquivos HTML de origem no repositório AEM.| |`destPath`|String|Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos.| |`createRev`|Booleano|Especificar se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos.|

**Exceção**: Lançamentos `RepositoryException`.

## Converter documentos do Word

A variável ``convertWordToDita`` O método converte documentos do Word no formato DITA.

**Sintaxe**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parâmetros**: |Nome|Tipo|Descrição| |—|—|—| |`session`|javax.jcr.Session|Uma sessão JCR válida.| |`inputFile`|String|Caminho absoluto dos arquivos de origem do Word no repositório AEM.| |`destPath`|String|Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos.| |`style2tagMap`|String|Caminho absoluto do arquivo de mapeamento de estilo que será usado para conversão.| |`createRev`|Booleano|Especificar se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos.|

**Exceção**: Lançamentos `RepositoryException`.
