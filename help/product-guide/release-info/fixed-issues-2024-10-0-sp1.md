---
title: Notas de versão | Correção de problemas na versão 2024.10.0 do Service Pack 1 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2024.10.0 do Service Pack 1 do Adobe Experience Manager Guides as a Cloud Service.
exl-id: d5fa200b-1f15-4ec2-adf9-a29382afc3de
TQID: https://experienceleague.adobe.com/ziRAAFKf5Dl-6Hd7ziXwSJepbiVzkXLGz5jDWIILPkU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 5%

---

# Correção de problemas na versão 2024.10.0 do Service Pack 1

Este artigo aborda os bugs corrigidos em várias áreas da versão 2024.10.0 do Service Pack 1 do Adobe Experience Manager Guides as a Cloud Service.

## Criação

- A criação do mapa DITA em uma instância UUID falha quando `xmleditor.uniquefilenames` é habilitado em `XMLEditorConfig`. (21201)
- Ao fechar um arquivo, comentários e rótulos adicionados à caixa de diálogo **Salvar Alterações e Desbloquear Arquivo** não são salvos no Histórico de Versões com a nova versão. Isto é específico para um caso de uso em que **Solicitar Check-in em Fechar** ou **Solicitar Nova Versão em Fechar** está habilitado em `XMLEditorConfig`. (20065)
- O estado do documento marcado como **Concluído** reverte para **Rascunho** antes de salvar uma nova versão, resultando no estado **Concluído** não persistente em nenhuma versão do documento. (20006)
- Não é possível adicionar um arquivo PDF como uma referência de imagem em um tópico no Editor da Web. (21206)
- Selecionar um arquivo DITA na interface do usuário do Assets mostra a opção **Abrir no FrameMaker**, mesmo quando desabilitada na configuração. (20082)

## Publicação

- Na saída do PDF nativo, os títulos de capítulo estão ausentes do índice, levando a uma hierarquia incorreta. (21840)


## Gerenciamento

- Fugas de recursos ocorrem devido a erros de **Unclosed ResourceResolver** nos logs. (18488)
- Ao criar uma linha de base nova ou duplicada, os rótulos são exibidos em uma ordem aleatória. (19307)


## Linha de base

- A edição e o salvamento de uma linha de base em uma configuração de nuvem expiram após 1 minuto, se a linha de base tiver um grande número de tópicos ou mapas. (19558)

## Tradução

- A tradução de mapas usando a Linha de base se torna lenta e eventualmente não carrega a lista de todos os tópicos associados e mapeia arquivos. (19733)
