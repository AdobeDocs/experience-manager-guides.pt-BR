---
title: APIs baseadas em Java para trabalhar com mapas DITA
description: Saiba mais sobre as APIs baseadas em Java para trabalhar com mapas DITA
exl-id: bd91fc90-75f8-487c-99d1-2637e9cf9924
feature: Java-Based API Dita Map
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 2%

---

# APIs baseadas em Java para trabalhar com mapas DITA {#id175UB30E05Z}

>[!NOTE]
>
> Você pode usar APIs baseadas em Java disponíveis no Experience Manager Guides para criar plug-ins personalizados e estender workflows prontos para uso. Este artigo será arquivado em novembro de 2024.
> Exiba [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obter a documentação mais recente e detalhada sobre como usar a API baseada em Java.



As seguintes APIs baseadas em Java permitem trabalhar com mapas DITA no AEM Guides. Essas APIs estão disponíveis no formato de um pacote. Você deve incluir esse pacote no código para usar essas APIs.

Detalhes do pacote:

- ID do grupo: **com.adobe.fmdita**

- ID do artefato: **api**

- Versão: **3.2**

- Pacote: **com.adobe.fmdita.api.maps**

- Detalhes da classe:

  ```JAVA
  public class MapUtilities extends Object
  ```

  A classe MapUtilities contém métodos para recuperar informações de metadados de um arquivo de mapa DITA.


## Baixar mapa DITA com dependentes

O método `zipMapWithDependents` cria um arquivo .zip contendo um mapa DITA juntamente com todos os seus dependentes, como tópicos, submapas, imagens e DTDs referenciados. O arquivo .zip do mapa DITA é criado com base em uma determinada linha de base.

Também permite manter a mesma estrutura \(pastas pai e filho\) ou criar uma estrutura de arquivo simples em uma única pasta para todos os arquivos dependentes.

>[!IMPORTANT]
>
> A API gerará uma exceção e não criará um arquivo .zip se algum dos arquivos dependentes estiver ausente.

**Sintaxe**:

```JAVA
public static void zipMapWithDependents(Session session, 
                     String sourcePath, 
                     String baseline, 
                     OutputStream outputStream,
                     boolean flatFS) 
                     throws RepositoryException, IOException
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `session` | javax.jcr.Session | Uma sessão JCR válida. |
| `sourcePath` | String | Caminho \(no repositório AEM\) do arquivo de mapa DITA que precisa ser baixado. |
| `outputStream` | java.io.OutputStream | O fluxo no qual gravar o ZIP. |
| `baseline` | String | O título da linha de base usada para recuperar o conteúdo com versão. <br> **Observação:** o valor diferencia maiúsculas de minúsculas. |
| flatFS | Booleano | \(Opcional\) Se definido como verdadeiro, então uma estrutura simples de arquivos é retornada no arquivo ZIP. Por exemplo, se o mapa DITA fizer referência ao conteúdo em várias pastas, todos os arquivos referenciados serão colocados em uma única pasta. Caso haja arquivos com o mesmo nome, eles serão renomeados adicionando um sufixo numérico. Todas as referências \(no mapa DITA e em tópicos\) são manipuladas automaticamente, pois são atualizadas com base no novo local dos arquivos na estrutura de pasta simples. Se definido como falso, a estrutura de pastas será mantida como está no arquivo ZIP. Se o mapa DITA se referir a arquivos de vários locais, todos esses locais também serão criados no arquivo ZIP. Ao restaurar o arquivo ZIP, a estrutura de pastas exata é criada no local de destino. <br> O valor padrão para este parâmetro é false. |

**Devoluções**:
O conteúdo do ZIP é gravado no `outputStream`.

**Exceção**:
Lança ``javax.jcr.RepositoryException``, `java.io.IOException`.

## Baixar mapa DITA com dependentes \(Assíncrono\)

Como alternativa, você pode baixar o mapa DITA com dependentes em um modo assíncrono. Essa abordagem é mais útil para mapas DITA maiores.

O método `zipMapWithDependents` cria um arquivo .zip contendo um mapa DITA juntamente com todos os seus dependentes, como tópicos, submapas, imagens e DTDs referenciados. O arquivo .zip do mapa DITA é criado com base em uma determinada linha de base.

Também permite manter a mesma estrutura \(pastas pai e filho\) ou criar uma estrutura de arquivo simples em uma única pasta para todos os arquivos dependentes.

>[!NOTE]
>
> Esse nó é excluído automaticamente após algum tempo com base na configuração output.history.purgetime, se definida, ou 5 dias, como padrão.

**Sintaxe**:

```JAVA
public static CompletableFuture<Node> zipMapWithDependencies(Session session,
                     String sourcePath, 
                     String baseline, 
                     boolean flatFS) 
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `session` | javax.jcr.Session | Uma sessão JCR válida. |
| `sourcePath` | String | Caminho \(no repositório AEM\) do arquivo de mapa DITA que precisa ser baixado. |
| `baseline` | String | O título da linha de base usada para recuperar o conteúdo com versão. <br> **Observação:** o valor diferencia maiúsculas de minúsculas. |
| flatFS | Booleano | \(Opcional\) Se definido como verdadeiro, então uma estrutura simples de arquivos é retornada no arquivo ZIP. Por exemplo, se o mapa DITA fizer referência ao conteúdo em várias pastas, todos os arquivos referenciados serão colocados em uma única pasta. Caso haja arquivos com o mesmo nome, eles serão renomeados adicionando um sufixo numérico. Todas as referências \(no mapa DITA e em tópicos\) são manipuladas automaticamente, pois são atualizadas com base no novo local dos arquivos na estrutura de pasta simples. Se definido como falso, a estrutura de pastas será mantida como está no arquivo ZIP. Se o mapa DITA se referir a arquivos de vários locais, todos esses locais também serão criados no arquivo ZIP. Ao restaurar o arquivo ZIP, a estrutura de pastas exata é criada no local de destino.<br> O valor padrão para este parâmetro é false. |

**Devoluções**:
O nó do arquivo zip está encapsulado na classe `CompletableFuture`. O usuário pode continuar a manipulá-lo de forma assíncrona e pode usar o método `.get()` do futuro para bloquear o thread quando o nó for necessário. O valor retornado também pode terminar com um erro, e isso pode ser tratado com o método `.exceptionally()`.

## Obter uma lista de linhas de base

O método ``getBaselineList`` recupera uma lista de todas as linhas de base existentes para um determinado mapa DITA.

**Sintaxe**:

```JAVA
public static List<HashMap<String,String>> getBaselineList( 
                  javax.jcr.Session session, 
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `session` | javax.jcr.Session | Uma sessão JCR válida. |
| `sourcePath` | String | Caminho \(no repositório AEM\) do arquivo de mapa DITA para o qual as informações da linha de base serão recuperadas. |

**Devoluções**:
Uma lista de `HashMap` objetos. Cada objeto `HashMap` representa uma linha de base e contém seu nome e título.

**Exceção**:
Lança ``javax.jcr.RepositoryException``.

## Obter uma lista de predefinições condicionais

O método ``getConditionalPresetList`` recupera uma lista de todas as predefinições condicionais existentes para um determinado mapa DITA.

**Sintaxe**:

```JAVA
public static List<HashMap<String,String>> getConditionalPresetList (
                  javax.jcr.Session session,
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `session` | javax.jcr.Session | Uma sessão JCR válida. |
| `sourcePath` | String | Caminho \(no repositório AEM\) do arquivo de mapa DITA para o qual as informações condicionais predefinidas serão recuperadas. |

**Devoluções**:
Uma lista de `HashMap` objetos. Cada objeto `HashMap` representa uma predefinição condicional e contém o nome e o título da predefinição condicional.

**Exceção**:
Lança ``javax.jcr.RepositoryException``.

## Obter as informações do arquivo DITAVAL para uma predefinição condicional

O método ``getDitavalFromConditionalPreset`` recupera o caminho do arquivo DITAVAL correspondente a uma predefinição condicional para um determinado mapa DITA.

**Sintaxe**:

```JAVA
public static String getDitavalFromConditionalPreset
    (Session session,
    String sourcePath, 
    String cpName) throws RepositoryException
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `session` | javax.jcr.Session | Uma sessão JCR válida. |
| `sourcePath` | String | Caminho \(no repositório AEM\) do arquivo de mapa DITA para o qual o arquivo DITAVAL será recuperado. |
| `cpName` | String | Nome da predefinição condicional no mapa DITA para a qual o arquivo DITAVAL deve ser recuperado. |

**Devoluções**:
O caminho do arquivo DITAVAL correspondente à predefinição condicional definida no arquivo de mapa DITA.

## Obter todas as dependências de um nó

O método ``getAllDependencies`` retorna todas as dependências de um determinado nó.

**Sintaxe**:

```JAVA
public static List
<Node> getAllDependencies 
(Node rootNode) throws GuidesApiException
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `rootNode` | javax.jcr.Node | O nó raiz para o qual todas as dependências devem ser recuperadas. |

**Devoluções**:
Uma lista de nós que contém todas as dependências do nó raiz.
