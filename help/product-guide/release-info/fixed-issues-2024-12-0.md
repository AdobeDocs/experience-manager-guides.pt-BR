---
title: Notas de versão | Correção de problemas na versão 2024.12.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2024.12.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f643a4a22151af2ff14288ab3885c1a6657a80ca
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# Correção de problemas na versão 2024.12.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2024.12.0 do Adobe Experience Manager Guides as a Cloud Service.

Saiba mais sobre [as instruções de atualização para a versão 2024.12.0](./upgrade-instructions-2024-12-0.md).

## Criação  

- A criação do mapa DITA em uma instância UUID falha quando `xmleditor.uniquefilenames` é habilitado em `XMLEditorConfig`. (21201)
- Ao fechar um arquivo, comentários e rótulos adicionados à caixa de diálogo **Salvar Alterações e Desbloquear Arquivo** não são salvos no Histórico de Versões com a nova versão. Isto é específico para um caso de uso em que **Solicitar Check-in em Fechar** ou **Solicitar Nova Versão em Fechar** está habilitado em `XMLEditorConfig`. (2006)
- O estado do documento marcado como **Concluído** reverte para **Rascunho** antes de salvar uma nova versão, resultando no estado **Concluído** não persistente em nenhuma versão do documento. (2006)
- Não é possível adicionar um arquivo PDF como uma referência de imagem em um tópico no Editor da Web. (21206)
- Selecionar um arquivo DITA na interface do usuário do Assets mostra a opção **Abrir no FrameMaker**, mesmo quando desabilitada na configuração. (20082)

## Publicação

- Na saída do PDF nativo, os títulos de capítulo estão ausentes do índice, levando a uma hierarquia incorreta. (21840)


## Gerenciamento

- Fugas de recursos ocorrem devido a erros de **Unclosed ResourceResolver** nos logs. (18488)
- Ao criar uma linha de base nova ou duplicada, os rótulos são exibidos em uma ordem aleatória. (19307)


## Linha de base

- A edição e o salvamento de uma linha de base em uma configuração de nuvem expiram após 1 minuto, se a linha de base tiver um grande número de tópicos ou mapas. (1955)

## Tradução

- A tradução de mapas usando a linha de base torna-se lenta e eventualmente não carrega a lista de todos os tópicos associados e mapeia arquivos. (1973)
