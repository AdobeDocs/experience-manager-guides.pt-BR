---
title: Estado do documento
description: Saiba mais sobre os tipos de estados de documentos no Adobe Experience Manager Guides. Saber como alterar ou exibir o estado do documento e usar o estado do documento no DDLC.
exl-id: 3a68b2ed-b917-4f05-8b2b-d2722a740502
feature: Authoring, Features of Web Editor, Document State
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---

# Estado do documento {#id1821HC00URO}

Para gerenciar a prontidão dos documentos, o Adobe Experience Manager Guides fornece a propriedade de estado do documento para indicar o estado atual do documento. Os estados do documento ajudam você a descobrir rapidamente se um documento é novo, está em revisão ou se está no estado concluído.

## Tipos de estados de documentos

Um documento pode ter qualquer um dos estados definidos no perfil **Estado do Documento**. Por exemplo, um documento pode ter qualquer um dos seguintes Estados do documento:

- Rascunho - Indica que o documento foi criado e salvo com novas alterações.
- Em revisão - Indica que um fluxo de trabalho de revisão foi iniciado para o documento.
- Revisado - Indica que o documento foi revisado pelos usuários pretendidos.

Esses estados são definidos manual ou automaticamente de acordo com as configurações do perfil Estados do documento. Por exemplo, se o perfil de estado Documento estiver configurado com o estado inicial como Rascunho e o estado Em revisão estiver definido para documentos em revisão. Em seguida, ao criar um documento, o estado do documento é definido como *Rascunho*. Se você iniciar uma tarefa de revisão, o estado do documento será alterado para Em revisão.

Você também pode alterar manualmente o estado do documento para um ou vários documentos. No entanto, se você optar por alterar o estado do documento para vários documentos, o estado permitido será determinado pelos estados comuns permitidos para os documentos selecionados. Por exemplo, digamos que você tenha definido os estados do documento como Rascunho, Em revisão, Revisado e Pronto para publicar, na mesma ordem. No documento one.dita, o estado é definido como *Rascunho* e no documento two.dita, o estado é definido como Revisado. Ao selecionar one.dita e two.dita, o estado do documento permitido será *Pronto para publicação*. Como two.dita está no estado *Reviewed*, o próximo estado possível para two.dita é somente *Ready to Publish*, que é mostrado quando ambos os documentos são selecionados.

>[!NOTE]
>
> Um documento só pode existir em um estado por vez.

## Alterar o estado do documento no Editor

Para alterar o estado de um documento, execute as seguintes etapas:

1. Abra o documento no Editor e selecione Propriedades do arquivo no painel direito.
1. No painel Propriedades do arquivo, selecione o novo estado na lista suspensa **Estado do documento**. Você pode selecionar apenas os estados do documento permitidos na seção Transição de estado do perfil Estado do documento.

   >[!NOTE]
   >
   >Os administradores podem exibir todos os estados do documento e alterá-lo para qualquer estado possível.

1. Selecione **Salvar** no prompt de confirmação.

## Alterar o estado do documento na interface do usuário do Assets

1. Na interface do usuário do Assets, selecione um ou mais documentos cujo estado do documento você deseja alterar.
1. Na barra de ferramentas principal, selecione **Propriedades**.
1. Selecione o novo estado na lista suspensa **Estado do documento**. Você pode selecionar apenas os estados do documento permitidos na seção Transição de estado do perfil Estado do documento.

   >[!NOTE]
   >
   >Os administradores podem exibir todos os estados do documento e alterá-lo para qualquer estado possível.

1. Selecione **Salvar e fechar**.

### Exibir estado do documento

A exibição de cartão da interface do usuário do Assets mostra o estado atual juntamente com a data de criação e o tamanho do respectivo tópico DITA ou mapa DITA.

![](images/document_state.png){align="left"}

## Usar estados de documento no DDLC

Os estados do documento desempenham um papel importante no gerenciamento do ciclo de vida dos documentos no DDLC. Se sua organização seguir estritamente o DDLC, ter um mecanismo para controlar a edição de documentos com base em seu estado se torna um recurso essencial. Por exemplo, você pode permitir a edição de documentos quando eles estiverem nos estados *Rascunho* ou *Em revisão*. No entanto, quando um documento é revisado e está pronto para ser publicado, deve haver uma maneira de impedir novas modificações nos documentos.

O Experience Manager Guides fornece fluxo de trabalho para aprovação de documentos, que ajuda a controlar o ciclo de vida do processo de desenvolvimento de documentos. Quando um documento estiver pronto para publicação ou tiver atingido o penúltimo estado, você poderá marcá-lo como aprovado. Depois que um documento é aprovado, o Experience Manager Guides cria uma nova versão do documento e o torna somente leitura. Você pode então mover o documento para publicação ou criar uma linha de base para processamento adicional.

Para iniciar uma nova versão dos documentos marcados como aprovados, um autor precisa iniciar uma nova versão. Iniciar uma nova versão altera o estado do documento para *Rascunho* novamente. Ao alterar o estado do documento para *Rascunho*, o documento se torna editável novamente e você pode continuar trabalhando na próxima versão.

Para usar o recurso de aprovação de documento, execute as seguintes etapas:

>[!NOTE]
>
> O recurso de fluxo de trabalho de aprovação deve ser habilitado pelo administrador. Para obter mais detalhes, exiba a seção *Habilitar fluxo de trabalho de aprovação* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

1. No Editor, abra o documento que deseja marcar para aprovação.

1. Selecione o ícone **Marcar como Aprovado**![](images/mark_approve_icon.svg).

1. Se o documento estiver no estado a ser marcado como aprovado, a seguinte caixa de diálogo será exibida:

   ![](images/mark-approved-correct-state.png){width="300" align="left"}

   Se o documento não puder ser marcado como aprovado, a seguinte mensagem será exibida:

   ![](images/mark-approved-incorrect-state.png){width="300" align="left"}

1. Se o documento estiver pronto para ser marcado como aprovado, selecione um rótulo na lista suspensa e selecione **Aprovar**.

   >[!NOTE]
   >
   > Se o administrador não tiver configurado uma lista predefinida de rótulos, você verá um campo de texto de forma livre para inserir um rótulo.

1. Depois que o documento for marcado com êxito como aprovado, uma **Visualização** do documento será mostrada no modo somente leitura. Todas as opções de edição são removidas de todos os três modos - Autor, Source e Visualização. Entretanto, você ainda terá acesso à lista suspensa **Menu** que apresenta as opções **Histórico de versões** e **Marcas**.

   ![](images/approved-doc-read-only.png){width="650" align="left"}

   >[!NOTE]
   >
   > No modo de Visualização, a lista suspensa Menu com o histórico de Versões e as opções de Tags é removida da barra de ferramentas.


Depois que um documento é marcado como aprovado, ele não fica mais disponível para edição. Se quiser usar o documento para a próxima versão, você precisará trazê-lo de volta para o estado *Rascunho*. Para alterar novamente o estado de um documento aprovado para o modo *Rascunho*, execute as seguintes etapas:

1. Em um documento aprovado, selecione o ícone ![](images/approved-restart-draft-mode-icon.svg) **Iniciar uma Nova Versão**.

   A mensagem Iniciar nova versão é exibida.

1. Selecione **Confirmar**.

   O estado do documento é alterado para Rascunho e o documento é aberto no Editor no modo de edição.


**Tópico pai:**[ Introdução ao Editor](web-editor.md)
