---
title: API baseada em Java para trabalhar com a geração de saída
description: Saiba mais sobre a API baseada em Java para trabalhar com a geração de saída
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/i5mTM1VtBg3QFUa-sBmF2pH8BITRn9j-efw2dr8VwCU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: a3bd6397-2eb2-4908-a61c-226e26855dcaid: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2: id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 2%

---

# API baseada em Java para trabalhar com a geração de saída {#id175UB30E05Z}

>[!NOTE]
>
> Você pode usar APIs baseadas em Java disponíveis no Experience Manager Guides para criar plug-ins personalizados e estender workflows prontos para uso. Este artigo será arquivado em novembro de 2024.
> Exiba [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obter a documentação mais recente e detalhada sobre como usar a API baseada em Java.

A seguinte API baseada em Java permite gerar saída para um mapa DITA. Essa API está disponível no formato de um pacote. Você deve incluir esse pacote no código para usar essas APIs.

Detalhes do pacote:

- ID do grupo: **com.adobe.fmdita**

- ID do artefato: **api**

- Versão: **3.4**

- Pacote: ****com.adobe.fmdita.api.maps****

- Detalhes da classe:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  A classe **`PublishUtils`** contém um método para gerar saída para uma ou mais predefinições de saída.


## Gerar saída

O método ``generateOutput`` gera saída para um arquivo de mapa DITA usando as predefinições de saída especificadas.

**Sintaxe**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `session` | javax.jcr.Session | Uma sessão JCR válida. |
| ``sourcePath`` | String | Caminho \(no repositório do AEM\) do arquivo de mapa DITA para o qual a saída precisa ser gerada. |
| ``outputName`` | String | Nome da predefinição de saída\(s\) a ser usada para gerar saída. Várias predefinições de saída podem ser especificadas usando um delimitador de barra vertical \(&quot;\|&quot;\), por exemplo `aemsite\|pdfoutput`. |

**Exceção**:
Lança ``javax.jcr.RepositoryException``, `java.io.IOException` e `java.lang.Exception`.
