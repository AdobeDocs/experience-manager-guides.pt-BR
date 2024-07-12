---
title: API REST para criar e ativar pacotes
description: Saiba mais sobre a API REST para criar e ativar pacotes
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: b95a64ca2e8ebffebec3d8ff8704f76f7faceca2
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# API REST para criar e ativar pacotes {#id198CF0260Y4}

A API REST a seguir permite criar e ativar pacotes do CRX.

## Criar e ativar pacote

Um método POST que cria e ativa o pacote CRX.

**Solicitar URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/ativate

**Parâmetros**:
A consulta de solicitação consiste na sequência de regras JSON. O tipo de conteúdo da solicitação POST deve ser definido como `application/json; charset=UTF-8`.

**Exemplo**:
O exemplo a seguir mostra a chamada de API usando o comando curl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Parâmetro opcional**

`activationTarget`

**Valores válidos**

`preview` ou `publish` para Cloud Service e `publish` para Software Local

- No Cloud Service, se o parâmetro contiver um valor inválido, a ativação do pacote falhará.

- Para Software Local, se o parâmetro contiver um valor inválido, o erro será registrado e a publicação será feita usando o valor padrão, `publish`.

Se você não definir o parâmetro opcional `activationTarget`, ele será ativado usando o agente de publicação padrão para o Cloud Service e para o Software local.



O exemplo a seguir mostra a chamada de API usando o comando curl com parâmetro opcional:


    &quot;XML
    
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[Cadeia de caracteres de regras JSON](create-ativate-package-java.md#example-create-ativate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/ativate?ativationTarget=`&lt;validAcdk tivationTargetValue>`
    &quot;
