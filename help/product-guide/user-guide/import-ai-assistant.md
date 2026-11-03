---
title: Importar documentos como tópicos com o Assistente de IA
description: Saiba como converter arquivos do PDF, Word e Markdown em tópicos DITA e um mapa com o AI Assistant e revise o resultado antes de salvá-lo.
source-git-commit: f936d474c6efcea89b244ccd25e03b065a478250
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---

# Importar conteúdo com o Assistente de IA

A habilidade **Importar** no modo de agente do Assistente de IA ajuda a converter arquivos PDF, Word ou Markdown existentes em tópicos DITA estruturados, com a opção de gerar mapas DITA com base na entrada do usuário. Ele simplifica a assimilação de conteúdo de formatos não estruturados para estruturados no Adobe Experience Manager Guides ao reduzir o esforço manual necessário para recriar, estruturar e organizar o conteúdo.

## Importar um arquivo

É possível importar arquivos do repositório de dispositivo ou conteúdo, especificar o nível de cabeçalho que define o início de um novo tópico e escolher a pasta de destino para o conteúdo importado. Para importar um arquivo, siga estas etapas:

1. Faça logon no Experience Manager Guides.
1. Na página inicial, selecione **Assistente de IA** na barra de navegação. Certifique-se de que o [Assistente de IA no modo Agente](../install-conf-guide/workspace-settings.md) esteja habilitado pelo administrador.
1. Selecione **Importar** no painel Assistente de IA. Você também pode usar outros prompts como *Converter este docx em tópicos DITA* para um arquivo do Word ou *Converter este markdown em tópicos DITA* para um arquivo do Markdown.

   O prompt inicial *Ajude-me a importar conteúdo do arquivo anexado do PDF* aparece na caixa de prompt.

1. Anexe o arquivo ao seu prompt usando um dos seguintes métodos:

   - **Usando atalho**: Digite `/` no campo Prompt e escolha **Adicionar referência do repositório** para escolher o arquivo do Repositório (ou **Adicionar arquivos do dispositivo** para carregar o arquivo do seu computador).

   - **Usando o ícone Anexar arquivos ou adicionar contexto (+)**: adiciona arquivos do sistema local para fornecer o conteúdo de importação.

   - **Arrastar e soltar**: arraste e solte o arquivo que deseja importar do sistema diretamente no espaço de prompt.

     ![](images/attach-import.png)

1. Selecione **Enviar**.

   O Assistente de IA analisa o arquivo e lista cada etapa concluída.

1. Selecione e confirme a pasta onde deseja salvar os tópicos importados.

   ![](images/folder-import.png)

1. Escolha o nível de cabeçalho que se tornará um tópico. Por exemplo, H2 como mostrado na captura de tela.

   Responda a quaisquer perguntas de acompanhamento adicionais que pareçam fornecer os detalhes necessários para o processo de importação.

   ![](images/heading-import.png)

1. Selecione **Confirmar**.

   O Assistente de IA inicia a conversão do arquivo. A habilidade Importar identifica e atribui automaticamente os tipos de tópicos DITA apropriados, como Tarefa, Solução de problemas e muito mais, com base no conteúdo importado.

1. Selecione **Visualizar** para revisar os tópicos gerados e o mapa.

   Verifique se cada tópico começa no cabeçalho esperado e se a ordem do mapa corresponde ao arquivo original. Também é possível verificar o código Source dos dados importados usando a guia Source.

   ![](images/preview-import.png)

1. Selecione uma das opções a seguir:

   - **Aceitar** para salvar todos os tópicos e mapear para a pasta confirmada.
   - **Rejeitar** para descartar a importação sem salvar nada. Você pode fornecer um motivo para rejeitar a importação e inserir um prompt especificando as alterações desejadas. O Assistente de IA usa seu feedback para revisar a importação.

   Os tópicos e o mapa agora estão disponíveis em seu repositório.

   ![](images/accept-reject-import.png)

Após a conclusão da conversão, o Assistente de IA abre uma pré-visualização dos tópicos e mapas gerados. Você pode navegar até o mapa e os tópicos correspondentes diretamente da caixa de diálogo do Assistente de IA.

## Importar conteúdo colado como tópicos

Colar conteúdo de uma página da Web, Word, Google Docs ou wiki permite importar sem salvar um arquivo primeiro. O conteúdo formatado mantém cabeçalhos, listas e tabelas.

Para importar conteúdo colado:

1. Faça logon no Experience Manager Guides.
1. Na página inicial, selecione **Assistente de IA** na barra de navegação. Certifique-se de que o Assistente de IA no modo Agente está ativado pelo seu administrador.
1. Copie o conteúdo da página da Web, do Word, do Google Docs ou da wiki.
1. Cole o conteúdo na caixa de prompt.

   O conteúdo formatado com mais de 2.000 caracteres é anexado como Markdown, portanto sua estrutura é transferida.

   ![](images/pasted-import.png)

1. Insira um prompt que especifique o conteúdo desejado.

   Por exemplo, insira *Importar a página colada no DITA* ou *Transformar o conteúdo colado em tópicos DITA e um mapa*

1. Selecione **Enviar**.

O Assistente do AI solicita que você selecione o nível de cabeçalho para dividir o conteúdo em tópicos e especifique a pasta de destino. As etapas restantes são as mesmas da importação de um arquivo anexado, incluindo a revisão e a confirmação do workflow de importação para gerar tópicos DITA e um mapa.



