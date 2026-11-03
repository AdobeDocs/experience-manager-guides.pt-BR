---
title: Criar tópicos e mapas com o Assistente de IA
description: Saiba como redigir novos tópicos e mapas DITA a partir de suas notas, especificações ou conteúdo colado com o AI Assistant e, em seguida, analisá-los antes de salvar.
source-git-commit: b9dc9674244cbcf20fba1f51665afb4440172cdb
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%
---

# Criar o primeiro rascunho do conteúdo

A habilidade **Criar** no modo de agente do Assistente de IA ajuda a gerar o primeiro rascunho de conteúdo estruturado de notas, especificações, imagens do quadro de comunicações, capturas de tela ou outros materiais de referência disponíveis. A habilidade identifica automaticamente o tipo de tópico DITA apropriado, como Conceito, Tarefa, Referência ou Solução de problemas, com base no conteúdo e nos modelos de tópico disponíveis em seu repositório, reduzindo o esforço manual necessário para estruturar e criar conteúdo.

Você pode anexar um arquivo, selecionar um arquivo existente como referência para tom e estilo e especificar a pasta onde deseja salvar o conteúdo gerado. Para criar o primeiro rascunho do conteúdo desejado, siga estas etapas:

1. Faça logon no Experience Manager Guides.
1. Na página inicial, selecione **Assistente de IA** na barra de navegação. Certifique-se de que o [Assistente de IA no modo Agente](../install-conf-guide/workspace-settings.md) esteja habilitado pelo administrador.

1. Selecione **Criar** no painel Assistente de IA.

   O prompt inicial aparece na caixa de prompt: *Criar conteúdo de rascunho referindo-se aos arquivos anexados e tendo um tom de conteúdo semelhante a [arquivo]*

1. Anexe suas notas, especificações ou outros arquivos de referência ao prompt usando um dos seguintes métodos:

   - **Usando atalho**: Digite `/` no campo Prompt e escolha **Adicionar referência do repositório** para escolher o arquivo do Repositório (ou **Adicionar arquivos do dispositivo** para carregar o arquivo do seu computador).

   - **Usando o ícone Anexar arquivos ou adicionar contexto (+)**: adicionar arquivos do sistema local.

   - **Arrastar e soltar**: arraste e solte o arquivo que deseja rascunhar do sistema diretamente no espaço de prompt.

1. *(Opcional)* No prompt inicial, selecione `[file]`. Selecione o tópico existente cujo tom você deseja que o rascunho corresponda. Você pode escolher o tópico do repositório ou de uma coleção. O nome do tópico substitui `[file]` no prompt.

   ![Selecione o espaço reservado para arquivo para escolher o tópico](images/sample-create.png){width="650"}

1. Selecione **Enviar**.

   O Assistente de IA analisa o conteúdo e lista cada etapa concluída.

1. Responda a qualquer pergunta de acompanhamento do Assistente de IA para fornecer os detalhes necessários para gerar o conteúdo.

   ![Selecione o espaço reservado para arquivo para escolher o tópico](images/folder-create.png){width="650"}

1. Selecione **Visualizar** para revisar o tópico gerado.

   Verifique cada rascunho em relação ao material de origem e aos tipos de tópico solicitados.

   ![](images/preview-create.png)

1. Selecione uma das opções a seguir:

   - **Aceitar** para salvar o tópico na pasta confirmada
   - **Rejeitar** para descartar as alterações sem salvar nada. Você pode fornecer um motivo para rejeitar o conteúdo de rascunho e inserir um prompt especificando as alterações desejadas. O Assistente de IA usa seu feedback para revisar o conteúdo de rascunho.

     O tópico agora está disponível em seu repositório.

     ![](images/accept-reject-create.png)

Depois que o Assistente de IA criar um tópico, você poderá abri-lo no Editor e refinar o conteúdo usando prompts de acompanhamento. Isso permite melhorar o tópico interativamente sem iniciar uma nova conversa. Cada alteração proposta é exibida na visualização com o **Controle de Alterações** habilitado, permitindo que você revise as modificações antes de aplicá-las.

Por exemplo, para refinar o título de um tópico gerado:

1. Abra o tópico recém-criado no Editor na caixa de diálogo Assistente do AI.

   ![](images/editor-create-agent.png)

1. No painel Assistente de IA, insira um prompt de acompanhamento, como `Improve the title of this topic to make it generic.`

   ![](images/follow-up-prompt.png)

1. Selecione **Enviar**.

   O Assistente de IA analisa e sugere um novo título.

1. Selecione **Visualizar** para revisar as alterações propostas.

   A visualização exibe o título revisado com alterações controladas, destacando o que foi modificado.

   ![](images/review-change.png)

1. Selecione **Aceitar** para aplicar as alterações ao tópico.

   ![](images/final-output-create.png)

Você pode continuar refinando outros elementos do tópico, como parágrafos, etapas ou tabelas, fornecendo prompts adicionais na mesma conversa.





