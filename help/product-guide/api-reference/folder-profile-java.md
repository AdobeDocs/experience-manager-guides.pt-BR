---
title: API baseada em Java para trabalhar com perfis de pastas
description: Saiba mais sobre a API baseada em Java para trabalhar com perfis de pasta
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
feature: Java-Based API Folder Profiles
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 2%

---

# API baseada em Java para trabalhar com perfis de pastas {#id175UB30E05Z}

>[!NOTE]
>
> Você pode usar APIs baseadas em Java disponíveis no Experience Manager Guides para criar plug-ins personalizados e estender workflows prontos para uso. Este artigo será arquivado em novembro de 2024.
> Exiba [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obter a documentação mais recente e detalhada sobre como usar a API baseada em Java.




A seguinte API baseada em Java permite adicionar atributos condicionais a um perfil de nível de pasta. Essa API está disponível no formato de um pacote. Você deve incluir esse pacote no código para usar essas APIs.

Detalhes do pacote:

- ID do grupo: **com.adobe.fmdita**

- ID do artefato: **api**

- Versão: **3.2**

- Pacote: **com.adobe.fmdita.api.profiles**

- Detalhes da classe:

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  A classe **`FolderProfileUtils`** contém um método para adicionar atributos condicionais em um perfil de pasta.


## Adicionar atributos condicionais a um perfil de pasta

O método ``addAttributeProfiles`` adiciona atributos condicionais a um perfil de nível de pasta.

**Sintaxe**:

```JAVA
public static boolean addAttributeProfiles
(List
<String> attributeNames, 
List
    <String> values, 
List
        <String> labels,
String profileName, 
Session session) throws GuidesApiException
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| ``attributeNames`` | String | Uma lista de nomes de atributos. |
| ``values`` | String | Uma lista de valores para os atributos fornecidos. |
| `labels` | String | Uma lista de rótulos para os pares `attribute`- `value`. [1](#fntarg_1) |
| `profileName` | String | O nome do perfil em nível de pasta ao qual esses atributos, valores e rótulos devem ser aplicados. **Importante:** todos os atributos-valores-rótulos existentes definidos no perfil são substituídos. |
| `session` | javax.jcr.Session | Uma sessão JCR válida. |

**Devoluções**:
`true` para obter êxito. No caso de uma falha, ele aciona uma exceção.

**Exceção**:
Lança ``java.lang.Exception`` nos seguintes cenários:

- Se a API não pudesse obter o objeto `resourceResolverFactory`. Nesse caso, você deve reiniciar o pacote.
- Se os parâmetros transmitidos para a API forem inválidos.
- Se a API for chamada por meio de uma sessão de usuário não autorizada, como o usuário que não é um administrador para o perfil de pasta determinado.

[1](#fnsrc_1) `attributeNames`, `values` e `labels` no mesmo índice em uma lista de matriz devem corresponder à mesma entrada.
