---
title: API REST para trabalhar com atributos condicionais
description: Saiba mais sobre a REST API para trabalhar com atributos condicionais
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/qtmJN6jjCm3xeNYAaHTWr7G3SZFSOodcVqBOKctR3B8'
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
  - id: d27d524e-c4e5-4b77-b86b-3db049db0b25
    internal-label: REST API Conditional Attributes
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 5%
---
# API REST para trabalhar com atributos condicionais {#id175UB30E05Z}

A API REST a seguir permite adicionar atributos condicionais em um perfil de pasta.

## Adicionar atributo condicional em um perfil de nível de pasta

Um método POST que adiciona atributos condicionais a um determinado perfil de nível de pasta.

**Solicitar URL**:\
http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/folderprofiles

**Parâmetros**:

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `:operation` | String | Sim | Nome da operação que está sendo chamada. O valor deste parâmetro é ``ADDATTRIBUTEPROFILES``. <br> **Observação:** o valor não diferencia maiúsculas de minúsculas. |
| `profilename` | String | Sim | Nome de exibição do perfil no nível da pasta no qual os atributos condicionais devem ser adicionados. |
| `conditionalprofiles` | Matriz JSON | Sim | Uma matriz JSON que consiste no nome e nos valores do atributo condicional. O trecho de código de exemplo a seguir mostra a matriz JSON com dois atributos - `platform` e `product` com vários valores atribuídos a eles. |

```JSON
[  {    name: "platform",    
        values: [       
                {value: "win", label: "Windows"},       
                {value: "mac", label: "Mac OS"}    
                ]},
                {    
                    name: "product",    
                    values: [      
                        {value: "aem_1", label: "AEM 6.1"},     
                        {value: "aem_4,  label: "AEM 6.4"}  
                        ]  
                }]
```

**Valores de resposta**:\
Retorna uma resposta HTTP 200 \(Successful\).
