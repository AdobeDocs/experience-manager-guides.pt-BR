---
title: API REST para trabalhar com atributos condicionais
description: Saiba mais sobre a REST API para trabalhar com atributos condicionais
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# API REST para trabalhar com atributos condicionais {#id175UB30E05Z}

A API REST a seguir permite adicionar atributos condicionais em um perfil de pasta.

## Adicionar atributo condicional em um perfil de nível de pasta

Um método POST que adiciona atributos condicionais a um determinado perfil de nível de pasta.

**URL de solicitação**:\
http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/folderprofiles

**Parâmetros**:\
|Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`:operation`|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é ``ADDATTRIBUTEPROFILES``. <br> **Nota:** O valor não diferencia maiúsculas de minúsculas.| |`profilename`|String|Sim|Exibir nome do perfil no nível da pasta no qual os atributos condicionais devem ser adicionados.| |`conditionalprofiles`|Matriz JSON|Sim|Uma matriz JSON que consiste no nome e nos valores do atributo condicional. O trecho de código de exemplo a seguir mostra a matriz JSON com dois atributos - `platform` e `product` com vários valores atribuídos a eles.|

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
