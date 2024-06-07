---
title: REST API para criação e ativação de pacotes
description: Saiba mais sobre a REST API para criar e ativar pacotes
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: b95a64ca2e8ebffebec3d8ff8704f76f7faceca2
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# REST API para criação e ativação de pacotes {#id198CF0260Y4}

A API REST a seguir permite criar e ativar pacotes CRX.

## Criar e ativar pacote

Um método POST que cria e ativa o pacote CRX.

**Solicitar URL**:
*&lt;aem-guides-server\>* http://: *&lt;port-number\>*/bin/fmdita/activate&lt;/port-number\>&lt;/aem-guides-server\>

**Parâmetros**:
O solicitação query consiste na string de regras JSON. A tipo de conteúdo da solicitação POST deve ser definida como `application/json; charset=UTF-8`.

**Exemplo**:
O exemplo a seguir mostra a chamada da API usando o comando curl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Parâmetro opcional**

`activationTarget`

**Valores válidos**

`preview` ou `publish` para Cloud Service e `publish` para software no local

- Para Cloud Service, se o parâmetro contiver um valor de inválido, o pacote ativação falhar.

- Para o Software no local, se o parâmetro contiver um valor de inválido, o erro será registrado e a publicação será feita usando o valor `publish`padrão.

Se você definir o parâmetro opcional, `activationTarget`ele será ativado usando o agente de publicar padrão para softwares Cloud Service e no local.



O exemplo a seguir mostra a chamada da API usando o comando curl com parâmetro opcional:


    &#39;&#39;&#39;XML
    
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: aplicativo/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate?activationTarget=&lt;validActivationTargetValue>&#39;&#39;&#39;
    &#39;&#39;
&lt;/validActivationTargetValue>&lt;/*port-number*>&lt;/*aem-guides-server*>&lt;/*password*>&lt;/*username*>