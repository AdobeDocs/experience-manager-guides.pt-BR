---
title: APIs baseadas em Java para trabalhar com rótulos e linhas de base
description: Saiba mais sobre as APIs baseadas em Java para trabalhar com linhas de base e rótulos
exl-id: 0e2ba1bb-f5bf-44da-848a-a55385460c83
feature: Java-Based API Baseline
role: Developer
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 0%

---

# APIs baseadas em Java para trabalhar com rótulos e linhas de base {#id175UB30E05Z}

As seguintes APIs baseadas em Java permitem criar uma linha de base e adicionar rótulos aos arquivos em uma linha de base. Essas APIs estão disponíveis no formato de um pacote. Você deve incluir esse pacote no código para usar essas APIs.

Detalhes do pacote:

- ID do grupo: **com.adobe.fmdita**

- ID do artefato: **api**

- Versão: **3.5**

- Pacote: **com.adobe.fmdita.api.baselines**

- Detalhes da classe:

  ```JAVA
  public class BaselineUtils extends Object
  ```

  A classe **BaselineUtils** contém métodos para criar linhas de base e aplicar rótulos a arquivos em uma linha de base.


## Criar uma linha de base

O método de criação de linha de base tem duas versões: uma para a solução do XML Documentation versão 3.5 e outra para versões anteriores à versão 3.5 \(que inclui as versões 3.4, 3.3 e 3.2\). A API versão 3.5 permite a criação de uma linha de base usando um rótulo, referências diretas e referências indiretas em um arquivo de mapa.

A outra versão da API usa data e hora para criar uma linha de base. Essa API é mantida para compatibilidade com versões anteriores com sistemas que usam a solução da XML Documentation 3.4, 3.3 ou 3.2.

**Sintaxe \(para a versão 3.5\)**:

```JAVA
public static String createBaseline(Session session, 
String sourcePath, 
String baselineTitle, 
String label, 
LinkedHashMap directContext, 
LinkedHashMap indirectContext) 
throws GuidesApiException
```

**Parâmetros**:
|Nome|Tipo|Descrição|
|—|—|—|
|`session`|javax.jcr.Session|Uma sessão JCR válida. A sessão do usuário precisa ter permissões de leitura e gravação para o mapa DITA e permissões de leitura para todos os arquivos de referência incluídos na linha de base.|
|`sourcePath`|String|Caminho absoluto do arquivo de mapa DITA no repositório AEM.|
|`baselineTitle`|Cadeia de caracteres|Um título exclusivo para a linha de base.|
|`label`|String|Selecione a versão de um tópico que tem o rótulo fornecido aplicado a ele.|
|`directContext`|LinkedHashMap&lt;String, Object\>|As configurações com base nas quais o tópico diretamente referenciado \(content\) é selecionado, a ordem mencionada no mapa é seguida para resolver uma versão. <br> Se, após a iteração em todas as chaves do mapa, nenhuma versão for encontrada, o processo de criação da linha de base falhará. <br> Se HashMap estiver vazio \(enviar mapa vazio e não nulo para o padrão\), então, por padrão, será preenchido como: <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Se você quiser que a criação da linha de base só escolha a versão de um determinado rótulo e falhar se essa versão não existir, coloque a chave `label` e o rótulo no qual você deseja criar a linha de base.|
|`indirectContext`|LinkedHashMap&lt;String, Object\>|As configurações com base nas quais o tópico indiretamente referenciado \(conteúdo referenciado\) é selecionado, a ordem mencionada no mapa é seguida para resolver uma versão. <br> Se, após a iteração em todas as chaves do mapa, nenhuma versão for encontrada, o processo de criação da linha de base falhará. <br> Se o HashMap estiver vazio \(enviar mapa vazio e não nulo para o padrão\), então, por padrão, ele será preenchido como: <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Se você quiser que seja a versão mais recente em vez de selecionar uma versão automaticamente, substitua: <br>`indirectContext.put("pickAutomatically", null);` <br> _com:_ <br>`indirectContext.put("latest", true)`|

**Devoluções**:
O nome da linha de base, que é o nome do nó da linha de base no repositório JCR. O título da linha de base recém-criada será mostrado ao usuário na página Linha de base do mapa DITA.

**Exceção**:
Lança ``ItemExistExceptiom`` se uma linha de base com o mesmo título já existir.

**Sintaxe \(para as versões 3.4, 3.3 e 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Parâmetros**:
|Nome|Tipo|Descrição|
|—|—|—|
|`session`|javax.jcr.Session|Uma sessão JCR válida. A sessão do usuário precisa ter permissões de leitura e gravação para o mapa DITA e permissões de leitura para todos os arquivos de referência incluídos na linha de base.|
|``sourcePath``|String|Caminho absoluto do arquivo de mapa DITA no repositório AEM.|
|`baselineTitle`|Cadeia de caracteres|Um título exclusivo para a linha de base.|
|`versionDate`|Data|A linha de base é criada usando as versões dos tópicos\(referenciadas diretamente do mapa DITA\) como nessa data. Especifique a data no formato `d-MM-yyyy H:mm`.|

**Devoluções**:
O nome da linha de base, que é o nome do nó da linha de base no repositório JCR. O título da linha de base recém-criada será mostrado ao usuário na página Linha de base do mapa DITA.

**Exceção**:
Lança ``RepositoryException.``

## Aplicar rótulos

O método ``applyLabel`` aplica um ou vários rótulos aos arquivos em uma linha de base.

**Sintaxe**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Parâmetros**:
|Nome|Tipo|Descrição|
|—|—|—|
|`session`|javax.jcr.Session|Uma sessão JCR válida.|
|`sourcePath`|String|Caminho absoluto do arquivo de mapa DITA no repositório AEM.|
|``baselineName``|String|Nome do nó da linha de base no qual o rótulo deve ser aplicado. Para obter o nome do nó de linha de base, você pode usar o método [\#id185NFF0085Z](#id185NFF0085Z) ou verificar o nó de linhas de base do mapa DITA no CRXDE.<br> **Observação:** o rótulo é aplicado à versão dos arquivos referenciados diretamente do arquivo de mapa na linha de base.|
|`label`|String|Um rótulo que é aplicado em arquivos na linha de base. Certifique-se de que o rótulo não contenha os seguintes caracteres: &amp;sol; &amp;vírgula; &amp;dois pontos; &amp;vírgula; &amp;lbrack; &amp;vírgula; &amp;rbrack; &amp;vírgula; &amp;vert; &amp;vírgula; &amp;ast; <br> Caso deseje definir vários rótulos, separe-os com uma vírgula; por exemplo, Rótulo1, Rótulo2.|

**Exceção**:
Lança `RepositoryException`.

## Excluir rótulos

O método ``deleteLabel`` exclui um ou vários rótulos dos arquivos em uma linha de base.

**Sintaxe**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Parâmetros**:
|Nome|Tipo|Descrição|
|—|—|—|
|`session`|javax.jcr.Session|Uma sessão JCR válida.|
|`sourcePath`|String|Caminho absoluto do arquivo de mapa DITA no repositório AEM.|
|`baselineName`|String|Nome da linha de base da qual o rótulo deve ser excluído. <br> **Observação:** o rótulo foi excluído da versão dos arquivos que são referenciados diretamente do arquivo de mapa na linha de base.|
|`label`|String|Um rótulo que deve ser excluído dos arquivos na linha de base. <br> Caso queira excluir vários rótulos, separe-os com uma vírgula; por exemplo Rótulo1, Rótulo2.|

**Devoluções**:
O mapa com o par *key:value* de `path:deletedlabels` para todos os arquivos na linha de base.

**Exceção**:
Lança ``RepositoryException`, `VersionException`, `Exception``.
