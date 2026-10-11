---
title: API para rastrear o pós-processamento de uma pasta ou um ativo
description: Saiba mais sobre a API para rastrear o pós-processamento de uma pasta ou um ativo
feature: Post-Processing Event Handler
role: Developer
level: Experienced
exl-id: f902fac1-2717-4696-a835-c4b0bb8add3d
TQID: 'https://experienceleague.adobe.com/Lyv-S5o-Z40bMqqIHhbxKrsmn9CCqHRnqnpiq91EjGU'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: e0bef973-8c57-4760-9b12-ec950a3c7247
    internal-label: Post processing event handler
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 8%
---
# API para rastrear o status pós-processamento de uma pasta ou um ativo

>[!NOTE]
>
> Para obter as definições mais recentes de ponto de extremidade de API REST e detalhes relacionados, exiba a documentação do Swagger em `https://<aem-author-url>/libs/fmdita/clientlibs/api-docs/index.html` (substitua `<aem-author-url>` pela URL do servidor do AEM). Como este artigo está programado para ser arquivado em outubro de 2026, recomendamos usar a documentação do Swagger a partir de agora para obter as informações mais atualizadas da API.

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

Um método GET que obtém o status de um trabalho assíncrono executado pela API acima.

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
