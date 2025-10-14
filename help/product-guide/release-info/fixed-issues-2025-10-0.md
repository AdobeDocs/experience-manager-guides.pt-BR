---
title: Notas de versão | Correção de problemas na versão 2025.10.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2025.10.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: ff3cf777bd348edded29d780031df59bbb03035d
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 0%

---

# Correção de problemas na versão 2025.10.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2025.10.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2025.10.0](whats-new-2025-10-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.10.0](upgrade-instructions-2025-10-0.md).

## Criação

- Quando vários mapas DITA ou tópicos são abertos e um dos tópicos é fechado, o botão **>>**, que mostra todas as guias abertas, é sobreposto às guias abertas restantes na barra de guias. (GUIDES-31421)
- Com o **fluxo de trabalho de aprovação** habilitado, o botão **Iniciar uma Nova Versão** não ficará visível na barra de ferramentas do Editor se o painel Esquerdo e o painel Propriedades de conteúdo estiverem abertos. (GUIDES-29093)
- Quando os nomes dos trechos excedem a largura do painel, eles são quebrados incorretamente na próxima linha, resultando em sobreposição com trechos adjacentes e afetando a legibilidade. (GUIDES-22685)
- Quando você adiciona a mesma referência várias vezes a um mapa DITA, a exibição **Mapa** exibe o título somente para a última ocorrência, enquanto as anteriores mostram a UUID da referência. (GUIDES-9699)
- Os arquivos DITAVAL permanecem editáveis, mesmo quando são bloqueados por outro usuário ou quando o servidor tem a opção **Desativar edição sem bloquear o arquivo** habilitada e o arquivo é aberto no modo somente leitura. (GUIDES-27754)
- Os logs de nós ausentes estão sendo gerados de trabalhos de limpeza interna que não são necessários e são marcados incorretamente como erros, resultando em arquivos de log desorganizados. (GUIDES-31765)


## Publicação

- Ao gerar PDFs, as regras de filtragem em um arquivo DITAVAL serão ignoradas se qualquer nome de propriedade contiver um ponto. (GUIDES-33229)
- A publicação do Salesforce falha com um erro de aplicativo, quando já existe um tópico com o mesmo nome e URL. (GUIAS- 32390)
- A publicação do Salesforce exibe um status de sucesso na interface do usuário mesmo quando um mapa DITA contendo um elemento `topichead` não publica os tópicos nele. (GUIDES-32143)
- Para a predefinição de saída do HTML5, a funcionalidade de filtro de pesquisa não está funcionando no AEM Assets para a filtragem DITAVAL, pois os arquivos correspondentes não são exibidos quando o filtro DITAVAL é selecionado. (GUIDES-28231)
- Ao gerar um PDF Nativo para um mapa DITA com vários tópicos, se qualquer tópico contiver um elemento `fig` em um `figgroup` junto com um `title`, o título `figgroup` será renderizado incorretamente como um título de capítulo no Índice. (GUIDES-23223)
- Ao duplicar modelos do PDF da interface do usuário, a UUID também é duplicada, fazendo com que os arquivos de modelo sejam excluídos e resultando em saídas incorretas do PDF. (GUIDES-30456)
- Ao gerar o PDF Nativo para um mapa DITA, o título do elemento `example` é renderizado como nível de cabeçalho `h1`, resultando em inconsistência visual e estrutura de índice inadequada. (GUIDES-19958)

## Tradução

- Ao ampliar a tela da interface de tradução, o botão **Enviar para tradução** fica abaixo das reticências e é habilitado mesmo sem que nenhum ativo seja selecionado. (GUIDES-33720)
- Ao selecionar arquivos com o status **Fora de sincronização** na interface de tradução e a largura da tela estiver restrita devido à abertura dos painéis Esquerdo e Direito, o rótulo **Enviar para tradução** fica truncado. (GUIDES-33692)

## Revisar

- Quando um revisor conclui uma tarefa de revisão ou o iniciador atualiza a tarefa de revisão sem inserir comentários, o email de notificação enviado exibe o comentário anterior mais recente. (GUIDES-33590)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2025.10.0:

- Ao abrir uma URL com um tópico DITA aberto anteriormente ou atualizar um tópico DITA aberto, ocorre uma falha ao localizar o tópico no repositório, apesar da configuração **Sempre localizar arquivos no repositório** estar habilitada nas preferências do usuário. (GUIDES-35565)<br>**Solução alternativa**: selecione a guia de tópico para localizar o arquivo no repositório.

- Ao criar um novo arquivo na visualização Autor com vários arquivos já abertos, o painel Direito não é atualizado e exibe dados incorretos se o cursor for colocado em uma tag de elemento em um arquivo diferente. (GUIDES-35450)<br>**Solução alternativa**: trocar de guia ou atualizar a página para resolver o problema.

- Ao alternar para a visualização Autor na visualização Source para um tópico recém-aberto (que é aberto inicialmente no modo Source), o conteúdo do tópico fica em branco. (GUIDES-35000)<br>**Solução alternativa**: atualize a página ou reabra o tópico para resolver o problema.

- O botão **Atualizar navegação** está aparecendo para arquivos de tópico DITA, embora só deva estar disponível para mapas DITA, mapas de livros e esquemas de assunto. (GUIDES-35452)






