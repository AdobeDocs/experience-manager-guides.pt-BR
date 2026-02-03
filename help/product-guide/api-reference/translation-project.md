---
title: Criar projeto de tradução
description: Saiba como criar um projeto de tradução de API
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 41dd3dee5f9d64fb5c58b5b302cc9759e48e3631
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 17%

---

# Criar projeto de tradução

Um método POST que ajuda a criar um projeto de tradução aceitando os detalhes necessários do projeto.

## URL de solicitação

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/create`

## Tipo de solicitação

POST

## Parâmetros de solicitação

| Nome | Tipo | Descrição |
|----|----|-----------|
| `type` | String | newTranslationProject, xliffTranslationProject, newMultiLingualTranslationProject, addToExistingProject, newScopingTranslationProject |
| `versionDetails`, `versionSelector` | String | Linha de base, latestVersion, versionAsOfDate |
| `language` | String | Idiomas separados por vírgulas &quot;de&quot;, &quot;fr&quot; |
| `map.id` | String | GUID do mapa de origem a ser traduzido |
| `map.path` | String | Caminho do mapa de origem a ser traduzido |
| `referenceType` | String | Indireto, Direto |
| `fileType` | String | Mapa, Tópico, Outros |
| `documentState` | String | pode ser uma das listas atribuídas pelo usuário no perfil do mapa |
| `translationStatus` | String | Fora de sincronia, Em sincronia, Atualizado, Desatualizado, Em andamento, Cópia ausente, NENHUM, N/D |

>[!NOTE]
>
>Você pode usar `map.id` ou `map.path` ao criar um projeto de tradução.

## Exemplo de solicitação

```JSON
{
  "title": "Test Project 1 on Dec 5",
  "type": "newTranslationProject",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en",
      "path": "/content/dam/ajay-test/lang/en/m2.ditamap"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "latestVersion"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
   ]
```

## Valores de resposta

```JSON
{
  "executionId": "5c13c571-3407-46d5-8f45-50ea9e05a212",
  "path": "/content/projects/test_project_1_ondec5"
}
```

**Códigos de resposta**

- 200 Êxito
- Entrada 400 inválida
- 401 Acesso não autorizado
- Erro interno do servidor 500

## Solicitações de exemplo

### Adicionar a um projeto existente

```json
{
  "title": "Add to existing Project",
  "type": "addToExistingProject",
  "path": "/content/projects/test_project_1_existing",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "versionAsOfDate",
      "version": "2025-12-05T10:30:00+01:30"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

### Adicionar a um projeto existente com Linha de Base

```json
{
  "title": "Add to existin project Project with baseline",
  "type": "addToExistingProject",
  "path": "/content/projects/existing_project_path",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "baseline",
      "version": "test1"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": ["Direct"] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

## Status de criação do projeto de tradução

Uma API do GET que rastreia o status de tradução de um projeto de tradução recém-criado.

## URL de solicitação

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/creationstatus`

## Tipo de solicitação

GET

## Parâmetros de solicitação

| Nome | Tipo | Descrição |
|----|----|-----------|
| `path` | String | Caminho do projeto |
| `languageStatusMap` | String | Para cada idioma solicitado, retorna o status de conclusão: Em andamento, Concluído, Com falha, Ignorado |


## Exemplo de solicitação

```json
{
  "path": "/content/projects/test_project_1_ondec5",
  "languageStatusMap": {
    "de": "Completed"
  }
}
```



