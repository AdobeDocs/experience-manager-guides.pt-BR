---
title: Métricas principais de SCORM para progresso do aluno e conclusão do curso
description: Saiba mais sobre as métricas principais do SCORM para progresso do aluno e conclusão do curso
feature: Authoring
role: Admin
level: Experienced
source-git-commit: 0dff380131dadc971f257eb464700392328164e5
workflow-type: tm+mt
source-wordcount: '279'
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
| **Tempo total (tentativa)** | Tempo total gasto na tentativa atual | cmi.total_time | 0000:01:09,87 |
| **Visibilidade do índice e contagem de tópicos** | Mostra visibilidade do índice e detalhes de conclusão do tópico | Projeto.OcultarSumário, Projeto.TotalTopics, Projeto.TópicosConcluído | - |
| **Status por tópico** | Status de conclusão e aprovação para cada tópico | Estado personalizado por lição | - |
| **Estado de escolha por pergunta** | Rastreia as opções selecionadas do aluno por pergunta | value, generated_id, checked | - |
| **Pontuação geral de perguntas** | Pontuação obtida no nível de perguntas e na agregação | {&quot;score&quot;:0,&quot;maxScore&quot;:1} e % | &quot;pontuação&quot;:33.33,&quot;maxScore&quot;:100,&quot;minScore&quot;:0 |
| **Interações em cada nível de pergunta** | Detalhes da interação do aluno por pergunta | id/tipo/carimbo de data e hora/correct_response/learner_response/result/latency | - |
| **Status geral do curso** | Indica aprovação/falha e progresso geral | success_status, completion_status, score, progress_measure | Aprovado ou reprovado |
| **Detalhes do aluno** | Identifica o aluno por ID e nome | cmi.learner_id, cmi.learner_name | Albert |
| **Parâmetros do questionário** | Configurações para tempo de teste e pontuação de aprovação | cmi.max_time_allowed, cmi.scaled_pass_score, cmi.time_limit_action | Valores indefinidos ou configurados |