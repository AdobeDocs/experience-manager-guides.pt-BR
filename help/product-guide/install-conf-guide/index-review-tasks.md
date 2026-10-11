---
title: Executar indexação para incluir todas as tarefas de revisão no painel Comentários
description: Saiba como indexar tarefas de revisão existentes para que elas apareçam juntamente com as mais recentes no menu suspenso de tarefas de revisão do painel Comentários.
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# Executar indexação para incluir todas as tarefas de revisão de um tópico no painel Comentários

O recurso [Exibir todas as tarefas de revisão para um tópico](../user-guide/review-address-review-comments.md#view-all-review-tasks-for-a-topic), disponível no painel Comentários, permite que os autores selecionem qualquer tarefa de revisão (aberta ou fechada) associada ao tópico atualmente aberto, sem alternar projetos de revisão. Quando habilitado, o painel **Comentários** do Editor inclui uma lista suspensa que lista todas as tarefas de revisão das quais o tópico faz parte, juntamente com o estado de cada tarefa e o projeto ao qual ela pertence.

Por padrão, quando esse recurso é ativado em uma instância, as tarefas de revisão são indexadas à medida que são criadas, para que fiquem automaticamente disponíveis nesse menu suspenso.

No entanto, se o recurso estiver desativado no momento em que o Experience Manager Guides for implantado em uma instância, as tarefas de revisão criadas enquanto ele permanecer desativado não serão indexadas. Como Administrador, se você ativar o recurso depois que essas tarefas de revisão já existirem, essas tarefas não aparecerão na lista suspensa até que sejam indexadas. Para disponibilizá-las, você deve executar um script único para indexar as tarefas de revisão existentes.

Execute o seguinte comando cURL uma vez para indexar tarefas de revisão existentes:

```bash
curl --location 'http://<host>:<port>/bin/guides/script/start' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic <base64-encoded-credentials>' \
--header 'Cookie: cq-authoring-mode=TOUCH' \
--data-urlencode 'jobType=review-topic-guids-migration'
```
