---
title: Notas de versão | Correção de problemas na versão 2025.02.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2025.02.0 do Adobe Experience Manager Guides as a Cloud Service.
exl-id: e7dec4a2-e11a-4b78-8111-a331d20ce73d
source-git-commit: 71971c25094b842cb7a0bd1f5bd2acbca4212a66
workflow-type: tm+mt
source-wordcount: '1325'
ht-degree: 0%

---

# Correção de problemas na versão 2025.02.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2025.02.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2025.02.0](whats-new-2025-02-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.02.0](upgrade-instructions-2025-02-0.md).


## Criação  

- Ao atualizar as condições do perfil da pasta, todos os grupos de condições são perdidos e as condições são niveladas. (23526)
- A alteração do valor das linhas de cabeçalho de uma tabela no painel **Propriedades de conteúdo** não aplica o valor atualizado. (23213)
- Para transições subsequentes de estado do documento de Guias, é necessária uma atualização de página. (19421)
- Ao adicionar tópicos no mapa DITA usando a caixa de diálogo de elemento **Referência de tópico** na exibição **Autor**, os tópicos selecionados são inseridos na ordem inversa de serem selecionados. (8031)
- Ao alternar entre a exibição **Autor** e a exibição **Source**, os espaços à esquerda nos elementos `<pre>` ou `<codeblock>` são excluídos e o arquivo é salvo com esta exclusão. (1998)
- O Estado do Documento marcado como **Concluído** reverte para **Rascunho** antes de salvar uma nova versão, resultando no estado **Concluído** que não persiste em nenhuma versão do documento. (2006)
- Quando os itens de lista são movidos para fora da tag para, o conteúdo do item de lista é perdido. (22764)
- Ao adicionar tópicos no mapa DITA usando a caixa de diálogo de elemento **Referência de tópico** na exibição **Autor**, os tópicos selecionados são inseridos na ordem inversa de serem selecionados. (22858)
- Ao adicionar novas referências de tópico no mapa DITA usando a caixa de diálogo de elemento **Referência de tópico** no modo de exibição **Layout**, as referências adicionadas serão mostradas como links desfeitos. (22859)
- Ao clicar com o botão direito do mouse na tag `<simpletable>` dentro de um tópico, a opção **Renomear** não é exibida. (22860)
- Quando você insere um `xref` que utiliza uma referência baseada em chave com texto de link, o texto do link não é exibido no Experience Manager Guides. 18775)
- Arrastar e soltar uma imagem em um tópico na exibição **Autor** faz com que a referência da imagem seja interrompida, resultando em perda de dados. (25769)
- Ao pesquisar arquivos no repositório usando a funcionalidade **Pesquisar e filtrar**, não é possível selecionar vários arquivos. (25104)
- Ao copiar uma imagem de qualquer produto externo (por exemplo, MS PowerPoint) e colá-la nos Guias, a funcionalidade de fazer upload do ativo instantaneamente para uso no arquivo do é interrompida. (24983)
- Arrastar um `topicref` sobre outro (no modo de exibição **Autor** ou **Layout**) solicita uma confirmação para substituição em vez de aninhar, e selecionar **Não** na caixa de diálogo de confirmação ainda fará com que o conteúdo seja substituído, resultando em perda de dados. (18602)
- Não é possível adicionar vários atalhos a um único evento, nem adicionar um argumento a um evento ao acioná-lo a partir de um atalho. (1906)
- Ao recarregar o navegador, a guia de imagem fechada anteriormente é reaberta. (19267)
- Selecionar parcialmente o texto em um elemento de parágrafo ou lista e arrastá-lo para fora do elemento causa perda de conteúdo ao alternar entre as exibições do **Author** e do **Source**. (25790)

## Publicação

- A publicação no Salesforce falha quando o conteúdo contém espaços não separáveis. (23664)
- Para mapas com links quebrados, a publicação do Salesforce falha e a barra de progresso é exibida indefinidamente. (24963)
- Para tópicos com erros como links quebrados, a publicação no Salesforce falha e a barra de progresso é exibida indefinidamente. (22985)
- Falha na publicação de pdf nativo para a opção de conformidade **PDF/X-4**. Erro: **os documentos PDF/X-4 exigem um título não vazio**. (16904)
- Quando o texto de espaço reservado é usado, as referências cruzadas que usam `<keyref>` no PDF Nativo não são resolvidas. (19365)
- Falha na geração de PDF nativo para conteúdo com **atributo de parte** definido como **para conteúdo**. (21772)
- Ao gerar uma saída Native PDF, o elemento `ditavalref` não é suportado. (16320)
- Ao editar um arquivo CSS grande no editor de CSS nativo do PDF, um atraso significativo é observado. (16915)
- Para publicações baseadas em HTML5, o sinalizador DITA-OT generate.copy.outer é aplicado automaticamente. (24299)
- A referência cruzada converte em link relativo mesmo quando o **escopo** do link está definido como **externo**. (23059)
- Quando um arquivo ICC está disponível em um caminho interno, ele não pode ser selecionado nas configurações **Imprimir** para a predefinição Nativa do PDF. (14741)
- Quando várias solicitações de publicação são iniciadas para mapas diferentes usando a mesma predefinição de perfil de pasta, a publicação falha. (18800)
- Para tópicos com metadados/propriedades de vários valores passados para o DITA OT, a publicação falha. (19001)
- A caixa de diálogo **Editar propriedades** de uma linha de base não mostra os critérios salvos anteriormente para a linha de base dinâmica.  (23964)
- A linha de base não inclui referências indiretas quando o conteúdo está no estado final do documento. (19148)
- A configuração **Limpar nomes de página e nomes de arquivo para AEM Sites e outros formatos de saída** é aplicável a todos os formatos de saída. (7651)
- Se um link externo contiver uma UUID, ele entrará no pós-processamento e converterá o link externo em link UUID, quebrando o link no editor da Web e também nos sites de publicação. (22574)


## Gerenciamento

- Vazamentos de recursos ocorrem devido a erros Unclosed **ResourceResolver** em logs. (18488)
- O título e o ícone da caixa de diálogo **Forçar exclusão** estão desalinhados na interface do Assets. (21933)
- Quando qualquer JSON é atualizado no perfil de pasta para Configuração do editor XML, a operação de salvamento interrompe a configuração do editor XML. (22414)
- Ao duplicar qualquer perfil de pasta, sua lista de usuários administradores também é copiada do perfil da pasta original. (19067)
- Ocorre um erro ao mover pastas grandes (com um grande volume de conteúdo DITA, até 200.000 itens) da interface do Assets. (2010)
- Ao usar o título dinâmico com `<conkeyref>`, ele não é resolvido corretamente na **Lista de Tópicos de Relatório de Guias**. (2014)
- A edição do perfil **Pasta** com o Unified Shell habilitado resulta em uma interface em branco. (22212)
- Ao excluir pastas que contêm um grande número de arquivos, a operação falha. (17107)
- Ao cancelar/excluir o trabalho de tradução ou excluir o projeto, o painel de tradução mostra o status **Em andamento**. (18417)
- Quando você habilita o Unified Shell para uma instância da nuvem, a visualização do tópico não abre a partir do painel do mapa. (18826)
- Ao enviar duas versões de um tópico não traduzido simultaneamente usando tradução não herdada e aprovar a segunda versão antes da primeira, o projeto de tradução com a primeira versão é corrompido. (22200)


## Revisar

- Ao selecionar vários tópicos para revisão em um mapa, a notificação por email que o revisor recebe indica que todos os tópicos no mapa estão disponíveis para revisão, em vez de apenas os selecionados. (23214)
- O título do tópico e o ícone estão desalinhados na interface de criação da revisão. (11670)


## APIs

- Erro ao criar uma **Linha de Base** usando a API de Guias acionando o serviço **BaslinUtlis**. (19385)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2025.02.0:

- Ao usar imagens como variáveis no modelo PDF, ele não resolve na saída.
- O recurso **Localizar no repositório** não funciona ao abrir o Editor de Guias pela primeira vez, mas começa a funcionar conforme esperado após atualizar o navegador.
- Nos relatórios da **Lista de tópicos**, a classificação por título falha para ativos com `<conref>` ou `<conkeyref>` no título, fazendo com que essas entradas sempre apareçam na parte superior.
- Alternar o perfil da pasta não reflete imediatamente as alterações na interface do usuário sem atualizar o navegador.
- As personalizações da estrutura de extensão feitas antes do Guides 2025.02.x.x podem não funcionar conforme esperado.
- O índice completo do mapa não é atualizado ao publicar tópicos do mapa de maneira seletiva.
- Falha na publicação de um mapa que contém um arquivo do Markdown com referências internas de imagem nos servidores Windows.
- A lista com marcadores não é convertida em lista numerada no Markdown.
- A publicação no site nativo do AEM falha quando os arquivos de marcação são referenciados em um mapa.
- A posição da cor do plano de fundo está desalinhada na interface do usuário do **Painel da condição**.
- Quando você usa a imagem como um `<keyref>`, o **Tipo de Referência** da imagem não é mostrado no **Relatório multimídia**.
- Em alguns casos, a funcionalidade de bloqueio para arquivos CSS não está funcionando como esperado, permitindo que outros usuários editem e salvem os arquivos mesmo quando eles são bloqueados por outro usuário.
- A aplicação de alterações na configuração predefinida não reflete as predefinições já criadas no mapa se o nome da predefinição tiver qualquer caractere em maiúsculas.
- Ao abrir um mapa DITA com o Unified Shell ativado, o editor é atualizado intermitentemente.
