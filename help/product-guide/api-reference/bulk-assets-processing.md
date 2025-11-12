---
title: API para iniciar o processamento em massa de ativos
description: Saiba mais sobre a API para iniciar o processamento em massa de ativos
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: e2eca63a5dd56e358aeea047b37f4b0f88dc720b
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 8%

---

# API para iniciar o processamento em massa de ativos

Um método POST que inicia o processamento de ativos em massa para um caminho especificado. Essa API oferece suporte ao processamento de ativos baseado em JCR e em banco de dados. Ele inicia um trabalho assíncrono que processa todos os ativos no caminho determinado e em seus subcaminhos. Após a inicialização, a API retorna uma ID de processamento exclusiva, que pode ser usada para rastrear o status da tarefa.

**Solicitar URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process`

**Solicitar Parâmetros**

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `path` | String | Sim | Caminho absoluto da pasta ou do ativo no repositório do AEM a ser processado. |
| `excludedPaths` | String | Não | Lista de caminhos a serem excluídos do processamento |
| `type` | String | Sim | Tipo de processamento a ser executado. Por exemplo: ASSET_PROCESSING. |

**Solicitar Exemplo**

```JSON
{
  "path": "/content/dam/status-fetch1",
  "excludedPaths": [
    "content/dam/status-fetch1/excluded-folder"
  ],
  "type": "ASSET_PROCESSING"
}
```

**Valores de resposta**

processingId para sondar para obter o status de trabalho assíncrono.

```JSON
{
  "processingId": "akjhdfalkj1132"
}
```

**Códigos de resposta**

- 200 Êxito
- Entrada 400 inválida
- 401 Acesso não autorizado
- Erro interno do servidor 500

## Verificar status do trabalho

Um método do GET que recupera o status atual de um trabalho de processamento de ativos iniciado anteriormente.

**Solicitar URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/status`

**Solicitar Parâmetros**

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `processingId` | String | Sim | Identificador exclusivo do trabalho cujo status está sendo consultado. |

**Exemplo de resposta**

```JSON
{
  "processingId": "string",
  "path": "string",
  "excludedPaths": ["string"],
  "status": "WAITING",
  "triggeredCount": 0,
  "startedAt": 0,
  "completedAt": 0,
  "hasLogs": true,
  "createdBy": "string",
  "type": "ASSET_PROCESSING",
  "migrationSet": {
    "totalFiles": 0,
    "calculationStatus": "WAITING"
  },
  "eta": {
    "value": 0,
    "unit": "string"
  },
  "comments": "string",
  "restartable": true,
  "resumable": true,
  "cancellable": true
}
```

**Códigos de resposta**

- 200 Êxito
- Entrada 400 inválida
- 401 Acesso não autorizado
- Erro interno do servidor 500

## Exibir logs do trabalho

Um método GET que recupera logs para uma determinada ID de trabalho. Essa API busca os logs do trabalho de processamento de ativos. A processingid é obrigatória. A API fornece parâmetros de deslocamento e limite, bem como uma estratégia de redução.

**Solicitar URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs`

**Solicitar Parâmetros**

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `processingId` | String | Sim | Identificador exclusivo do trabalho cujos logs devem ser visualizados. |
| `offset` | Número inteiro | Não | O ponto inicial (número da linha) do qual os logs devem ser lidos. Usado para paginação para ignorar as primeiras N linhas. |
| `limit` | Número inteiro | Não | O número máximo de linhas de log a serem buscadas. |
| `tail` | Número inteiro | Não | Número de linhas de log a serem recuperadas do final. |


**Exemplo de resposta**

```JSON
{
  "lines": [
    "string"
  ],
  "limit": 0,
  "offset": 0,
  "hasMore": true
}
```

**Códigos de resposta**

- 200 Êxito
- Entrada 400 inválida
- 401 Acesso não autorizado
- Erro interno de servidor 500


## Baixar logs do trabalho

Um método GET que baixa o arquivo de log de um determinado trabalho como um ZIP.

**Solicitar URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs/download`

**Solicitar Parâmetros**

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `processingId` | String | Sim | Identificador exclusivo do trabalho cujo arquivo de log precisa ser baixado. |


**Exemplo de resposta**

```JSON
{
  "logFilePaths": [
    "string"
  ]
}
 
```

**Códigos de resposta**

- Entrada 400 inválida
- 401 Acesso não autorizado
- Erro interno de servidor 500

## Cancelar tarefa

Uma API POST que cancela uma solicitação contínua de processamento de ativos em massa. Se o trabalho não for encontrado, a API retornará um erro.

**Solicitar URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/cancel`

**Solicitar Parâmetros**

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `processingId` | String | Sim | Identificador exclusivo do trabalho cujo status está sendo consultado. |


**Códigos de resposta**

- 200 Êxito
- Entrada 400 inválida
- 401 Acesso não autorizado
- Erro interno de servidor 500


## Retomar trabalho

Uma API POST que reinicia uma solicitação de processamento de ativos em massa cancelada ou que falhou anteriormente. Ele reinicia o processamento do último ponto de verificação. Se o trabalho não for encontrado ou estiver em execução no momento, a API retornará um erro.

**Solicitar URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/resume`

**Solicitar Parâmetros**

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `processingId` | String | Sim | Identificador exclusivo do trabalho cujo status está sendo consultado. |


**Códigos de resposta**

- 200 Êxito
- Entrada 400 inválida
- 401 Acesso não autorizado
- Erro interno de servidor 500

## Exibir histórico de tarefas

Uma API do GET que retorna as últimas execuções &quot;N&quot; de pós-processamento de ativos.

**Solicitar URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/history`

**Solicitar Parâmetros**

Nenhum. Esta solicitação GET recupera o histórico de processos sem exigir parâmetros de entrada.

**Exemplo de resposta**

```JSON
{
  "executionHistory": [
    {
      "processingId": "165f1de6-68c4-4dcd-9223-2b7242b62306",
      "path": "/content/dam/22858",
      "status": "SUCCESS",
      "triggeredCount": 6,
      "startedAt": 1761291362776,
      "completedAt": 1761291364026,
      "hasLogs": true,
      "createdBy": "user",
      "type": "ASSET_PROCESSING",
      "migrationSet": {
        "totalFiles": 6,
        "calculationStatus": "SUCCESS"
      },
      "eta": {
        "value": 0,
        "unit": "SECONDS"
      },
      "comments": "",
      "filter": {
        "fileTypes": [],
        "filterProcessedAssets": false
      },
      "cancellable": false,
      "resumable": false,
      "restartable": true
    }
  ]
}
```



