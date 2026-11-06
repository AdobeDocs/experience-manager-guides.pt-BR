---
title: Notas de versão | Correção de problemas na versão 2026.11.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2026.11.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 0ebd3941a6ea5160c86e68a9ca6bdda50900a78d
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 0%

---

# Correção de problemas na versão 2026.11.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2026.11.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2026.11.0](./whats-new-2026-11-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.11.0](./upgrade-instructions-2026-11-0.md).

## Editor 2.0

- Quando uma linha de tabela é selecionada usando a navegação estrutural no Editor e a opção **Excluir** é selecionada no menu de contexto, somente o conteúdo da célula é removido, em vez da exclusão da linha inteira. (GUIDES-56759)
- Quando uma tabela é colada do Microsoft Word, as células da linha de cabeçalho são criadas, mas seu conteúdo é perdido. (GUIDES-49847)
- As alterações controladas nos arquivos criados antes de passar para o Editor 2.0 não aparecem no painel **Controlar alterações**. (GUIDES-44777)
- Quando o código é colado em um elemento `codeblock`, do Microsoft Word ou de editores de texto similares, usando Ctrl+V, quebras de linha e espaços à esquerda são perdidas e o código é nivelado em uma única linha. (GUIDES-33247)

## Criação

- Quando o Unified Shell está ativado, o cabeçalho do Adobe Experience Manager Guides também é exibido no Editor e no console do Mapa. (GUIDES-56812)
- Na interface do Assets, ações específicas de DITA, como **Exibir origem**, **Editar tópicos** e **Compartilhar link de UUID**, são exibidas para ativos que não sejam DITA. Além disso, o **Link de UUID de Compartilhamento** gera um link inválido para ativos que não têm uma UUID. (GUIDES-47043)
- No painel Esquema do assunto, o título exibido é escolhido somente do atributo `navtitle`. O elemento `navtitle` é ignorado mesmo quando ambos estão presentes. (GUIDES-37722)
- Na **exibição de Título** do painel Repositório, as reticências não estão inicialmente visíveis para arquivos com nomes longos. Ao clicar com o botão direito do mouse em um arquivo desse tipo, as reticências e o menu de contexto aparecem bem à direita do arquivo, às vezes parcialmente fora da tela. (GUIDES-37118)
- No painel Condições, as condições são classificadas alfabeticamente com base em seus valores em vez de seus rótulos. (GUIDES-14593)
- Nos Modelos de saída, o botão **Novo estilo** (+) não é exibido no painel Estilos quando uma folha de estilos, como layout.css, é aberta. (GUIDES-49448)

## Gerenciamento de ativos

- Ao carregar um arquivo modificado usando a opção **Substituir arquivo existente**, o carregamento parecerá ser concluído se o arquivo existente não tiver Guides UUID e estiver armazenado em uma pasta listada em **Caminhos Ignorados para Pós-Processamento**. No entanto, o arquivo existente não é substituído e nenhuma nova versão é criada. (GUIDES-55866)
- Em um bookmap, quando um elemento `booktitle` contém vários subelementos, como `booklibrary` e `mainbooktitle`, espaços em branco extras são adicionados entre seus valores nos metadados `dc:title`. (GUIDES-28877)

## Publicação

- No console Mapa, depois que a saída é gerada para um mapa, o botão **Gerar** é desabilitado quando outro mapa é aberto. Atualizar o navegador ativa o botão novamente. (GUIDES-54591)
- A publicação de determinados mapas em um site do AEM com mapeamento de componentes falha com um erro enquanto o índice é criado. (GUIDES-53807)
- A publicação de um mapa em um site do AEM com mapeamento de componente falha quando o mapa contém um elemento `topicref` com um atributo `navtitle` e nenhum atributo `href`. As tentativas subsequentes também falham, mesmo após a remoção do elemento, até que os nós de site gerados sejam excluídos. (GUIDES-53707)
- Na saída do site do AEM com mapeamento de componente, os cabeçalhos do Markdown de níveis 2 a 6 são renderizados como cabeçalhos de nível 1. (GUIDES-51134)
- Para a saída do site do AEM com mapeamento de componente, os metadados do prólogo, como autor, palavras-chave e ID de recurso, aparecem no corpo da página da saída publicada. (GUIDES-44087)
- Quando um tópico é publicado no ServiceNow, o corpo do artigo inclui a descrição curta e o prólogo do tópico. (GUIDES-47868)
- Quando um tópico já publicado no ServiceNow é publicado novamente, um novo artigo é criado no estado Rascunho, em vez de substituir o artigo existente. (GUIDES-37872)
- Quando as predefinições de condição excluem referências de tópico durante a publicação no Salesforce, a geração de saída é relatada como falha, mesmo que os tópicos restantes sejam publicados com êxito. (GUIDES-37807)
- A publicação de um mapa grande no Salesforce falha com um erro de tempo limite do gateway. (GUIDES-33722)
- A publicação de um mapa no Salesforce falha com um erro de limite excedido quando uma solicitação contém mais de 25 operações. (GUIDES-33721)
- No Painel do Mapa (Antigo), **Adicionar tudo** em uma predefinição de condição existente não seleciona valores de condição que foram adicionados ou alterados após a criação da predefinição. (GUIDES-45940)
- Os logs na página **Histórico de saída** contendo avisos são mostrados com um ícone verde, que não indica que há avisos presentes. (GUIDES-27000)
- O glossário não é incluído na saída quando nenhum termo no conteúdo do mapa se refere a uma entrada do glossário. (GUIDES-52964)
- Os tópicos de um submapa referenciado em um apêndice são renderizados como capítulos em vez do conteúdo do apêndice. (GUIDES-52775)
- Alguns caracteres de chinês simplificado são renderizados com uma fonte japonesa quando o idioma de saída é definido como chinês (simplificado). (GUIDES-48094)
- As entradas de índice perdem o texto de elementos filhos, como `keyword`, `ph` e `sup`. Como resultado, alguns rótulos de índice estão incompletos ou vazios. (GUIDES-40902)
- Espaços ao redor dos elementos `option` incorporados não são retidos, levando ao texto adjacente que aparece unido. (GUIDES-40900)

## Tradução

- Na página Tradução, pesquisar e classificar por **Título** use o valor de metadados localizado em vez do título exibido na coluna. (GUIDES-45396)

## Revisar

- Na página **Revisores**, durante a criação ou edição de uma tarefa de revisão, os botões **Limpar Seleção**, **Adicionar Revisores**, **Remover Revisores** e **Reatribuir Revisores** são habilitados por padrão, mesmo quando nenhuma linha é selecionada. (GUIDES-35125)
- Na caixa de entrada do AEM, as notificações relacionadas às tarefas de revisão, como atribuição de tarefa, feedback recebido, menções e lembretes de vencimentos ou vencidos, são exibidas sem nenhum nome de projeto. (GUIDES-10912)
- Na exibição Lado a lado de um tópico em uma tarefa de revisão, o conteúdo marcado com tachado aparece com formatação diferente nas duas exibições. (GUIDES-56079)

## Conteúdo de aprendizado

- A geração de uma saída SCORM para um curso grande, normalmente de 300 MB a 600 MB, leva mais de 30 minutos e falha sem detalhes de erro nos registros. (GUIDES-56101)
- Os critérios de conclusão de uma saída SCORM não podem ser definidos no Experience Manager Guides. (GUIDES-55520)
- As imagens no formato AVIF são exibidas no editor, mas estão ausentes na saída publicada. (GUIDES-55515)
- O atributo `href` é removido das marcas de âncora na saída publicada, portanto, os links não são clicáveis. (GUIDES-55514)

## Platform

- Quando um usuário é atribuído como um Usuário administrador em um perfil de pasta, mas não é membro do grupo de administradores, ele não pode adicionar outros Usuários administradores com êxito. Embora uma mensagem de sucesso seja exibida, os usuários recém-adicionados desaparecem após atualizar a página. (GUIDES-50144)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2026.11.0:

## Criação

- Ao criar um mapa a partir de um modelo contendo tópicos ou submapas dependentes, a criação do mapa pode falhar intermitentemente com um erro, especialmente quando o servidor está sob carga pesada. (GUIDES-58715)

### Editor 2.0

- A opção **Atualizar atributo de título de navegação** não adiciona o atributo `@navtitle` aos elementos `topicref` existentes em um mapa DITA. (GUIDES-54348)

**Controlar alterações**

Quando o **Controle de alterações** está ativado:

- As exclusões aninhadas pelo mesmo usuário nem sempre são mescladas em uma única entrada quando o elemento que contém o conteúdo excluído é renomeado ou formatado. (GUIDES-58429)
- O painel **Controlar alterações** às vezes mostra conteúdo incompleto para o elemento pai quando uma exclusão aninhada é feita por um usuário diferente. (GUIDES-58428)
- O marcador de canaleta vermelho não aparece à esquerda quando você exclui conteúdo em uma inserção feita por outro usuário. (GUIDES-58418)

### Publicação

- Na saída do PDF nativo, a formatação sobrescrita e subscrita não é preservada nas entradas de índice. (GUIDES-58349)
- Quando você usa a mesma predefinição global para gerar saída para mapas diferentes, a seleção de tópico do mapa anterior pode afetar a saída do novo mapa. (GUIDES-58346)
- A publicação de um mapa às vezes resulta em uma página em branco quando, em um cenário específico, um `<chapter>` define simultaneamente um destino `href` direto e esse capítulo contém elementos filho `<topicref>` aninhados. (GUIDES-58266)
- Ao navegar para a guia **Histórico de saída** de uma predefinição com alterações não salvas, os botões **Salvar** e **Gerar saída** permanecem visíveis. (GUIDES-57989)
- Quando um fluxo de trabalho de pós-publicação é configurado para uma predefinição, a duração da publicação mostrada em **Histórico de saídas** não inclui o tempo gasto pelo fluxo de trabalho. (GUIDES-57856)
- Não é possível cancelar a geração de saída do PDF Nativo da página **Histórico de saída**. (GUIDES-57821)

### Revisar

- Abrir uma tarefa de revisão criada na versão 2026.08.0 ou 2026.09.0 às vezes resulta em um erro de aplicativo quando o conteúdo revisado contém *qualquer anotação de revisão* com espaços não separáveis (`&nbsp;`). (GUIDES-56583) <br>**Solução alternativa:** Conclua ou feche todas as tarefas de revisão criadas nessas versões.

