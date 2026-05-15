---
title: Notas de versão | Correção de problemas na versão Adobe Experience Manager Guides 5.1.0 Service Pack 3
description: Saiba mais sobre as correções de erros na versão 5.1.0 Service Pack 3 do Adobe Experience Manager Guides
role: Leader
exl-id: faa9a5d7-616f-4692-98d1-23abc78556b6
TQID: https://experienceleague.adobe.com/qiVY-B-D3FcHq2PH7Go2AAFpnstCrPJ2MVLEalQCVn0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 297
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
