---
title: Gerar saída da knowledge base
description: Saiba como publicar um ou mais artigos no console Mapa. Gere saída para um ou mais tópicos em um mapa DITA no AEM Guides.
exl-id: d89ce69d-8d4c-4265-bfca-60763f561afd
feature: Publishing
role: User
TQID: 'https://experienceleague.adobe.com/ZoHALUOHRMDqjz0JjR4ZQFXtYju6LQOdy1nwuzwvw5E'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: afb45297-4313-4f67-818e-bc0b03abe086
    internal-label: Knowledge base
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 43e3af5a6d753e6124acf1d56e99497f6b9c4cd9
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 0%
---
# Gerar saída da knowledge base {#id218CL05J0M1}

O Adobe Experience Manager Guides vem com um recurso de publicação baseado em artigos que permite que os usuários publiquem um ou mais artigos da Base de conhecimento simultaneamente.

Esse mecanismo também vem com um modelo de conteúdo OOTB, criado sobre os componentes principais do Adobe Experience Manager, que permite que os usuários criem um repositório baseado em conhecimento do conteúdo técnico. Esse template pode ser personalizado para atender às necessidades dos clientes.Esse mecanismo permite que os usuários criem o mapa DITA de forma aditiva e publiquem tópicos quando estiverem prontos.

Se você atualizou o conteúdo apenas para alguns tópicos no mapa DITA, nem sempre é necessário publicar o mapa inteiro. Você pode selecionar e publicar somente os tópicos atualizados.

Para uma publicação baseada em artigo, é necessário criar a predefinição de saída para o mapa DITA da knowledge base. Seu mapa deve incluir os tópicos que você deseja publicar. Também é possível aplicar condições e especificar os detalhes do AEM Sites para a predefinição de saída. Em seguida, você poderá gerar saída usando o recurso **Gerar saída**.

Execute as seguintes etapas para gerar uma saída baseada em artigo:

1. [Criar a predefinição da Base de Dados de Conhecimento](./generate-output-knowledge-base.md) para saída baseada em artigo.
1. Navegue até a guia **Artigos** e selecione os tópicos para os quais deseja gerar a saída.

   ![](images/add-preset-articles-tab_cs.png)

   >[!NOTE]
   >
   > Ao publicar no Salesforce, um ícone de aviso será exibido ao lado da guia **Artigos** se nenhum tópico for selecionado para publicação. O ícone de aviso desaparece após a seleção de um ou mais tópicos.
1. Selecione **Gerar saída** na parte superior para gerar a saída.
1. No prompt **Confirmar arquivos para publicação**, selecione os arquivos que deseja publicar e confirme selecionando **Publicar**.

   ![Novo(a) ](images/knowledge-base-confirm-files-for-publishing.png)

   Você visualizará o status do processo de geração de saída. A coluna **Tópicos** lista os tópicos para os quais a saída está sendo gerada, enquanto a coluna **Status** exibe o status de publicação de cada tópico.


   ![](images/add-preset-output-generated_cs.png)

   Para exibir a saída, feche a caixa de diálogo **Saída gerada** e selecione **Exibir saída** na página predefinida.


   >[!NOTE]
   >
   > Também é possível Renomear, Duplicar ou Excluir uma predefinição de saída existente no menu Opções.

## Publicação aprimorada do Salesforce usando processamento de back-end

A partir da versão 2026.11.0 do Experience Manager Guides as Cloud Service, uma experiência de publicação aprimorada do Salesforce estará disponível. Ele usa o processamento de back-end para oferecer suporte a trabalhos de publicação maiores, melhorar a segurança e solucionar problemas com o processo de publicação existente.

>[!NOTE]
>
> A experiência de publicação aprimorada do Salesforce está desativada por padrão. Para ativá-lo, entre em contato com a equipe de Sucesso do cliente da Adobe.

Ao publicar artigos no Salesforce usando a experiência aprimorada do, os seguintes recursos adicionais estão disponíveis:

- **Aviso para tópicos não selecionados**: um indicador de aviso aparece na guia **Artigos** da predefinição de saída da Base de Dados de Conhecimento Salesforce quando nenhum tópico é selecionado para publicação. O aviso desaparece ao selecionar um ou mais tópicos.

  ![](./images/articles-tab-salesforce-kb.png)
- **Status de publicação em nível de artigo**: após a geração de saída, o status de publicação de cada artigo, como Sucesso ou Falha, juntamente com seu tópico ou nome de arquivo, é exibido na caixa de diálogo **Resultados da publicação do Saleforce**.

  ![](./images/salesforce-publish-results-dialog.png)

- **Logs de publicação**: use a opção **Exibir log** na predefinição de saída da Base de Dados de Conhecimento Salesforce para revisar logs de publicação e solucionar erros ou avisos.

  ![](./images/salesforce-kb-view-log-option.png)

  Os logs também fornecem um resumo dos resultados da publicação.

  ![](./images/download-log-sf.png)
- **Histórico de saída**: exiba o histórico de saída de tarefas de publicação do **Console do mapa** ou da **Interface do usuário do Assets**.

  Para obter mais informações sobre como gerenciar tarefas de publicação, exiba [Gerenciar processo de geração de saída](./generate-output-manage-process.md).

  ![](./images/salesforce-publishing-output-history-panel.png)
- **Publicação de ativos otimizados:** ao publicar tópicos no Salesforce, a Experience Manager Guides verifica se os ativos referenciados, como multimídia e outros arquivos não DITA, foram modificados desde a última publicação. Somente os ativos modificados são publicados novamente, enquanto os ativos inalterados são ignorados. Isso reduz as atualizações de ativos redundantes e melhora a eficiência da publicação.

### PKCE e autenticação baseada em token de atualização

A experiência de publicação aprimorada do Salesforce também oferece suporte à atualização da autenticação baseada em token, reduzindo a necessidade de fazer logon repetidamente no Salesforce a partir do Experience Manager Guides quando os tokens de acesso expiram.

>[!NOTE]
>
> O suporte ao token de atualização está desativado por padrão. Para ativá-lo, entre em contato com a equipe de Sucesso do cliente da Adobe.

Para usar esse recurso, verifique se o **Executar solicitações a qualquer momento (refresh_token, offline_access)** está incluído nos escopos OAuth selecionados e se a **Extensão Exigir Chave de Prova para Troca de Código (PKCE) para Fluxos de Autorização com Suporte** está habilitada no aplicativo conectado do Salesforce.

A habilitação do suporte ao token de atualização no Experience Manager Guides habilita automaticamente o suporte ao PKCE. No entanto, a configuração correspondente também deve estar ativada no Salesforce para que a autenticação funcione com êxito.


**Tópico pai:**[ Trabalhar com o editor](web-editor.md)
