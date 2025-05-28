---
title: Notas de versão | Correção de problemas na versão 2025.06.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2025.06.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 78d8896982ff73e954de6d6daa9832faf30ed3b3
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---

# Correção de problemas na versão 2025.06.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2025.06.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2025.06.0](whats-new-2025-06-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.06.0](upgrade-instructions-2025-06-0.md).

## Criação  

- Ao abrir um mapa DITA com o Unified Shell ativado, o editor é atualizado intermitentemente. (GUIDES-26919)
- Falha ao fechar conexões da sessão JCR ao atualizar ou criar tópicos resulta em vazamentos de memória e tempo de inatividade do serviço. (GUIDES-26282)
- Arrastar as colunas altera a largura de porcentagem para valores de pixel, o que resulta em tabelas distorcidas ou desalinhadas.(GUIDES-23128)
- Quando o conteúdo é colado em um `code block` ou quando espaços são adicionados em `code block` e a exibição é trocada, o espaçamento é perdido. (GUIDES-27478)
- Ao adicionar um mapa ao `bookmap`, ele é armazenado em `fmditatopicrefs` em vez de `fmditamaprefs`. (GUIDES-25480)
- A caixa de diálogo **Inserir imagem** não é renderizada corretamente em telas de alta resolução ou com menos zoom, fazendo com que o título da figura e os campos de texto alternativos desapareçam. (GUIDES-26459)


## Publicação

- A publicação do PDF nativo continua indefinidamente se o conteúdo DITA tiver um link da Web sem ter o escopo `external`. (GUIDES-26434)
- A publicação de PDFs nativos e sites do AEM é interrompida e colocada em fila quando há erros no conteúdo. (GUIDES-26516)
- Ao criar uma nova linha de base com um grande número de rótulos, isso impede que todos os rótulos sejam buscados. (GUIDES-16232)
- Ao gerar páginas do site do AEM com títulos que incluem várias palavras separadas por espaços, o título do mapa exibe hifens em vez de espaços. (GUIDES-27903)
- Para o PDF Nativo, um nome de propriedade de metadados inválido não está sendo resolvido e é exibido como `unresolved property name` em **propriedades do documento**. (GUIDES-25680)
- O texto multilinha em `codeblock` causa problemas de estouro de texto durante a geração do PDF. (GUIDES-15541)
- Ao adicionar mapas à coleção de mapas, os ativos diferentes dos mapas (curtidas, tópicos etc.) são exibidos e os idiomas do mapa traduzido também não são classificados corretamente.(GUIDES-25085)


## Revisar

- A exibição de documento na interface de Revisão não envolve o conteúdo para alguns tamanhos de tela, exigindo que os usuários rolem horizontalmente para visualizar o conteúdo completo. (GUIDES-25292)


## Problemas conhecidos

A Adobe identificou o seguinte problema conhecido para a versão 2025.06.0:

- Ao usar a opção Localizar e substituir, depois de aplicar a operação Substituir ocorrência única em um arquivo, nenhuma outra ação pode ser executada no painel Localizar e substituir. (GUIDES-28930)

- Em um perfil de pasta, quando um ativo já indexado é excluído da interface do usuário, o caminho indexado correspondente não é removido e uma tentativa de reindexação falha com uma mensagem de erro. (GUIDES-29147) <br>**Solução alternativa:** Remova o caminho obsoleto que não existe mais antes de iniciar a reindexação.

- Se um mapa contiver dependências cíclicas e você abrir a Visualização de mapa, as visualizações Source, Autor e Layout ficarão inacessíveis até que a página seja atualizada. (GUIDES-28334) <br>**Solução alternativa:** atualize a página para restaurar o acesso a essas exibições.
