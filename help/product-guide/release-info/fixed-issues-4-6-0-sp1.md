---
title: Notas de versão | Correção de problemas no Adobe Experience Manager Guides 4.6.0 Service Pack 1 versão
description: Saiba mais sobre as correções de erros na versão 4.6.0 Service Pack 1 do Adobe Experience Manager Guides
role: Leader
exl-id: ab45ac10-8a97-4ade-accc-2b884da0e973
TQID: https://experienceleague.adobe.com/-PGxudGeachzaYoru1fHTObZcwRuXzle5s7KRRJlfBA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 311
ht-degree: 4%

---

# Correção de problemas na versão 4.6.0 do Service Pack 1 (outubro de 2024)


Este artigo aborda os bugs corrigidos em várias áreas da versão 4.6.0 Service Pack 1 do Adobe Experience Manager Guides.

Saiba mais sobre as [instruções de atualização para o 4.6.0 Service Pack 1 versão](upgrade-instructions-4-6-0-sp1.md).

## Criação

- A criação do mapa DITA em uma instância UUID falha quando `xmleditor.uniquefilenames` é habilitado em `XMLEditorConfig`. (21201)
- Ao fechar um arquivo, comentários e rótulos adicionados à caixa de diálogo **Salvar Alterações e Desbloquear Arquivo** não são salvos no Histórico de Versões com a nova versão. Isto é específico para um caso de uso em que **Solicitar Check-in em Fechar** ou **Solicitar Nova Versão em Fechar** está habilitado em `XMLEditorConfig`. (20065)
- O Estado do Documento marcado como **Concluído** reverte para **Rascunho** antes de salvar uma nova versão, resultando no estado **Concluído** que não persiste em nenhuma versão do documento. (20006)
- Não é possível adicionar um arquivo PDF como uma referência de imagem em um tópico no Editor. (21206)
- Selecionar um arquivo DITA na interface do usuário do Assets mostra a opção **Abrir no FrameMaker**, mesmo quando desabilitada na configuração. (20082)


## Publicação

- O upload de anexos no Salesforce falhará se o caminho do anexo exceder o comprimento permitido. (19420)
- Ao publicar um tópico no Salesforce, os links do arquivo do PDF não são resolvidos. (19304)
- O erro `DUPLICATE_VALUE` ocorre intermitentemente ao tentar republicar um artigo existente no Salesforce. (17932)
- Na saída do PDF nativo, os títulos de capítulo estão ausentes do índice, levando a uma hierarquia incorreta. (21840)
- Ao publicar o AEM Sites, somente um número limitado de atributos estará disponível para inclusão no índice. (7483)

## Gerenciamento

- Vazamentos de recursos ocorrem devido a erros Unclosed **ResourceResolver** em logs. (18488)
- Ao criar uma linha de base nova ou duplicada, os rótulos são exibidos em uma ordem aleatória. (19307)
