---
title: Notas de versão | Correção de problemas na versão 2026.04.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2026.04.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: ce2c9da0d9beb05a15f7cefcf9483e0c93abbf37
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---

# Correção de problemas na versão 2026.04.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2026.04.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2026.04.0](whats-new-2026-04-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.04.0](upgrade-instructions-2026-04-0.md).

## Criação

- Ao editar um arquivo do Esquematron (`*.sch`) e usar o recurso Localizar e substituir, o painel Localizar e substituir aparece parcialmente fora da tela na parte inferior, impedindo o acesso aos campos e controles de entrada. (GUIDES-38412)

## Publicação

- Quando o mesmo tópico é reutilizado em vários mapas com diferentes predefinições condicionais, a publicação do mapa mais recente no Salesforce substitui o conteúdo do tópico, resultando na exibição de dados incorretos para os usuários de mapas publicados anteriormente. (GUIDES-37806)
- Ao publicar um PDF nativo para um mapa que inclui processamento condicional ou certos mapas aninhados, o `dc:title` definido no mapa falha ao aparecer na capa do PDF, resultando em um título de capa ausente. (GUIDES-37733)
- Gerar a saída do site do AEM (usando o mapeamento de componente composto) para um mapa falha e resulta em erro quando a variável `map_title` está presente no caminho de saída. (GUIDES-36968)
- Quando um caminho de saída com uma barra à direita é especificado na predefinição de saída nativa do PDF, a interface do usuário anexa automaticamente uma barra à direita adicional, resultando em um caminho de barra dupla que faz com que o upload do PDF falhe em determinados cenários. (GUIDES-34932)
- Publicar páginas do AEM Sites geradas de conteúdo DITA por meio da Publicação rápida ou Gerenciar publicação publica involuntariamente os ativos DITA associados. (GUIDES-27967)
- Ao publicar um mapa no AEM Sites (usando o mapeamento de componente herdado), as referências cruzadas (`xrefs`) com `scope = peer` que direcionam subelementos de um tópico (como parágrafos) em um mapa diferente não resolvem a ID de elemento específica e resolvem somente o tópico pai, fazendo com que a página seja carregada no início do tópico, em vez de rolar até a seção desejada. (GUIDES-21802)


## Tradução

- Quando uma imagem gerenciada inicialmente como um ativo específico de idioma com uma versão específica (por exemplo, em `/en/`) é movida para uma pasta global com uma versão atualizada e a exportação da linha de base é executada, a nova linha de base continua a fazer referência a versões desatualizadas específicas de idioma dessa imagem, resultando em uma falha na exportação da linha de base. (GUIDES-39394)
- Ao processar projetos de tradução criados fora do Experience Manager Guides, várias mensagens de log de erros são geradas informando que a propriedade *`fmTarget`não foi encontrada*. (GUIDES-37804)

## Linha de base

- Ao criar uma linha de base dinâmica, o Editor às vezes não responde devido a várias solicitações de API simultâneas, fazendo com que todas as outras operações travem. (GUIDES-39054)

## Revisar

- Ao atribuir um usuário a uma tarefa de revisão, a lista suspensa lista todos os usuários em vez de apenas aqueles associados aos projetos selecionados, resultando em opções de usuário inválidas. (GUIDES-37781)

## Relatórios

- Ao abrir um Relatório para um mapa, há um atraso no carregamento do painel Filtros (GUIDES-39385)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2026.04.0:

- Uma tela em branco é carregada ao criar uma predefinição duplicada do ServiceNow Knowledge Base. (GUIDES-42732)
- A API para recuperar o estado do documento retorna uma resposta nula para alguns arquivos, fazendo com que estados de documento incorretos apareçam na interface do usuário. (GUIDES-42561)
- As personalizações da interface do usuário com base nos nomes das guias no Painel do mapa não são aplicadas. (GUIDES-42285)
- Quando um arquivo é aberto no Editor e no painel Pesquisar, excluí-lo do painel Explorer remove o arquivo e atualiza a lista do Explorer, mas atualizar a página continua exibindo o arquivo no painel Pesquisar. (GUIDES-41935)
- Ao atualizar uma tarefa de revisão ativa, se um tópico que já faz parte da revisão for removido e adicionado novamente sem clicar em **Atualizar**, as informações do(s) revisor(es) na guia Revisores serão perdidas.   (GUIDES-38774)
- Selecionar um tópico no modo de Visualização não o realça na exibição de Mapa se o tópico estiver dentro de tags de mapa (assunto principal, capítulo, parte ou backmatter) ou de parte do conteúdo cíclico. (GUIDES-42416)
- Na interface do usuário do Assets, o botão **Mover** não é habilitado na primeira tentativa quando mais de 2 arquivos ou pastas são selecionados. (GUIDES-42721) <br> **Solução alternativa**: depois de selecionar mais de dois arquivos ou pastas, aguarde alguns segundos antes de selecionar a pasta de destino.
- Quando você navega do Editor para **Preferências do usuário** e atualiza o mapa raiz enquanto o modo de Visualização está aberto no Editor, a visualização do mapa é carregada como uma tela em branco quando você retorna ao Editor. (GUIDES-42412) <br> **Solução alternativa**: atualizar a visualização usando o ícone **Atualizar** disponível no modo de Visualização resolve o problema.
- Renomear um modelo existente não atualiza o nome no painel **Modelos de saída** até que a página seja atualizada manualmente. (GUIDES-42528)<br> **Solução alternativa**: atualize o navegador para exibir o nome do modelo atualizado no painel Modelos de saída.
