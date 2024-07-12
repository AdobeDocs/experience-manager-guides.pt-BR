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
Neste exemplo, personalizamos o menu de contexto `file_options`, para remover as opções `Delete` e `Edit`, e substituir a opção `Duplicate` por uma opção `Download`.

2. [Painel esquerdo](../../src/left_panel_container.ts)
Neste exemplo, personalizamos o `left tab panel` para ter outro`tab` chamado &quot;EXTENSÃO DE TESTE&quot;, e um `tab panel` correspondente que tenha um rótulo: `Test Tab Panel`

3. [Painel Direito](../../src/right_panel_container.ts)
Neste exemplo, personalizamos o `right tab panel` para ter outro `tab` chamado &quot;EXTENSÃO DE TESTE&quot;, e um `tab panel` correspondente que tenha um rótulo: `New Tab Panel`

4. [Painel Repositório](../../src/repository_panel.ts)

5. [Barra de ferramentas](../../src/toolbar.ts)
Neste exemplo, substituímos os botões `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` por um único botão `More Insert Options` que contém todos esses.

[Analisar Exemplos de Aplicativos]

1. [Caixa de ferramentas de anotação](../../src/review_app_examples/annotation_extension.ts)
Neste exemplo, adicionamos outro botão à caixa de ferramentas de anotação que abre o tópico de revisão atual no AEM.

2. [Comentário da avaliação](../../src/review_app_examples/review_comment.ts)
Neste exemplo, adicionamos substituímos o nome de usuário pelas informações do usuário (que consistem no nome completo e no título do comentarista), adicionamos uma ID de comentário exclusiva, um ícone mailTo e adicionamos campos de entrada para mencionar a gravidade e o motivo do comentário.
Também adicionamos um botão `accept with modification` em comentários no lado do XMLEditor que abre uma caixa de diálogo.

3. [Resposta ao comentário](../../src/review_app_examples/comment_reply.ts)
Neste exemplo, adicionamos substituímos o nome de usuário por informações do usuário (que consistem no nome completo e no título do comentarista) e adicionamos um ícone mailTo no cabeçalho do comentário.

4. [Painel de revisão em linha](../../src/review_app_examples/inline_review_panel.ts)
Neste arquivo, calculamos e atribuímos a ID de comentário exclusiva, mencionada nos exemplos `Review Comment` e `Comment Reply`.
   - O método `setCommentId` define a ID de comentário exclusiva para cada comentário, dependendo da contagem de comentários.

   - O `setUserInfo` define o valor de userInfo, usando o nome completo e o título de cada comentário.

   - O `onNewCommentEvent` garante que o método `setUserInfo` seja chamado para cada novo comentário ou resposta.

   - A função `updatedProcessComments` é executada para cada novo Evento de comentário e garante que `setCommentId` seja chamado se recebermos um novo evento de comentário.

5. [Painel de Revisões de Tópico](../../src/review_app_examples/topic_reviews.ts): este arquivo estende o [Painel de Revisão Embutido](../../src/review_app_examples/inline_review_panel.ts) para que as personalizações adicionadas também funcionem no lado do Aplicativo de Revisão.

6. [Aceitar com Caixa de Diálogo de Modificação](../../src/review_app_examples/accept_with_modification_dialog.ts)
Este é um exemplo de adição de novos widgets ao aplicativo. Aqui criamos uma nova caixa de diálogo, que tem dois campos de texto de entrada: `Revised Text` e `Adjudicator Comment Rationale`

![Aceitar Com Caixa De Diálogo De Modificação](./imgs/accept_with_modification_dialogue.png)

Este é o painel de revisão antes e depois da personalização:

![Painel de Revisão;](./imgs/review_panel.png)
![Aceitar Com Caixa De Diálogo De Modificação](./imgs/customised_review_panel.png)
