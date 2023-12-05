---
title: API baseada em Java para trabalhar com perfis de pastas
description: Saiba mais sobre a API baseada em Java para trabalhar com perfis de pasta
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# API baseada em Java para trabalhar com perfis de pastas {#id175UB30E05Z}

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

  A variável **`FolderProfileUtils`** A classe contém um método para adicionar atributos condicionais em um perfil de pasta.


## Adicionar atributos condicionais a um perfil de pasta

A variável ``addAttributeProfiles`` O método adiciona atributos condicionais a um perfil de nível de pasta.

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

**Parâmetros**: |Nome|Tipo|Descrição| |—|—|—| |``attributeNames``|String|Uma lista de nomes de atributos.| |``values``|String|Uma lista de valores para os atributos fornecidos.| |`labels`|String|Uma lista de rótulos para a `attribute`- `value` pares. [1](#fntarg_1)| |`profileName`|String|O nome do perfil no nível da pasta ao qual esses atributos, valores e rótulos devem ser aplicados. **Importante:** Todos os atributos-valores-rótulos existentes definidos no perfil são substituídos.| |`session`|javax.jcr.Session|Uma sessão JCR válida.|

**Devoluções**:
`true` para obter sucesso. No caso de uma falha, ele aciona uma exceção.

**Exceção**: Lançamentos ``java.lang.Exception`` nos seguintes cenários:

- Se a API não pudesse obter `resourceResolverFactory` objeto. Nesse caso, você deve reiniciar o pacote.
- Se os parâmetros transmitidos para a API forem inválidos.
- Se a API for chamada por meio de uma sessão de usuário não autorizada, como o usuário que não é um administrador para o perfil de pasta determinado.

[1](#fnsrc_1) A variável `attributeNames`, `values`, e `labels` no mesmo índice em uma lista de matriz deve corresponder à mesma entrada.
