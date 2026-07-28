---
title: Configuração da predefinição SCORM
description: Saiba mais sobre as várias configurações de predefinição SCORM no Treinamento e aprendizado do produto
feature: Authoring
role: User
exl-id: b3000708-6120-4725-bea1-0b8e58048948
TQID: https://experienceleague.adobe.com/9WSwgksrX0fahrniOalbizWFXCqcW0QlGAHn707vm-k
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: dbb138a7804d102d1b9aa9cfbc3564e827ef199e
workflow-type: tm+mt
source-wordcount: 678
ht-degree: 0%

---

# Configurar predefinição de saída SCORM

Após a criação da predefinição, defina as configurações de predefinição SCORM. As opções de configuração predefinidas estão organizadas nas guias Geral, Conteúdo, Experiência do aluno e Publicar.

- **Geral:** usado para especificar configurações básicas de saída, como a versão com suporte, o caminho de saída, o nome de arquivo SCORM (zip), o modelo de saída e o Fluxo de Trabalho de Pós-Geração para uma nova lista suspensa de Fluxo de Trabalho de Pós-Geração que contém todos os fluxos de trabalho configurados.

  ![](assets/scorm-general-tab-v3.png){width="650"}


- **Conteúdo:** use para especificar a filtragem condicional disponível (usando DITAVAL ou usando alguma predefinição de condição) e o conjunto de variáveis.

  ![](assets/scorm-content-tab.png){width="650"}

- **Experiência do aluno**: a guia **Experiência do aluno** permite configurar como os alunos interagem com o e navegam pelo resultado do SCORM. As configurações estão organizadas em **Geral**, **Navegação** e **Questionário**, permitindo que você controle a acessibilidade do conteúdo, o fluxo de navegação e o comportamento do questionário para obter uma experiência de aprendizado personalizada.

  ![](assets/learner-experience.png){width="650"}

  - **Geral:** configure opções de nível de saída, como habilitar downloads do PDF para alunos.

    - **Permitir que os alunos baixem o curso PDF**: Quando habilitada, esta opção adiciona um ícone PDF à saída SCORM. Clicar nesse ícone permite que o aluno baixe uma versão do PDF do conteúdo do curso diretamente da saída publicada.

      **Pré-requisitos:** Antes de habilitar esta opção, verifique o seguinte:

      - O **Modelo de saída** deve ser configurado com o ícone **Incorporar PDF** no local desejado e o mesmo modelo deve ser selecionado na opção **Modelo de saída** na guia **Geral** ao configurar uma Predefinição SCORM.

        ![](assets/embed-pdf.png){width="650"}

      - A **Predefinição de PDF nativa** associada deve ter sido gerada pelo menos uma vez. Selecionar uma predefinição do PDF não gerada resultará em um erro solicitando que o usuário publique a predefinição.

    Depois que a saída SCORM é gerada com as configurações acima, a saída resultante inclui um ícone do PDF, como mostrado abaixo, permitindo que os alunos baixem o PDF do curso.

    ![](assets/pdf-icon.png){width="650"}

  - **Navegação:** defina como os alunos se movem pelo curso, incluindo a progressão sequencial, as condições de conclusão obrigatórias e as regras para desbloquear o botão **Avançar**.

    - **Os alunos devem avançar pelo conteúdo em ordem sequencial**: garante que os alunos percorram o curso em uma sequência fixa e não possam pular para a frente ou saltar entre os componentes do curso.
    - **Desabilitar o botão Avançar se o aluno não passar no questionário**: impede o aluno de ir para a próxima seção/página até que ele passe no questionário.
    - **Os alunos devem tentar responder todas as perguntas para continuar**: exige que os alunos tentem responder todas as perguntas antes de enviarem o questionário, evitando envios incompletos.
    - **Bloquear o progresso até a conclusão**: impede a navegação pelo curso até que todas as subcondições configuradas abaixo dele sejam satisfeitas, desabilitando o botão **Avançar** no curso.
      - **Todos os elementos interativos abertos**: exige que o aluno abra todos os elementos interativos da página.
      - **Todas as mídias assistidas**: exige que o aluno assista a todas as mídias de vídeo/áudio na página.
      - **Tentativa de todas as verificações de conhecimento**: exige que o aluno tente todas as perguntas de verificação de conhecimento da página.
      - **Tempo mínimo gasto na página**: exige que o aluno permaneça na página pelo menos pela duração especificada antes que o botão Avançar seja habilitado. Depois de habilitado, você precisa inserir o tempo necessário, conforme mencionado abaixo.
        - **Tempo necessário (segundos)**: o número mínimo de segundos (por exemplo, `30`) que um aluno deve permanecer na página para que essa condição seja atendida.

  - **Questionário:** configure o comportamento relacionado ao questionário, como a aleatoriedade da ordem das perguntas e as opções de resposta, para reduzir a previsibilidade entre tentativas.

    - **Randomizar a ordem das perguntas para cada tentativa**: exibe as perguntas dos questionários em uma ordem diferente para cada tentativa, ajudando a reduzir a previsibilidade.
    - **Randomizar opções de resposta para cada tentativa**: embaralha as opções de resposta para cada pergunta em cada tentativa, reduzindo as chances de adivinhação.

- **Publicar no LMS:** Use essa configuração para publicar seu conteúdo diretamente no Adobe Learning Manager (ALM). Na lista suspensa **Servidor de publicação**, selecione **Adobe Learning Manager** e escolha o **Perfil de publicação** necessário que foi configurado anteriormente nas configurações do Workspace. O perfil selecionado é usado para estabelecer a conexão e carregar o conteúdo gerado no ALM.

  >[!NOTE]
  >
  > Antes de publicar conteúdo no ALM, você deve configurar um perfil de publicação do Adobe Learning Manager. Para obter detalhes, consulte [Publicar perfis](../lc-config-guide/lc-folder-profile.md).

  ![](assets/scorm-publish-lms.png){width="650"}

Depois que todas as alterações forem configuradas, salve as alterações da predefinição SCORM usando **Salvar** no canto direito da barra de ferramentas da página de predefinições SCORM.
