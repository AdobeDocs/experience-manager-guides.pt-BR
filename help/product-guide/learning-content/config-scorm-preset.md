---
title: Configuração da predefinição SCORM
description: Saiba mais sobre as várias configurações de predefinição SCORM no Treinamento e aprendizado do produto
feature: Authoring
role: User
exl-id: b3000708-6120-4725-bea1-0b8e58048948
TQID: https://experienceleague.adobe.com/9WSwgksrX0fahrniOalbizWFXCqcW0QlGAHn707vm-k
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: f7c0b10f032c2584fb6e951da898faaeb4ca7aaf
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 0%

---

# Configurar predefinição de saída SCORM

Após a criação da predefinição, defina as configurações de predefinição SCORM. As opções de configuração predefinidas são organizadas nas guias Geral, Conteúdo e Publicar.

- **Geral:** usado para especificar as configurações básicas de saída, como a versão suportada, o caminho de saída, o nome do arquivo ZIP, o modelo de saída e outras opções relacionadas à experiência do aluno.

  ![](assets/scorm-general-tab-v3.png){width="650"}

  **Experiência do aluno**

   - **Os alunos devem avançar pelo conteúdo em ordem sequencial**: garante que os alunos avancem pelo questionário em uma sequência fixa e não possam pular adiante ou saltar entre perguntas.
   - **Os alunos devem tentar responder todas as perguntas para continuar**: exige que os alunos tentem responder todas as perguntas antes de enviarem o questionário, evitando envios incompletos.
   - **Randomizar a ordem das perguntas para cada tentativa**: exibe as perguntas dos questionários em uma ordem diferente para cada tentativa, ajudando a reduzir a previsibilidade.
   - **Randomizar opções de resposta para cada tentativa**: embaralha as opções de resposta para cada pergunta em cada tentativa, reduzindo a chance de adivinhação com base na posição.
   - **Usar id de pergunta nos relatórios de questionários**: inclui a ID de pergunta exclusiva nos relatórios de questionários, facilitando o rastreamento, a análise e o mapeamento dos resultados para perguntas específicas.
   - **Fluxo de Trabalho de Pós-Geração**: ao escolher essa opção, uma nova lista suspensa de Fluxo de Trabalho de Pós-Geração que contém todos os fluxos de trabalho configurados é exibida.

- **Conteúdo:** use para especificar a filtragem condicional disponível (usando DITAVAL ou usando alguma predefinição de condição) e o conjunto de variáveis.

  ![](assets/scorm-content-tab.png){width="650"}


- **Publicar no LMS:** Use essa configuração para publicar seu conteúdo diretamente no Adobe Learning Manager (ALM). Na lista suspensa **Servidor de publicação**, selecione **Adobe Learning Manager** e escolha o **Perfil de publicação** necessário que foi configurado anteriormente nas configurações do Workspace. O perfil selecionado é usado para estabelecer a conexão e carregar o conteúdo gerado no ALM.

  >[!NOTE]
  >
  > Antes de publicar conteúdo no ALM, você deve configurar um perfil de publicação do Adobe Learning Manager. Para obter detalhes, consulte [Publicar perfis](../lc-config-guide/lc-folder-profile.md).

  ![](assets/scorm-publish-lms.png){width="650"}

Depois que todas as alterações forem configuradas, salve as alterações da predefinição SCORM usando **Salvar** no canto direito da barra de ferramentas da página de predefinições SCORM.
