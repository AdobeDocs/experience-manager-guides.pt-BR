---
title: Configurar estados dos documentos
description: Saiba como Configurar estados dos documentos
exl-id: d7603b4e-aae4-48ca-be84-8edb51626405
feature: Document State
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 0%

---

# Configurar estados dos documentos {#id181GB0400UI}

O AEM Guides permite definir os estados dos documentos para os tópicos DITA de acordo com os requisitos da organização. Você pode definir diferentes estados do seu documento do início ao fim. Por exemplo, o primeiro estado pode ser Rascunho e pode ser movido para Revisão, Aprovado, Traduzido e finalmente para Publicado.

Há duas maneiras pelas quais um tópico pode passar de um estado para outro: manual e automática. Os estados do documento definidos em um perfil podem ser usados para alterar manualmente o estado do documento. Isso pode ser feito a partir da página Propriedades de um arquivo de tópico. Além disso, você pode definir quem pode mover o documento de um estado para outro estado. Por exemplo, um autor pode criar um documento e o estado padrão do documento pode ser Rascunho. Quando o autor envia o documento para revisão, ele pode alterar o estado do documento para Em revisão. O revisor pode alterar o estado do documento para Aprovado ou Rascunho novamente com base no processo de revisão. Se o documento for Aprovado, o editor poderá alterar o estado do documento para Traduzido ou Publicado, dependendo do fluxo de trabalho.

>[!NOTE]
>
> Se um usuário pertencer ao grupo *administradores*, ele poderá alterar o estado de um documento de qualquer estado, independentemente das transições de estado do documento definidas no sistema.

## Criar um estado de documento

O AEM Guides é enviado com um conjunto de estados de documento padrão. Esses estados são:

- Rascunho
- Editar
- Em revisão
- Aprovado
- Revisado
- Concluído

Esses estados padrão estão disponíveis para todos os tópicos DITA criados no DAM. Você pode criar seus próprios estados dos documentos e atribuí-los a uma pasta específica. Todos os arquivos DITA criados nessa pasta terão acesso aos estados de documento recém-criados.

Para criar estados de documento usando o Perfil de pasta, execute as seguintes etapas:

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas.
1. Clique no bloco Estados do documento.

   A página Estados da Assets é exibida. Por padrão, a página mostra um perfil padrão.

1. Clique em **Criar Perfil** e insira os seguintes detalhes:
   - Insira o nome do perfil no campo Profile.
   - Especifique o caminho no qual deseja aplicar o novo perfil.
   - Especifique os estados do documento nos **Estados permitidos** em **Estados**. Os estados padrão do documento são Rascunho, Editar, Em revisão, Aprovado e Concluído.-

     Clique no botão **Adicionar** para adicionar um estado de documento.

      - Clique no ícone Excluir para excluir um estado de documento.

     >[!NOTE]
     >
     > Não exclua um estado de documento se os documentos ainda estiverem nesse estado. Se você excluir um estado de documento, não poderá alterar o estado desses documentos, a menos que pertença ao grupo de usuários *administrador*.

   - Especifique o estado inicial do documento no **Estado Inicial**.
   - Especifique o estado final do documento no **Estado Final**.
   - Especifique a transição de estado do documento em **De** e **Para** em **Transição de Estado**.

      - Especifique os usuários e grupos de usuários que podem alterar o estado do documento em **Grupos**.

      - Clique no botão **Adicionar** para adicionar uma transição de estado.

      - Clique no ícone Excluir para excluir uma transição de estado.

     >[!NOTE]
     >
     > Não exclua uma transição de estado se os documentos ainda estiverem no estado `From`. Se você excluir uma transição de estado, não poderá alterar o estado desses documentos, a menos que pertença ao grupo de usuários *administrador*.

1. Clique em **Concluído**.

## Criar uma cópia de um perfil de estado de documento

Dependendo do seu requisito, você pode criar uma cópia de um perfil de estado de documento existente. Você pode usar a cópia como base para criar outro perfil de documento.

Para criar uma cópia de um perfil de estado do documento, execute as seguintes etapas:

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas.
1. Clique no bloco Estados do documento.

   A página Estados da Assets é exibida.

1. Selecione o perfil de estado do documento que você deseja duplicar e clique em **Duplicar Perfil**.
1. Faça as alterações necessárias e clique em **Concluído**.

## Excluir um estado de documento ou transição de estado

>[!NOTE]
>
> Não exclua um estado de documento ou transição de estado se os documentos ainda estiverem no estado ou em transição de estado. Se você excluir uma transição de estado ou estado, não poderá alterar o estado desses documentos, a menos que pertença ao grupo de usuários *administrador*.

Execute as seguintes etapas para excluir um estado de documento ou uma transição de estado de um perfil de estado de documento:

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas.
1. Clique no bloco Estados do documento.

   A página Estados da Assets é exibida.

1. Selecione o perfil de estado do documento do qual deseja excluir o estado do documento e clique em **Editar Perfil**.
1. Exclua o estado do documento ou a transição de estado e clique em **Concluído**.

## Excluir um perfil de estado de documento

Para excluir um perfil de estado do documento, execute as seguintes etapas:

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas.
1. Clique no bloco Estados do documento.

   A página Estados da Assets é exibida.

1. Selecione o perfil de estado do documento que você deseja excluir e clique em **Excluir Perfil**.

## Automatizar a alteração do estado do documento

Se não quiser alterar manualmente os estados do documento, você poderá criar um fluxo de trabalho e automatizar a alteração do estado do documento.

>[!NOTE]
>
> Os workflows automatizados devem estar em conformidade com os estados e as transições do documento definidos na configuração. O sistema não executa nenhuma verificação de alterações de estado feitas por meio de workflows automatizados.

Execute as seguintes etapas para automatizar a alteração do estado do documento:

1. Abra a página de fluxo de trabalho no URL do servidor AEM.

   `<AEM_Server_URL>:<port>/workflow`

1. Abra um workflow na página de workflow. Por exemplo, Revisar tópico.
1. Selecione **Etapa do processo** na seção **Fluxo de trabalho** da caixa de diálogo do AEM e arraste e solte no fluxo de trabalho.

   ![](assets/process-step-workflow.png)

1. Clique duas vezes no processo e abra a caixa de diálogo **Propriedades da etapa**.
1. Insira os seguintes detalhes na guia **Processo** da caixa de diálogo e clique em OK:
   - Selecione **Definir estado do documento para qualquer ativo DAM** no menu suspenso Processo.
   - Marque a caixa de seleção Avanço do manipulador.
   - Digite o nome do estado do documento na caixa de texto **Argumentos**.

     >[!NOTE]
     >
     > Certifique-se de inserir o estado correto do documento na caixa de texto Argumento. Se você inserir um nome incorreto, o documento será definido para o estado de documento incorreto.

1. Clique em **Salvar** para salvar o fluxo de trabalho.

## Ativar fluxo de trabalho de aprovação

O AEM Guides fornece fluxo de trabalho para aprovação de documentos, que ajuda a controlar o ciclo de vida do processo de desenvolvimento de documentos. Para habilitar o fluxo de trabalho de aprovação, execute as seguintes etapas:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Navegue até o arquivo de configuração padrão disponível no seguinte local:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Crie uma cópia do arquivo de configuração padrão no seguinte local:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navegue e abra o arquivo `ui_config.json` no nó `apps` para edição.

1. No arquivo `ui_config.json`, habilite o recurso de fluxo de trabalho de aprovação alterando a seção *recursos* como mostrado abaixo:

   ```json
   "features":  
   { 
      "approvalWorkflow":  true 
   }
   ```
