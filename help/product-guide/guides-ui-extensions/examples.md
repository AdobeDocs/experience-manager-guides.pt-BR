---
sidebar_position: 8
source-git-commit: eb3fe92d36bc58a11e47f786a10d5938e2ed0184
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---


# Exemplos

Neste pacote, também fornecemos alguns exemplos de personalização (disponíveis em `guides_extension/src`). Veja abaixo uma breve descrição de cada uma delas.

1. [Menu de contexto](./../../src/file_options.ts)
Neste exemplo, personalizamos o `file_options` menu de contexto, para remover o `Delete` e `Edit` e substitua o `Duplicate` opção com um `Download` opção.

2. [Painel esquerdo](../../src/left_panel_container.ts)
Neste exemplo, personalizamos o `left tab panel` para ter outro`tab` intitulado &quot;EXTENSÃO DE TESTE&quot;, e uma `tab panel` que tem um rótulo: `Test Tab Panel`

3. [Painel direito](../../src/right_panel_container.ts)
Neste exemplo, personalizamos o `right tab panel` para ter outro `tab` intitulado &quot;EXTENSÃO DE TESTE&quot;, e uma `tab panel` que tem um rótulo: `New Tab Panel`

4. [Painel Repositório](../../src/repository_panel.ts)

5. [Barra de ferramentas](../../src/toolbar.ts)
Neste exemplo, substituímos a variável `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` botões com um único `More Insert Options` botão contendo todos esses itens.

[Revisar exemplos do aplicativo]

1. [Caixa de ferramentas de anotação](../../src/review_app_examples/annotation_extension.ts)
Neste exemplo, adicionamos outro botão à caixa de ferramentas de anotação que abre o tópico de revisão atual no AEM.

2. [Comentário da revisão](../../src/review_app_examples/review_comment.ts)
Neste exemplo, adicionamos substituímos o nome de usuário pelas informações do usuário (que consistem no nome completo e no título do comentarista), adicionamos uma ID de comentário exclusiva, um ícone mailTo e adicionamos campos de entrada para mencionar a gravidade e o motivo do comentário.
Também adicionamos um `accept with modification` botão em comentários no lado do XMLEditor que abre uma caixa de diálogo.

3. [Comentário Responder](../../src/review_app_examples/comment_reply.ts)
Neste exemplo, adicionamos substituímos o nome de usuário por informações do usuário (que consistem no nome completo e no título do comentarista) e adicionamos um ícone mailTo no cabeçalho do comentário.

4. [Painel de revisão em linha](../../src/review_app_examples/inline_review_panel.ts)
Nesse arquivo, calculamos e atribuímos a ID de comentário exclusiva, mencionada no `Review Comment` e `Comment Reply` exemplos.
   - A variável `setCommentId` define a ID de comentário exclusiva para cada comentário, dependendo da contagem de comentários.

   - A variável `setUserInfo` define o valor de userInfo, usando o nome completo e o título de cada comentário.

   - A variável `onNewCommentEvent` assegura a `setUserInfo` é chamado para cada novo comentário ou resposta.

   - A variável `updatedProcessComments` para cada novo Evento de comentário e garante que `setCommentId` é chamado se recebermos um novo evento de comentário.

5. [Painel de análises de tópico](../../src/review_app_examples/topic_reviews.ts): Este arquivo estende [Painel de revisão em linha](../../src/review_app_examples/inline_review_panel.ts) para que as personalizações adicionadas também funcionem no lado do Aplicativo de revisão.

6. [Aceitar com caixa de diálogo de modificação](../../src/review_app_examples/accept_with_modification_dialog.ts)
Este é um exemplo de adição de novos widgets ao aplicativo. Aqui criamos uma nova caixa de diálogo, que tem dois campos de texto de entrada: `Revised Text` e `Adjudicator Comment Rationale`

![Caixa de diálogo Aceitar com modificação](./imgs/accept_with_modification_dialogue.png)

Este é o painel de revisão antes e depois da personalização:

![Painel de revisão;](./imgs/review_panel.png)
![Caixa de diálogo Aceitar com modificação](./imgs/customised_review_panel.png)
