---
title: Notas de versão | Correção de problemas na versão 2026.09.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2026.09.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 2123962f8c168928c9b0a1ee1331e5cfd86db319
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 0%

---

# Correção de problemas na versão 2026.09.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2026.09.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2026.09.0](./whats-new-2026-09-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.09.0](./upgrade-instructions-2026-09-0.md).

## Editor 2.0

- Copiar uma tabela do modo Autor e colá-la no modo Autor remove atributos como `colwidth` e quaisquer outros atributos definidos em `colspec`, causando a perda das configurações de largura da coluna. (GUIDES-52916)
- Espaço em branco inserido imediatamente antes da exclusão de uma marca embutida em uma célula de tabela `<entry>`. (GUIDES-49144)

## Criação

Esta seção aborda os bugs corrigidos na criação que são comuns ao Editor 1.0 e ao Editor 2.0.

- Em telas de baixa resolução, a caixa de diálogo Inserir Palavra-chave não é exibida ao inserir uma palavra-chave na barra de ferramentas, enquanto abre conforme esperado ao usar a opção **Mais**. (GUIDES-48304)
- Salvar um tópico quando a validação do Schematron estiver configurada com um arquivo de regras vazio mostra uma mensagem de erro imprecisa e genérica. (GUIDES-48106)
- As regras de esquema que usam um contexto de nó de texto não acionam a validação. (GUIDES-14500)
- Inserir uma referência cruzada usando a opção **Link da Web** adiciona um link `scope=local` e modifica o valor `href`, em vez de inserir um `scope=external` conforme esperado. (GUIDES-48457)
- Salvar um mapa de referência resulta em uma referência quebrada, em vez de resolver para o mapa correto quando um autor move o mapa referenciado enquanto outro autor adiciona simultaneamente uma referência a ele em um mapa não salvo. (GUIDES-47467)

## Gerenciamento de ativos

- A API de status do ativo não retorna o status correto para ativos cujo caminho contém uma vírgula. (GUIDES-49065)
- O filtro do elemento DITA no Painel de pesquisa do administrador do Assets não aplica o valor inserido, portanto, os resultados da pesquisa não são filtrados. (GUIDES-48450)
- O utilitário de limpeza de versão falha ao ser concluído em vários cenários, incluindo determinados tipos de arquivos, ativos com metadados ausentes e relatórios grandes, em vez de concluir a limpeza e gerar um relatório preciso. (GUIDES-43453)
- Renomear um ativo com um nome de arquivo baseado em GUID para um GUID diferente usando a operação Mover na interface do usuário do Assets substitui o GUID exclusivo original do ativo pelo novo GUID. (GUIDES-43006)

## Publicação

- Ao gerar a saída do AEM Sites (com mapeamento de componente composto) com uma linha de base direcionada a uma versão mais antiga, o conteúdo da página mostra corretamente essa versão mais antiga, mas os metadados da página mostram a versão atual. (GUIDES-49325)
- Quando as páginas são replicadas usando a ativação em massa, as propriedades de rastreamento de replicação são definidas somente na página raiz e não nas páginas secundárias, dificultando a determinação do conteúdo alterado desde a última replicação. (GUIDES-37871)
- Quando o campo **Rótulo** da caixa de diálogo Criar/Editar Linha de Base recebe foco pela primeira vez, colar ou digitar o primeiro caractere não filtra as sugestões de preenchimento automático corretamente, e o campo exibe todas as sugestões em vez dos resultados filtrados.(GUIDES-50143)
- A filtragem de ramificação gera páginas extras para tópicos indesejados usados como `keydef` (que são marcados `resource-only ="true"` por DITA-OT). (GUIDES-19701)
- A coleção de mapas habilita a opção **Publicar** para predefinições que ainda não foram geradas. (GUIDES-50510)
- A seção Histórico de publicação não exibe o texto do espaço reservado quando uma coleção de mapas recém-criada não tem registros de publicação. (GUIDES-50366)
- Aplicar um perfil de cores ICC em uma predefinição nativa do PDF causa falha na geração de saída e as cores CMYK não são renderizadas corretamente, mesmo quando um caminho de perfil direto é usado. (GUIDES-47137)
- A configuração de sangria definida em uma predefinição nativa do PDF não é refletida na saída gerada. (GUIDES-47034)
- O campo **Texto antes da quebra** para continuação de tabela renderiza apenas a cadeia de caracteres localizada e não substitui o espaço reservado para número de página. (GUIDES-32872)
- O navegador de perfis ICC exibe incorretamente os arquivos DITA em vez de mostrar apenas os arquivos ICC. (GUIDES-25017)
- Comentários de rascunho não estão sendo renderizados na saída nativa do PDF. (GUIDES-47044)
- Um comentário de rascunho colocado dentro de um elemento `title` aparece inesperadamente na saída publicada. (GUIDES-10686)
- No painel de Mapa, selecionar uma predefinição diferente aciona uma chamada para buscar links de colegas, resultando em processamento adicional. (GUIDES-53703)

## Tradução

- Iniciar uma tradução usando um projeto XLIFF cria um projeto vazio que nunca é movido para um estado em andamento. (GUIDES-51759)
- Mover o conteúdo de uma pasta de idioma para outra usando a operação de movimentação de ativos impede que os autores selecionem esse conteúdo para tradução no painel Tradução. (GUIDES-49386)
- Enviar ativos para tradução usando a opção **Adicionar ao projeto de tradução existente** enquanto outra solicitação de tradução (uma nova criação de projeto ou uma solicitação *Adicionar à existente*) para o mesmo projeto ainda está processando resultados em um conflito. (GUIDES-49354)

## Linha de base

- A seleção de linha de base salva de uma predefinição é exibida incorretamente como *Nenhuma Linha de Base* após a exclusão da linha de base ou enquanto uma linha de base dinâmica ainda estiver sendo criada. (GUIDES-52690)

## Revisar

- Abrir o painel Revisão ou aplicar um filtro de projeto leva algum tempo para carregar a lista de tarefas. (GUIDES-48893)

## Relatórios

- Gerar o relatório Links quebrados para um mapa com um grande número de tópicos faz com que a interface do relatório permaneça presa na mensagem **Buscando detalhes para links quebrados** indefinidamente, tornando o navegador sem resposta e eventualmente causando uma falha. (GUIDES-37845)

## Conteúdo de aprendizado

- Quando um novo tópico de aprendizado é criado usando uma HTML ou um modelo de aprendizado com um cabeçalho personalizado, o título do tópico não é exibido no cabeçalho personalizado. (GUIDES-52343)
- A porcentagem de precisão calculada de um questionário do curso difere levemente do valor esperado. (GUIDES-52346)
- Em um curso, ao tentar um questionário, as marcas pontuadas diferem levemente da pontuação calculada esperada. (GUIDES-52345)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2026.09.0:

- Alterar o estado do documento de um tópico já bloqueado atualiza o documento inteiro. (GUIDES-53905)
- Ao usar o recurso Visualizar usando linha de base, as solicitações de visualização atingem o tempo limite para mapas grandes (mais de 10.000 tópicos) ou mapas com um alto número de `keydefs` (por exemplo, 100 tópicos `keydefs` e 3.500 tópicos). (GUIDES-54147)
- Para servidores de BD, quando um mapa contendo um `keydef` sem um `href` é visualizado com uma opção de Visualização usando linha de base habilitada, o `keydef` não resolve. (GUIDES-53878)
- As regiões de ponto de acesso configuradas em um ativo de mapa de imagem não são interativas no modo de Visualização, impedindo que os autores validem links de pontos de acesso antes da publicação. (GUIDES-53398)<br>**Solução alternativa**: insira a imagem que você deseja converter em um mapa de imagem, selecione **Editar mapa de imagem** no menu de contexto e configure os links de pontos de acesso.
- Quando você move um mapa com uma linha de base existente para uma pasta diferente enquanto o mapa está aberto, a opção **Visualizar usando linha de base** permanece selecionada no modo de Visualização, mas a linha de base não aparece mais na lista suspensa. (GUIDES-54284)<br>**Solução alternativa**: você pode fechar e reabrir o mapa para resolver o problema.
- Em um ambiente do AEM Cloud Service recém-configurado (AEM as a Cloud Service SDK), tentar criar um mapa ou arquivo de tópico resulta em um erro *Falha ao criar arquivo* ou *Erro ao recuperar a regra DTD*. (GUIDES-53904)<br>**Solução alternativa**: você pode reiniciar o ambiente do AEM Cloud Service.
- Quando dois autores trabalham simultaneamente no mesmo tópico, bloquear um tópico que foi aberto por algum tempo por um autor não atualiza as propriedades de metadados, como número da versão, rótulos, estado do documento, tags e outros, mesmo depois de alterados pelo outro autor, fazendo com que valores desatualizados continuem sendo exibidos. (GUIDES-54810)<br>**Solução alternativa**: feche e reabra o tópico para atualizar os metadados e exibir os valores mais recentes.