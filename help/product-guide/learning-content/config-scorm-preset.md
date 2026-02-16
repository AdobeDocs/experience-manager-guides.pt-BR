---
title: Configuração da predefinição SCORM
description: Saiba mais sobre as várias configurações de predefinição SCORM no Treinamento e aprendizado do produto
feature: Authoring
role: User
exl-id: b3000708-6120-4725-bea1-0b8e58048948
source-git-commit: 3fdedee6e07908632bcf1b804805fcac7925c4e0
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Configurar predefinição de saída SCORM

Após a criação da predefinição, defina as configurações de predefinição SCORM. As opções de configuração predefinidas são organizadas nas guias Geral, Conteúdo e Publicar.

- **Geral:** usado para especificar as configurações básicas de saída, como a versão suportada, o caminho de saída, o nome do arquivo ZIP, o modelo de saída e outras opções relacionadas à experiência do aluno.

  ![](assets/scorm-general-tab-v3.png){width="650" align="left"}

  **Experiência do aluno**

   - **Os alunos devem avançar pelo conteúdo em ordem sequencial**: garante que os alunos avancem pelo questionário em uma sequência fixa e não possam pular adiante ou saltar entre perguntas.
   - **Os alunos devem tentar responder todas as perguntas para continuar**: exige que os alunos tentem responder todas as perguntas antes de enviarem o questionário, evitando envios incompletos.
   - **Randomizar a ordem das perguntas para cada tentativa**: exibe as perguntas dos questionários em uma ordem diferente para cada tentativa, ajudando a reduzir a previsibilidade.
   - **Randomizar opções de resposta para cada tentativa**: embaralha as opções de resposta para cada pergunta em cada tentativa, reduzindo a chance de adivinhação com base na posição.
   - **Usar id de pergunta nos relatórios de questionários**: inclui a ID de pergunta exclusiva nos relatórios de questionários, facilitando o rastreamento, a análise e o mapeamento dos resultados para perguntas específicas.
   - **Fluxo de Trabalho de Pós-Geração**: ao escolher essa opção, uma nova lista suspensa de Fluxo de Trabalho de Pós-Geração que contém todos os fluxos de trabalho configurados é exibida.

- **Conteúdo:** use para especificar a filtragem condicional disponível (usando DITAVAL ou usando alguma predefinição de condição) e o conjunto de variáveis.

  ![](assets/scorm-content-tab.png){width="650" align="left"}

- **Publicar:** use essa configuração somente se desejar publicar a saída na Nuvem SCORM para acesso direto.

  ![](assets/scorm-publish-tab.png){width="650" align="left"}

Depois que todas as alterações forem configuradas, salve as alterações da predefinição SCORM usando **Salvar** no canto direito da barra de ferramentas da página de predefinições SCORM.
