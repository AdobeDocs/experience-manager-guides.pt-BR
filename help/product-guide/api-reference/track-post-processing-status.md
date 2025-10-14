---
title: API para rastrear o pós-processamento de uma pasta ou um ativo
description: Saiba mais sobre a API para rastrear o pós-processamento de uma pasta ou um ativo
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 558108650aeeeda440895972e460fa523b804bb2
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 10%

---

# API para rastrear o status pós-processamento de uma pasta ou um ativo

Veja a seguir um método POST que inicia um trabalho assíncrono para obter o status dos ativos.

## Localizar status de ativos nos Guias

**Solicitar URL**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status `

**Parâmetros**

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `path` | String | Sim | Caminho da pasta ou do ativo para o qual o status precisa ser buscado. |
| `excludedPaths` | String | Não | Caminhos de pasta a serem excluídos da lista acima. |

```JSON
{ 

    "paths": [ 

        "/content/dam/status-fetch1", 

        "/content/dam/status-fetch2" 

    ], 

    "excludedPaths": [ 

        "content/dam/status-fetch1/excluded-folder" 

    ] 

} 
```

**Valores de resposta**
jobId para pesquisar e obter o status de um trabalho assíncrono.

```JSON
{ 

  "jobId": "akjhdfalkj1132", 

  "status": "WAITING", 

 

} 
```

## API do Poller

Um método GET que obtém o status de trabalho assíncrono executado pela API acima.

**Solicitar URL**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status`

**Parâmetros**

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `jobId` | String | Sim | ID do trabalho retornada pela API acima. |

**Valores de resposta**

Lista de ativos e seus status.

```JSON
{ 

  "jobId": " akjhdfalkj1132", 

  "status": "SUCCESS", 

  "assets": [ 

    { 

      "path": "/content/dam/status-fetch1/a.dita", 

      "uuid": "GUID-1293914ansd", 

      "status": "SUCCESS", 

      "exists": true 

    }, 

    { 

      "path": "/content/dam/status-fetch1/b.dita", 

      "uuid": "GUID-1883241", 

      "status": "FAILURE", 

      "exists": true 

    } 

 

  ] 

} 
```

**Valores de status:** SUCESSO, FALHA, PROCESSAMENTO, PENDENTE
