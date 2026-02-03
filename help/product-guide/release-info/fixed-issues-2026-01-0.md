---
title: Notas de versão | Correção de problemas na versão 2026.01.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2026.01.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 8a9a82e79c757e403141e853aafbc64e1618c30a
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 0%

---

# Correção de problemas na versão 2026.01.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2026.01.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2026.01.0](whats-new-2026-01-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.01.0](upgrade-instructions-2026-01-0.md).

## Criação

- Ao atualizar uma equação de MathML em linha usando a opção Editar MathML do menu de contexto, o valor atualizado não é refletido até que a página seja atualizada. (GUIDES-38198)
- Quando um tópico contém muitos elementos reutilizáveis (aqueles com IDs) adicionados no painel Reutilizável, alguns elementos podem não estar acessíveis devido à altura fixa do contêiner. (GUIDES-37220)
- Ao inserir uma referência cruzada a um arquivo, os ícones de mapas e tópicos são idênticos.(GUIDES-36662)
- Ao editar um mapa, símbolos especiais em `navtitle` não são exibidos para `topichead` no modo de exibição Autor. (GUIDES-35435)
- Não é possível adicionar vários rótulos de Versão a um tópico da caixa de diálogo **Salvar como nova versão**. (GUIDES-32716)

## Gerenciamento de ativos

- Não é possível remover rótulos de versão do painel Histórico de versão na interface do usuário do Assets. (GUIDES-38276)
- Ao carregar ativos com nome de arquivo contendo caracteres inválidos, o ativo não é carregado e exibe uma mensagem incorreta **O arquivo está bloqueado por outro usuário** apesar de o ativo estar desbloqueado. (GUIDES-32680)
- Na pesquisa do Assets, os nós de subativos e metadados (como imagens e PDFs) são incluídos incorretamente nos resultados. Além disso, para uma predefinição de saída quando os filtros DITAVAL são aplicados, a pesquisa retorna arquivos DITAVAL gerados internamente a partir de predefinições de condição. (GUIDES-35418)

## Publicação

- Ao gerar a saída do AEM Sites, os títulos de mapa que contêm palavras-chave e títulos de tópico com o elemento `<ph>` não são incluídos na saída publicada. (GUIDES-36641)
- Ao publicar usando uma predefinição personalizada com conteúdo que contenha links para PDFs sem o escopo definido como externo, o processo não é concluído. (GUIDES-21708)
- Ao executar a ativação em massa, a criação de pacote adiciona filtros para todos os caminhos listados na propriedade `fileReference` de uma página, incluindo caminhos externos e de mesmo nível. (GUIDES-24887)
- Na saída do PDF Nativo, o elemento `abbreviated-form` exibe o `glossterm` em vez do `glossSurfaceForm` ou `glossAcronym` designado. (GUIDES-26393)
- Para a saída Native PDF, o elemento `<alt>` para imagens é ignorado, impedindo que o texto alternativo seja aplicado para acessibilidade. (GUIDES-29087)
- Ao baixar arquivos temporários para um mapa com uma linha de base durante a publicação de uma predefinição, o arquivo `metadata.xml` faz referência incorretamente a `versionPath` em vez de `dampath`.(GUIDES-29815)
- Ao criar ou editar um tópico que inclua uma citação, se o campo Autor não for adicionado à caixa de diálogo de citação, a PDF não será gerada. (GUIDES-37934)
- O arquivo CSS (`rhdefault.css`) é aplicado incorretamente ao modelo PDF apesar de nenhum CSS ser referenciado, causando a ausência de logs de erro do arquivo CSS.(GUIDES-31752)

## Platform

- Ao tentar salvar um tópico ou mapa, a operação pode falhar intermitentemente com um erro **Falha ao salvar arquivo**, especialmente durante tarefas de processamento intensivo de ativos ou fluxos de trabalho de tradução em execução em segundo plano. (GUIDES-37837)
- Usar `scope="external"` para uma referência ao conteúdo DAM em um tópico ou mapa faz com que o caminho relativo do ativo seja substituído por um GUID. (GUIDES-38783)

## Relatórios

- O relatório Lista interrompida está incluindo incorretamente links externos, `keyrefs` válidos e palavras-chave que são resolvidas corretamente dentro do escopo do mapa atual. (GUIDES-27774)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2026.01.0:

- Quando um tópico em revisão é removido de uma tarefa de revisão em andamento, seu estado do documento continua a ser **Na revisão**, mesmo que o tópico não faça mais parte de nenhuma tarefa de revisão. (GUIDES-38709)<br>**Solução alternativa**: altere o estado do documento do tópico de **Em Revisão** para o estado apropriado na página Propriedades ou no painel Propriedades do arquivo.
- Ao executar uma pesquisa usando **Localizar e substituir**, se você abrir um arquivo a partir dos resultados da pesquisa, fechá-lo e tentar reabri-lo selecionando o resultado listado, o arquivo não será reaberto. (GUIDES-39050)<br>**Solução alternativa**: abra primeiro qualquer outro arquivo dos resultados da pesquisa e reabra o arquivo fechado anteriormente da lista para resolver o problema.
- Ao usar Guias com servidor DB, para conteúdo que inclui autorreferências, o relatório Lista de tópicos exibe entradas inválidas para cada autorreferência, resultando em uma contagem de arquivos imprecisa. (GUIDES-39420)












