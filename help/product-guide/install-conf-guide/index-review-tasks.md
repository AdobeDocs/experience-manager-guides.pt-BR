---
title: Executar indexação para incluir todas as tarefas de revisão no painel Comentários
description: Saiba como indexar tarefas de revisão existentes para que elas apareçam juntamente com as mais recentes no menu suspenso de tarefas de revisão do painel Comentários.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 7d0c757b647a2e6c5e563f0ed7db6a7225769033
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
