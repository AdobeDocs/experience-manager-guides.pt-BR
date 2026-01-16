---
title: Notas de versão | Correção de problemas na versão Adobe Experience Manager Guides 5.1.0 Service Pack 3
description: Saiba mais sobre as correções de erros na versão 5.1.0 Service Pack 3 do Adobe Experience Manager Guides
role: Leader
source-git-commit: 82eb0e18eb285006c66b1fe2b6ecc3ca86fefe61
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 1%

---

# Correção de problemas na versão 5.1.0 do Service Pack 3 (dezembro de 2025)


Este artigo aborda os bugs corrigidos em várias áreas da versão 5.1.0 Service Pack 3 do Adobe Experience Manager Guides.

Saiba mais sobre [as instruções de atualização para o 5.1.0 Service Pack 3 versão](upgrade-instructions-5-1-0-sp3.md).


## Criação

- O CSS personalizado aplicado a um perfil de nível de pasta para tópicos ou mapas é revertido para o estilo padrão no modo de Visualização após a atualização do navegador. (GUIDES-31098)
- Não é possível adicionar vários **rótulos de versão** a um tópico da caixa de diálogo **Salvar como nova versão**. (GUIDES-32716)


## Gerenciamento de ativos

- Não é possível remover rótulos de versão do painel **Histórico de versões** na interface do usuário do Assets. (GUIDES-38276)


## Revisar

- Quando um Revisor conclui uma tarefa de revisão ou o iniciador atualiza a tarefa de revisão sem inserir comentários, o e-mail de notificação enviado exibe o comentário anterior mais recente. (GUIDES-33590)

## Publicação

- Ao gerar saída do AEM Sites usando o mapeamento de componente herdado, os tópicos que usam o atributo `copy-to` são publicados com o nome do tópico `copy-from` em vez do nome definido no atributo `copy-to`. (GUIDES-22155)
- Quando a saída do PDF Nativo é gerada usando uma linha de base dinâmica, o termo **PDFProject** é exibido como o título do PDF em vez do título do mapa real. (GUIDES-31102)

## Platform

- Usar `scope="external"` para uma referência ao conteúdo DAM em um tópico ou mapa faz com que o caminho relativo do ativo seja substituído por um GUID. (GUIDES-35605)

## Problema conhecido

A Adobe identificou o seguinte problema conhecido para a versão 5.1.0 Service Pack 3:

- Quando você marca uma tarefa de revisão como concluída na página de detalhes da tarefa, a tarefa é concluída e fechada; no entanto, seu status continua a ser exibido como **Em andamento** no painel Revisão. (GUIDES-39375)




