---
title: API REST para registrar um conector de fonte de dados
description: Saiba mais sobre a REST API para registrar um conector de fonte de dados
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
source-git-commit: 45ae1471fe0f0586764ede9dd96530b7f75f69ee
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 7%

---

# API REST para registrar um conector de fonte de dados {#id236LG0Y0CXA}

A API REST a seguir permite registrar um conector de fonte de dados.

## Registrar um conector de fonte de dados

Um método GET que registra um conector de origem de dados.

**Solicitar URL**:

`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parâmetros**:

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `path` | String | Sim | Uma string que aponta para um caminho no repositório AEM. Pode ser um caminho no `/content/dam or /var/dxml`. |

**Exemplo**:

`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
