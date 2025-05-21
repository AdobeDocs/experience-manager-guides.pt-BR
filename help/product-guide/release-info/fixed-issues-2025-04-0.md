---
title: Notas de versão | Correção de problemas na versão 2025.04.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2025.04.0 do Adobe Experience Manager Guides as a Cloud Service.
exl-id: ad3e95b5-4903-4387-8e4d-c4b9ba77fee2
source-git-commit: 70078864379eedd82ae21da70614055c60f0b114
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 0%

---

# Correção de problemas na versão 2025.04.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2025.04.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2025.04.0](whats-new-2025-04-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.04.0](upgrade-instructions-2025-04-0.md).

## Criação  

- A caixa de inserção de caracteres especiais no Editor não é carregada para o locale alemão. (24537)
- Comentários e rótulos adicionados ao salvar uma nova versão de um arquivo DITAVAL não são salvos no Histórico de versões com a nova versão. (24076)
- As referências de saída e de entrada em **Propriedades do arquivo** no painel direito não são atualizadas corretamente ao alternar entre arquivos de mapa. Esse problema ocorre especificamente quando os arquivos de mapa contêm um grande número de referências. (23344)
- O filtro Repository não retém a ordem dos filtros personalizados definidos em `ui_config.json`. (21193)
- A exclusão de várias linhas de texto em um elemento `codeblock` cria um espaço vazio que não pode ser removido da exibição Autor. (20672)
- Não é possível gerar novas IDs para elementos quando esses elementos são adicionados através de trechos ou criados através de modelos, mesmo quando a opção **gerar ID automaticamente** está habilitada em `XMLEditorConfig`. (21734)
- A criação de um novo ativo DITA a partir de modelos DITA copia as propriedades de replicação dos modelos DITA correspondentes. (25145)
- Não é possível acessar as propriedades do arquivo no painel de repositório se o nome da pasta pai incluir o caractere &quot;&amp;&quot;. (25762)
- Fechar um arquivo de tópico permite que ele seja salvo como uma nova versão, mesmo quando o tópico estiver bloqueado. Este problema ocorre especificamente quando a opção **Solicitar nova versão ao fechar** está habilitada em `XMLEditorConfig`. (23875)
- A largura máxima atual do painel do repositório oculta títulos de tópico e mapa quando a hierarquia de conteúdo está profundamente aninhada. (27751)

## Publicação

- Na saída herdada do AEM Sites, os links de seção dentro de tópicos aninhados de um mapa não são resolvidos corretamente quando definidos manualmente no modo Source ou o conteúdo é importado de uma fonte externa. Em vez de navegar até a seção desejada, eles redirecionam para o tópico principal que contém o tópico aninhado. (26103)
- Se o atributo `scope=external` estiver ausente em links externos em um tópico DITA, a publicação do HTML5 falhará sem indicar os arquivos em que esse atributo está ausente nos logs de erro, especialmente quando o microsserviço está habilitado. (25969)
- Não é possível incorporar links de vídeo no PDF Nativo, mesmo quando a opção **Incorporar Arquivos de Multimídia** está habilitada na predefinição do PDF. (9989)
- Não é possível passar as propriedades de metadados para mapear páginas de aterrissagem geradas usando a nova publicação do AEM Sites. (27288)

## Gerenciamento

- O estado do documento da cópia de trabalho de um tópico é exibido em relação a todas as versões desse tópico na interface de Tradução e Linha de base. (20674)


## Revisar

- Atualizar os detalhes de uma tarefa de revisão no painel Revisão não confirma se a atualização foi bem-sucedida ou malsucedida. (8051)

## Tradução

- As traduções enviadas por meio do Experience Manager Guides não incluem os ativos anexados, fazendo com que o botão **Iniciar** do trabalho de tradução fique indisponível para os usuários.

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2025.04.0:

- A contagem de referências na interface do usuário da Linha de base não é atualizada ao editar a Linha de base. Ela só é atualizada quando as alterações são salvas. (28015)
- Quando várias guias são abertas no Editor, executar uma operação **Desfazer** na exibição **Source** de um arquivo reverte a última edição, mas também alterna para a guia aberta anteriormente. (27891)
- A opção **Verificação ortográfica do AEM** aparece na lista suspensa **Menu**, mesmo quando a opção **Verificação ortográfica do navegador** está habilitada nas configurações do Editor. (27993)
- Uma versão adicional é criada e mostrada no painel **Histórico de Versão** quando você edita uma imagem na interface do usuário do Assets e a salva. (28001)
- Uma linha vazia é inserida automaticamente ao colar o novo conteúdo em uma nova linha em um elemento `codeblock`.(27842)
- Alternar entre predefinições que usam a mesma Linha de Base desativa o botão **Salvar** para a predefinição atual. (28025)
- Um tópico em um mapa DITA não é publicado na saída do AEM Sites quando está sendo usado como `keydef` e `topicref` em seus submapas. (22269)
- Um erro de aplicativo ocorre quando vários tópicos de um mapa são editados e fechados usando a opção **Fechar tudo**, com a configuração **Perguntar ao salvar versão ao fechar** habilitada.(27931)

A Adobe identificou o seguinte problema conhecido com uma solução alternativa:

+++Na saída do AEM Sites, as imagens são interrompidas quando a Linha de base não é aplicada durante a publicação. (28043)
***Solução alternativa:*** você pode publicar esses ativos na **Interface do usuário do Assets**, postar onde o link se tornará operacional.
+++