---
title: Notas de versão | Versão as a Cloud Service do Adobe Experience Manager Guides de maio de 2022
description: Lançamento de maio do Adobe Experience Manager Guides as a Cloud Service
exl-id: 7928a300-5ec9-492c-b9be-02b6f87638c6
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# Lançamento de maio do Adobe Experience Manager Guides as a Cloud Service

## Atualização para a versão de maio

Atualize sua configuração atual do Adobe Experience Manager Guides as a Cloud Service (mais tarde chamada de configuração do *AEM Guides as a Cloud Service*) executando as seguintes etapas:
1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
1. Atualize a propriedade `<dox.version>` no arquivo `/dox/dox.installer/pom.xml` do código Git do Cloud Service para 2022.5.144.
1. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de maio do AEM Guides as a Cloud Service.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com a versão de as a Cloud Service de maio de 2022 da AEM Guides.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Não compatível | Atualização 4 e superior para 2020 |
| | |

*A linha de base e as condições criadas no AEM são compatíveis com as versões do FMPS a partir de 2020.2.

### Conector de oxigênio

| Versão do AEM Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac |
| --- | --- | --- |
| 2022.5.0 | 2.6.9 | 2.6.9 |
|  |  |  |


## Novos recursos e melhorias

O AEM Guides as a Cloud Service fornece vários aprimoramentos e novos recursos na versão de maio:

### Editor da Web aprimorado

* **Criar mapas com base em modelos personalizados**

Agora você tem o recurso poderoso para criar modelos de mapa personalizados. Você pode usá-los para criar mapas DITA juntamente com os modelos de tópico e de mapa referenciados no modelo de mapa.

![modelos dita](assets/dita-templates.png)

Também é possível consultar outros modelos de mapa e modelos de tópico do modelo de mapa personalizado. Os modelos de mapa referenciados podem se referir a vários modelos de mapa, modelos de tópico, tópicos, mapas, imagens, vídeos e outros ativos.

![criar modelos de dita](assets/create-dita-template.png)

O modelo de mapa personalizado pode ajudá-lo a replicar com facilidade os modelos de mapa e toda a estrutura de pastas indicada. Esses modelos personalizados são especialmente úteis para criar e recriar vários mapas que têm estruturas e referências recursivas.

* O recurso **Inserir Palavra-chave** foi aprimorado. Agora é possível encontrar mais facilmente uma Palavra-chave a ser inserida, pois as palavras-chave são listadas em ordem alfabética. Você também pode pesquisar palavras-chave digitando uma string de pesquisa na caixa Pesquisar.

![inserir palavra-chave](assets/insert-keyword.png)

* Agora, na Exibição do repositório, os arquivos são carregados em lotes. São carregados 75 arquivos de cada vez. Esse carregamento em lote é eficiente, e você pode acessar os arquivos mais rapidamente em comparação ao carregamento de todos os arquivos existentes em uma pasta.

![carregar mais arquivos](assets/load-more-files.png)

* É possível renderizar imagens de SVG que incluem dados ou links incorporados em todas as telas do editor XML, incluindo, mas não limitado à, visualização e Autor.

* O XSD/DTD padrão pode ser atualizado para a versão mais recente

### Processo de tradução aprimorado

* **Capacidade de criar um projeto de tradução de escopo**
Se precisar criar somente o escopo para que um projeto seja traduzido, você pode selecionar **Criar um novo projeto de tradução de escopo**. Isso não enviará as cópias para tradução e o status original da tradução dos arquivos será mantido.

![projeto de tradução de escopo](assets/scoping-translation-project.png)

* Se você rejeitar a tradução de um ou mais tópicos em um trabalho de tradução, o status Em andamento da tradução de todos os tópicos rejeitados será revertido para seu status original.

* A lista **Idiomas** exibe as pastas de idioma junto com seus códigos de idioma. Por exemplo, francês (fr) e alemão (de).

* O recurso de tradução agora também oferece suporte ao código de idioma, que inclui o país e o idioma. Por exemplo, `fr-fr`, `en-us`.

![idioma de tradução](assets/translation-languages.png)

* Ao carregar um mapa DITA que esteja fora da pasta de idioma, nenhuma exceção é registrada no back-end.

Para obter mais detalhes sobre a tradução, consulte a seção *Traduzir documentos do Editor da Web* em Uso do Adobe Experience Manager Guides as a Cloud Service.


### Publicação aprimorada

* Você também pode acessar o **Painel do Publish** na guia Saídas enquanto gera a saída do painel do mapa. Uma lista de todas as tarefas de publicação ativas está disponível no Painel do Publish.

![saídas na fila](assets/queued-output.png)

* No painel de mapa, é possível selecionar vários arquivos DITAVAL para gerar conteúdo condicional. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Você também pode passar o mouse sobre o nome do arquivo para ver o caminho no repositório AEM onde o arquivo está armazenado.

* **Recurso obsoleto**
O AEM as a Cloud Service não oferece mais suporte à geração de formato de saída DITA para documentos do FrameMaker. Essa opção DITA também foi removida das Predefinições de saída do painel Mapa.

### Publicação aprimorada baseada em artigos

O Editor de XML oferece a capacidade de mapear mais de uma categoria de produto para um artigo enquanto publica em um perfil do Salesforce.

### Outras melhorias de recursos

* O modo de Visualização também oferece suporte ao atributo de processamento condicional `deliveryTarget` em DITA. Está disponível como uma opção no filtro suspenso junto com **público-alvo**, **plataforma**, **produto**, propriedades, **outras propriedades**.
* Foi fornecida uma opção para a sincronização forçada entre o servidor AEM no Oxygen e o sistema local.

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

* No painel de revisão do Editor da Web, o usuário não pode responder aos comentários de revisão. (9667)
* O aplicativo fica em branco ao clicar em uma pasta em branco após atualizá-la por meio do menu Opções. (9639)
* Uma nova versão está sendo criada quando **Salvamos e Fechamos** o arquivo com check-in. (9638)
* O botão Fechar não é exibido quando a caixa de seleção **Salvar como nova versão** está habilitada. (9637)
* O PDF correto não será publicado se for publicado primeiro por meio de um PDF separado para cada capítulo e, em seguida, um único arquivo de PDF (a opção Criar arquivos de PDF separados está desmarcada). (9632)
* O painel de mapa está gerando um problema de metadados para usuários não administradores. (9620)
* Depois que uma linha de base é criada, o status é definido como falha na interface (a chamada get status está falhando) se o servidor estiver tendo mais de 10000 arquivos. (9608)
* Armazenar grandes dados em propriedades resulta em um erro de publicação, pois o fluxo de trabalho de publicação dividido falha. (9586)
* O estado dos Filtros de atributos condicionais não é preservado ao alternar entre o modo de Visualização para o Source e novamente o modo de Visualização. (9553)
* O nome do mapa está ficando em branco na exibição Repositório caso nenhum nome seja fornecido por meio da tag `mainbooktitle`. (9538)
* HTTP 400 ocorre ao abrir um arquivo carregado usando o Oxygen. (9535)
* As Predefinições de um mapa aberto anteriormente permanecem visíveis na guia Saída ao abrir um mapa sem predefinições definidas. (9523)
* A funcionalidade de pesquisa de Tags e Atributos não está funcionando no painel Estrutura de tópicos. (9506)
* A coleção recém-criada não estará visível até que o navegador seja atualizado. (9505)
* Os rótulos de Atributos condicionais (não os valores) aparecem no modo de origem ao adicionar todas as condições por meio da opção &quot;Adicionar todas as props&quot;. (9501)
* O check-out dos arquivos é feito automaticamente ao reverter para qualquer versão. (9482)
* Diferenças incorretas de carimbo de data e hora são exibidas na interface do usuário do Assets ao reverter uma versão de arquivo. (9480)
* Vários itens dos resultados da pesquisa são adicionados ao inserir itens no elemento topicref do mapa DITA. (9474)
* Se a configuração **Criar nova versão para arquivo carregado** estiver ATIVADA, uma nova versão será criada ao reverter e salvar em qualquer nó congelado. (9473)
* O texto de exibição da Referência principal e da Referência de chave de conteúdo não é mantido ao alterar o URL do link, se o texto de exibição não for adicionado ao definir a referência principal. (9458)
* No Histórico de versões, o número da versão e o rótulo não são exibidos para a versão atual. (9446)
* O editor congela quando determinados arquivos de conteúdo são abertos no editor. (9443)
* Pesquisar no painel Repositório e a caixa de diálogo Procurar topicref congela a tela quando o conteúdo é grande. (9432)
* Os metadados transmitidos para a saída do site AEM não respeitam a linha de base do conteúdo. (9416)
* O Oxygen verifica uma versão incorreta de um tópico após uma reversão de versão no AEM. (9411)
* Falha na linha de base desativa a edição na guia Predefinição do painel do mapa. (9403)
* O erro sempre é registrado na criação de novo conteúdo. (9388)
* Os ativos DITA recém-criados sempre passam por check-out por outro usuário. (9387)
* A renomeação do elemento não está funcionando corretamente ao converter topicref em glossref. (9380)
* O Rótulo da Versão não vem como lista suspensa na caixa de diálogo **Salvar como Nova Versão**. (9379)
* As condições não estão sendo aplicadas ao alternar entre diferentes versões da lista suspensa **Mostrar comparação**. (9366)
* Vários problemas ocorrem ao usar os filtros de Visualização. (9365)
* Não é possível inserir ativos não DITA e DITAVAL em topicref. (9363)
* A tradução aprovada não é integrada ao idioma de destino quando o código do idioma de destino contém cinco caracteres como `fr_ca`. (9357)
* Não é possível pesquisar arquivos usando **Localizar Arquivos na Pasta** no menu **Mais Opções** e o aplicativo fica sem resposta. (9337)
* A caixa de diálogo Procurar trava se houver um grande número de chaves. (9332)
* Os arquivos DITAVAL não funcionam durante a publicação baseada em artigos. (9330)
* A ordem das notas de rodapé está incorreta na saída do site AEM. (9327)
* A pesquisa não é executada automaticamente quando o caminho selecionado é alterado. (9323)
* Quando a tradução for concluída, uma versão adicional será criada para o ativo traduzido. (9310)
* Não é possível excluir os usuários administradores no perfil de pasta. (9306)
* O Mapa raiz atualizado da Referência de chave de conteúdo não é definido até que a página seja atualizada. (9302)
* A autenticação da Web não está funcionando no Oxygen. (9296)
* Os links da Web com caracteres codificados não estão funcionando corretamente. (9227)
* O check-out do arquivo não é feito quando aberto no Oxygen. (9217)
* A atualização de arquivos obtidos não está funcionando no logon com autenticação da Web no Oxygen. (9179)
* As guias Tradução e Linha de base ficam visíveis por algum tempo no painel Mapa. (9146)
* Problemas de experiência ou recursos ocorrem ao recarregar o Perfil de pasta. (9103)
* A exclusão do editor de layout de página não o fecha no painel central na exibição Autor. (9087)
* Ocorre um erro de validação no Editor da Web ao remover uma imagem e salvar a nova versão do documento. (8985)
* Não é possível exibir todos os `glossrefs` no painel Glossário (específico do conteúdo). (8886)
* `xref` sem texto não está sendo exibido na saída da publicação baseada em artigo. (8764)
* As referências são interrompidas ao mover imagens ou arquivos multimídia que têm um espaço nos nomes de arquivo. (8624)
* As referências são interrompidas ao escolher `Select All` e mover os arquivos multimídia ou o conteúdo DITA para outra pasta. (8622)
* Os trabalhos de saída com status como &quot;Aguardando&quot; ou &quot;Executando&quot; não são limpos no Painel do Publish.  (8569)
* O recurso de limpeza de saída falhará se um grande número de nós de histórico de saída restantes estiverem presentes. (8568)
* O pacote de complemento DITA impede a detecção de ativos duplicados do DAM. (8417)
* Botão Criar tarefa de revisão ativado para arquivos não DITA. (8401)
* A caixa de diálogo Inserir referências é aberta ao adicionar subjectref a um mapa usando a interface do usuário. (8212)
* Espaço inesperado encontrado em cada elemento `entry` em branco quando o atributo outputclass é adicionado ao elemento `tgroup`. (7532)
* O painel Repositório não exibe ícones de bloqueio de arquivos com check-in ou check-out assim que a ação for concluída. (5817)
* O ícone de bloqueio é exibido na visualização de repositório mesmo quando o arquivo é submetido a check-in pelo editor.  (5756)
* Os sites estão ausentes nas predefinições de AEM na guia Saída. (9567)
* O Editor de XML trava ao tentar editar alguns arquivos DITA. (9537)
* Fazer uma pesquisa no Editor de XML faz com que a página congele. (9452)
* Baixar o mapa com a linha de base inoperante se o conteúdo for movido para outra pasta. (9331)
* O recarregamento falha no Oxygen quando os arquivos já existem no AEM no mesmo local. (9328)
* A posição do realce está incorreta na exibição lado a lado. (9305)
* Após o check-in de um documento do Oxygen para o AEM, o conteúdo em japonês no documento é substituído por pontos de interrogação (???). (9276)
* O upload de arquivos do Oxygen para o AEM falha. (9157)
* A notificação por email não é enviada quando uma tarefa de revisão é reatribuída na Caixa de entrada. (8376)

## Problemas conhecidos

Uma página em branco é exibida intermitentemente ao abrir o editor.
