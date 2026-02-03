---
title: Noções básicas das notificações de revisão
description: Saiba mais sobre os diferentes tipos de notificações de revisão e como elas são acionadas durante as diferentes fases do fluxo de trabalho de revisão no Experience Manager Guides.
feature: Reviewing
role: User
exl-id: dc452e7d-a317-4168-8015-9fa4a06666ea
source-git-commit: 16688221c35e0b24c51cbff27953a93892cd0944
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 0%

---

# Noções básicas das notificações de revisão

>[!IMPORTANT]
>
> Os novos recursos descritos neste artigo são ativados por padrão com a versão 2508 do Experience Manager Guides as a Cloud Services. As revisões criadas antes da migração não são afetadas e continuarão a usar o fluxo de trabalho anterior. Se preferir continuar usando os recursos existentes sem essas atualizações, entre em contato com a equipe de Sucesso do cliente para desabilitar os novos recursos.

O Experience Manager Guides simplifica a colaboração entre Autores e Revisores por meio de um fluxo de trabalho de revisão estruturado. Como parte desse fluxo de trabalho, as notificações desempenham uma função essencial para manter todos os participantes de uma tarefa de revisão informados e responsivos às alterações.

Sempre que uma ação relacionada à revisão for executada, como atribuição de tarefa, conclusão ou atualizações de feedback, uma notificação será enviada automaticamente aos usuários envolvidos da tarefa de revisão para chamar sua atenção imediata. Essas notificações são enviadas em dois formatos:

- **Notificações do AEM**: exibidas na interface do AEM.
- **Notificações por email**: enviadas diretamente para a caixa de entrada do usuário.

A tabela abaixo fornece uma visão geral dos diferentes tipos de notificações de revisão, quais ações as acionam e como elas são exibidas em diferentes formatos:


## Revisar formatos de notificação com valores de amostra

| **Ação de revisão** | **Título da notificação (AEM)** | **Texto de notificação (AEM)** | **Assunto do email** | **Texto de notificação por email** | **Destinatário** |
|-----------------------------|--------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| Tarefa de revisão criada | Tarefa de revisão atribuída: **Revisão da Página Inicial** | Atribuído por **Autor** | Tarefa de revisão atribuída: **Revisão da Página Inicial** | O **Autor** criou uma tarefa de revisão **Revisão da Página Inicial** no projeto **Revamp do WebDocs** com data de vencimento **15 de agosto de 2025**. Você foi atribuído como revisor. | **Revisor** |
| Feedback enviado | Comentário de avaliação recebido para **Análise da Página Inicial** | Comentários de **Revisor** | Comentário de avaliação recebido para **Análise da Página Inicial** | O **Revisor** enviou feedback para a tarefa **Revisão da Página Inicial** no projeto **Revamp do WebDocs**. Revise e faça as atualizações necessárias bem antes da data de vencimento **15 de agosto de 2025**. | **Autor** ou **Iniciador da tarefa** |
| Reavaliação solicitada | Nova revisão solicitada para **Revisão da Página Inicial** | Solicitado por **Autor** | Revisão solicitada para **Revisão da Página Inicial** por **Autor** | **O Autor** atualizou o documento para a tarefa **Revisão da Página Inicial** com base nos seus comentários e está solicitando uma revisão. Revise com bastante antecedência a data de vencimento **15 de agosto de 2025**. | **Revisor** |
| Revisão encerrada | Tarefa de revisão encerrada: **Revisão da Página Inicial** | Fechado por **Autor** | Tarefa de revisão encerrada: **Revisão da Página Inicial** | A tarefa de revisão **Revisão da Página Inicial** no projeto **Renovação de WebDocs** foi fechada por **Autor**. | **Autor** ou **Iniciador da tarefa** , **Revisor** |
| Revisor não atribuído | Tarefa de revisão não atribuída **Revisão da página inicial** | Não atribuído por **Autor** | Tarefa de revisão não atribuída **Revisão da página inicial** | Você foi desatribuído da tarefa de revisão **Revisão da Página Inicial** no projeto **Renovação de WebDocs** pelo **Autor**. | **Revisor** |
| Menção de tag | Mencionado no comentário da tarefa de revisão para **Revisão da página inicial** | Mencionado por **Autor** | Mencionado no comentário da tarefa de revisão para **Revisão da página inicial** | Você foi mencionado em um comentário na tarefa **Revisão da Página Inicial** em **Renovação de WebDocs** por **Autor**. **Trecho do comentário:** *&quot;Atualize a estrutura do cabeçalho para seguir as diretrizes de acessibilidade.&quot;* | **Usuário mencionado** |
| Conteúdo atualizado durante a revisão | Tópico atualizado na tarefa de revisão **Revisão da Página Inicial** | Atualizado por **Autor** | Tópico atualizado na tarefa de revisão **Revisão da Página Inicial** | **O Autor** atualizou as versões de tópico para a tarefa de revisão **Revisão da Página Inicial**. Revise com bastante antecedência a data de vencimento **15 de agosto de 2025**. | **Revisor** |
| Tópicos adicionados ou removidos ou versão atualizada enquanto uma tarefa de revisão está em andamento com o(s) revisor(es) | Tópicos atualizados na tarefa de revisão **Revisão da Página Inicial** | Atualizado por **Autor** | Tópicos atualizados na tarefa de revisão **Revisão da Página Inicial** | **O Autor** atualizou as versões de tópico para a tarefa de revisão **Revisão da Página Inicial**. Revise com bastante antecedência a data de vencimento **15 de agosto de 2025**. | **Revisor** |


Na tabela acima, o **texto em negrito** representa valores de exemplo e está sendo orientado por variáveis predefinidas que podem ser usadas em notificações.


Por exemplo:

- **Revisão da Página Inicial** é um nome de tarefa de exemplo.
- **Priya** (Autor) e **John** (Revisor) são exemplos de nomes de usuário.
- **WebDocs Revamp** é um nome de projeto de exemplo.
- **15 de agosto de 2025** é uma data de término de exemplo.

Além disso, se uma tarefa contiver comentários, um trecho de comentário ( uma parte do comentário completo) será incluído na notificação por email. O trecho é exibido nos seguintes casos:

- Quando você estiver marcado em um comentário, um trecho do comentário marcado será exibido na notificação por email.
- Quando um comentário no nível da tarefa é adicionado a uma tarefa de revisão da qual você faz parte, um trecho desse comentário é exibido na notificação por email.

Para obter uma lista completa de variáveis predefinidas e revisar a personalização da notificação, exiba [Configurar e personalizar fluxos de trabalho](../cs-install-guide/customize-workflows.md#customize-email-and-aem-notification-templates).




**Tópico pai:**[ Introdução à revisão](review.md)
