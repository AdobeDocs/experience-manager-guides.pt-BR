---
title: Notas de versão | Correção de problemas na versão Adobe Experience Manager Guides 5.0.0 Service Pack 1
description: Saiba mais sobre as correções de erros na versão 5.0.0 do Service Pack 1 do Adobe Experience Manager Guides
role: Leader
source-git-commit: 083a8e16b9d3cd6c3894d7eaa2fee489b1dc0bb8
workflow-type: tm+mt
source-wordcount: '293'
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
