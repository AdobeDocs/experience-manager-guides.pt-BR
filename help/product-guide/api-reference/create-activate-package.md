---
title: API REST para criar e ativar pacotes
description: Saiba mais sobre a API REST para criar e ativar pacotes
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# API REST para criar e ativar pacotes {#id198CF0260Y4}

A API REST a seguir permite criar e ativar pacotes do CRX.

## Criar e ativar pacote

Um método POST que cria e ativa o pacote do CRX.

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


```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate?activationTarget=`<validActivationTargetValue>`
```
