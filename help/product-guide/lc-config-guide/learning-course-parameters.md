---
title: Métricas principais de SCORM para progresso do aluno e conclusão do curso
description: Saiba mais sobre as métricas principais do SCORM para progresso do aluno e conclusão do curso
feature: Authoring
role: Admin
level: Experienced
exl-id: f25cbbbd-5d9f-47b0-9260-8062e026913d
TQID: https://experienceleague.adobe.com/ZyY9sjaqGANXlUI5l3OsP-i1Pu-es-B-iGnpPJjQYrY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 1%

---

# Métricas principais de SCORM para progresso do aluno e conclusão do curso

O artigo lista os principais parâmetros capturados em um pacote SCORM, juntamente com seus campos correspondentes e exemplos. Esses parâmetros fornecem insights críticos sobre o progresso do aluno, a conclusão do curso, os detalhes da interação e o desempenho do questionário. Os administradores podem usar essas informações para validar o rastreamento, configurar relatórios e garantir análises precisas no ambiente do LMS. Abaixo estão exemplos de valores fornecidos para cada parâmetro como ele aparece no pacote SCORM.

| **Nome do parâmetro** | **Descrição** | **Campos** | **Exemplo** |
|---|---|---|---|
| **Status de conclusão do curso** | Indica se o curso foi concluído ou não | cmi.completion_status | incompleto |
| **Contagem de tentativas** | Número de tentativas feitas pelo aluno | Contador/conteúdo de tentativas do LMS | Tentativas: 1 |
| **Local do pacote SCORM** | Favorito ou local atual no curso | cmi.location | - |
| **Conclusão do progresso** | Progresso do aluno | cmi.progress_measure | 0,87 |
| **Tempo total (tentativa)** | Tempo total gasto na tentativa atual | cmi.total_time | 0000:01:09.87 |
| **Visibilidade do índice e contagem de tópicos** | Mostra visibilidade do índice e detalhes de conclusão do tópico | Projeto.OcultarSumário, Projeto.TotalTopics, Projeto.TópicosConcluído | - |
| **Status por tópico** | Status de conclusão e aprovação para cada tópico | Estado personalizado por lição | - |
| **Estado de escolha por pergunta** | Rastreia as opções selecionadas do aluno por pergunta | value, generated_id, checked | - |
| **Pontuação geral de perguntas** | Pontuação obtida no nível de perguntas e na agregação | {&quot;score&quot;:0,&quot;maxScore&quot;:1} e % | &quot;pontuação&quot;:33.33,&quot;maxScore&quot;:100,&quot;minScore&quot;:0 |
| **Interações em cada nível de pergunta** | Detalhes da interação do aluno por pergunta | id/tipo/carimbo de data e hora/correct_response/learner_response/result/latency | - |
| **Status geral do curso** | Indica aprovação/falha e progresso geral | success_status, completion_status, score, progress_measure | Aprovado ou reprovado |
| **Detalhes do aluno** | Identifica o aluno por ID e nome | cmi.learner_id, cmi.learner_name | Albert |
| **Parâmetros do questionário** | Configurações para tempo de teste e pontuação de aprovação | cmi.max_time_allowed, cmi.scaled_pass_score, cmi.time_limit_action | Valores indefinidos ou configurados |
