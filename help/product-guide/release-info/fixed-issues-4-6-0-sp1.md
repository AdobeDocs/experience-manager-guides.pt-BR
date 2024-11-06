---
title: Notas de versão | Correção de problemas na versão do Adobe Experience Manager Guides 4.6.0 Service Pack 1
description: Saiba mais sobre as correções de erros na versão 4.6.0 Service Pack 1 do Adobe Experience Manager Guides
role: Leader
source-git-commit: 2362870e0e3e6c08df03e8c547bb77de7faa0a02
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---


# Correção de problemas na versão 4.6.0 do Service Pack 1 (outubro de 2024)


Este artigo aborda os bugs corrigidos em várias áreas da versão 4.6.0 Service Pack 1 do Adobe Experience Manager Guides.

Saiba mais sobre as [instruções de atualização para o 4.6.0 Service Pack 1 versão](upgrade-instructions-4-6-0-sp1.md).

## Criação  

- A criação do mapa DITA em uma instância UUID falha quando `xmleditor.uniquefilenames` é habilitado em `XMLEditorConfig`. (21201)
- Ao fechar um arquivo, comentários e rótulos adicionados à caixa de diálogo **Salvar Alterações e Desbloquear Arquivo** não são salvos no Histórico de Versões com a nova versão. Isto é específico para um caso de uso em que **Solicitar Check-in em Fechar** ou **Solicitar Nova Versão em Fechar** está habilitado em `XMLEditorConfig`. (2006)
- O Estado do Documento marcado como **Concluído** reverte para **Rascunho** antes de salvar uma nova versão, resultando no estado **Concluído** que não persiste em nenhuma versão do documento. (2006)
- Não é possível adicionar um arquivo PDF como uma referência de imagem em um tópico no Editor da Web. (21206)
- Selecionar um arquivo DITA na interface do usuário do Assets mostra a opção **Abrir no FrameMaker**, mesmo quando desabilitada na configuração. (20082)


## Publicação

- O upload de anexos no Salesforce falhará se o caminho do anexo exceder o comprimento permitido. (19420)
- Ao publicar um tópico no Salesforce, os links do arquivo PDF não são resolvidos. (19304)
- O erro `DUPLICATE_VALUE` ocorre intermitentemente ao tentar republicar um artigo existente no Salesforce. (17932)
- Na saída do PDF nativo, os títulos de capítulo estão ausentes do índice, levando a uma hierarquia incorreta. (21840)
- Ao publicar o AEM Sites, somente um número limitado de atributos estará disponível para inclusão no índice. (7483)

## Gerenciamento

- Vazamentos de recursos ocorrem devido a erros Unclosed **ResourceResolver** em logs. (18488)
- Ao criar uma linha de base nova ou duplicada, os rótulos são exibidos em uma ordem aleatória. (19307)









