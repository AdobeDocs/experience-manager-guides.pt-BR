---
title: API REST para trabalhar com atributos condicionais
description: Saiba mais sobre a REST API para trabalhar com atributos condicionais
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# API REST para trabalhar com atributos condicionais {#id175UB30E05Z}

A API REST a seguir permite adicionar atributos condicionais em um perfil de pasta.

## Adicionar atributo condicional em um perfil de nível de pasta

Um método POST que adiciona atributos condicionais a um determinado perfil de nível de pasta.

**Solicitar URL**:\
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/folderprofiles

**Parâmetros**:\
|Nome|Tipo|Obrigatório|Descrição|
|—|—|—|—|
|`:operation`|Cadeia de Caracteres|Sim|Nome da operação que está sendo chamada. O valor deste parâmetro é ``ADDATTRIBUTEPROFILES``. <br> **Observação:** o valor não diferencia maiúsculas de minúsculas.|
|`profilename`|String|Yes|Exibir o nome do perfil de nível de pasta no qual os atributos condicionais devem ser adicionados.|
|`conditionalprofiles`|Matriz JSON|Sim|Uma matriz JSON que consiste no nome e nos valores do atributo condicional. O trecho de código de exemplo a seguir mostra a matriz JSON com dois atributos - `platform` e `product` com vários valores atribuídos a eles.|

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
