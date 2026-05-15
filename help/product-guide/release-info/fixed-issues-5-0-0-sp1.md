---
title: Notas de versão | Correção de problemas na versão Adobe Experience Manager Guides 5.0.0 Service Pack 1
description: Saiba mais sobre as correções de erros na versão 5.0.0 do Service Pack 1 do Adobe Experience Manager Guides
role: Leader
exl-id: 1d0bc3d0-aedf-4f67-b6f7-2208facdee96
TQID: https://experienceleague.adobe.com/0qxye7ZUWt1iixHthjjTNJgtlOQX-C30jGi5zQlRJfA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 1%

---

# Correção de problemas na versão 5.0.0 do Service Pack 1 (junho de 2025)


Este artigo aborda os bugs corrigidos em várias áreas da versão 5.0.0 Service Pack 1 do Adobe Experience Manager Guides.

Saiba mais sobre as [instruções de atualização para o 5.0.0 Service Pack 1 versão](upgrade-instructions-5-0-0-sp1.md).

## Criação

- Quando o conteúdo é colado em um `codeblock` ou quando espaços são adicionados em `codeblock` e a exibição é trocada, o espaçamento é perdido. (GUIDES-29347)
- Quando um comentário XML é adicionado em um elemento na exibição **Source**, os espaços à esquerda e à direita em torno do comentário são perdidos ao alternar exibições. (GUIAS- 28188)

## Gerenciamento de ativos

- Ao abrir um tópico no modo de exibição **Autor** após a atualização de um navegador, as marcas aplicadas anteriormente no painel **Propriedades do Arquivo** não serão mantidas, e a adição de novas marcas substitui as existentes, principalmente quando um grande número de marcas está disponível para seleção. (GUIDES-29078)
- Ao gerar um relatório de Metadados para um mapa DITA contendo um grande número de ativos, o botão **Gerenciar** fica sem resposta ou exibe resposta atrasada. (GUIDES-29778)

## Tradução

- Ao enviar ativos para tradução do Experience Manager Guides, os ativos não são adicionados ao trabalho de Tradução, o que impede que o botão **Iniciar** apareça e impede que você inicie o trabalho de tradução. (GUIDES-28237)

## Publicação

- Ao modificar as configurações de uma predefinição de saída no perfil de pasta e selecionar **Aplicar alterações de predefinição**, as alterações não serão propagadas para as predefinições de saída presentes no mapa DITA. (GUIDES-26694)

## Revisar

- As tentativas de criar tarefas de revisão por meio do fluxo de trabalho do AEM falham consistentemente, pois o nó de revisão não é criado. (GUIDES-28214)
