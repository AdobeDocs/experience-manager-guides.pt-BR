---
title: Notas de versão | Correção de problemas na versão 2024.10.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2024.10.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 64c5318a064d28a42f3f11d2fe5b7d8548e341d8
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 0%

---

# Correção de problemas na versão 2024.10.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2024.10.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2024.10.0](whats-new-2024-10-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2024.10.0](upgrade-instructions-2024-10-0.md).


## Criação  

- A opção **Localizar** não está funcionando na exibição **Source**. 18610)
- O elemento `<title>` é adicionado automaticamente quando o elemento `<fig>` é inserido como um trecho. (18562)
- A regeneração de tópico falha devido à falha da API de publicação incremental ou de Regeneração de Tópico OOTB. (18452)
- A instância do Experience Manager Guides fica instável e os logs de erro aumentam de tamanho em 30 a 40 GB após acessar a interface do usuário do Assets. (18414)
- Os ícones **Check-out** e **Check-in** aparecem juntos quando `autocheckout` está configurado no xmleditor. (18088)
- O comando copiar e colar de imagens da exibição Autor não funciona na versão 2024.06.0 do Adobe Experience Manager Guides as a Cloud Service.(18062)
- `<conref>` para um tópico referenciado em um mapa DITA não está sendo refletido na visualização no editor. (17794)
- Os mapas DITA grandes são carregados lentamente e demoram para alternar para a exibição **Layout**. (17590)
- A versão DITA exibe incorretamente o nome de usuário na interface do usuário do Assets. 17580)
- Erros de IDs de imagem duplicadas nos tópicos impedem que o usuário salve ou crie um tópico. (17528)
- Ocorrem problemas ao carregar um grande número de arquivos com conjuntos de dados densos para a Experience Manager Guides.(17008)
- Falhas intermitentes ocorrem com a funcionalidade de renderização de PDF no Experience Manager Guides as a Cloud Service. (16966)
- Ao criar um mapa DITA com base em um modelo, o fluxo de trabalho DXML do OOTB causa interrupções no processo e resulta em 503 erros que não podem ser reparados. (16529)
- **Caracteres especiais** gravados com caracteres de escape são removidos do tópico após serem carregados no Experience Manager Guides. (16495)
- A mensagem de erro &quot;Check-out de arquivo&quot; é exibida incorretamente ao editar arquivos que são movidos de outra guia, quando os tokens expiram ou quando o usuário está desconectado. (15223)
- Arquivos grandes não são carregados no Editor da Web e fazem com que o navegador congele. (13227)
- `<Topicref>` adicionado usando `<keyref>` não é exibido no PDF nativo. (1974)
- O caminho do componente `/libs/fmdita/components/versions` está codificado e os usuários não podem sobrepô-lo. (8779)
- Abrir um tópico DITA ou mapa em uma nova guia para edição congela a navegação de seleção na interface do Assets. (4992)
- Baixar um mapa DITA com arquivos de vídeo grandes aciona um erro de falta de memória nos registros e falha na interface do usuário. (18884)
- Ao inserir uma equação MathML contendo o símbolo &quot;&lt;&quot;, um erro **Caractere inválido** é gerado. (18742)
- A geração incorreta de UUID durante o processo de assimilação de conteúdo resulta em referências de submapa corrompidas no mapa assimilado. (18308)
- Em alguns casos, atrasos no processamento de um novo tópico DITA são observados quando criado a partir do editor da Web. (16836)
- A pesquisa de arquivos no **Repositório** dentro do Editor da Web demora muito e, às vezes, não carrega os resultados. (16837)

## Publicação

- A referência cruzada para a chave não está sendo resolvida na saída de PDF nativo. (18087)
- O erro **duplicate_value** ocorre intermitentemente ao republicar um artigo existente no Salesforce. (17932)
- A formatação de estilo e conteúdo nos modelos de clientes muda automaticamente quando o layout inclui campos de metadados, causando a formatação incorreta nos PDF publicados. (17900)
- A validação da conexão do Salesforce falha com o URL do lightning. (17797)
- O PDF referenciado não é ativado no **Painel do Publish em massa** durante a Ativação em massa do conteúdo publicado. (17793)
- A Ativação em massa de conteúdo publicado não está funcionando para mapas localizados. (17638)
- Ao selecionar a opção **Usar metadados adicionados ao topicmeta**, as propriedades de metadados não são propagadas nas propriedades do documento da saída de PDF nativo. (17283)
- A filtragem de condição na saída de PDF nativo não está funcionando como esperado em comparação ao DITA-OT. (17095)
- O índice não respeita as tags `<sub>` ou `<sup>` na saída de PDF nativo. (17028)
- A geração de sites de AEM e a API de publicação incremental não estão funcionando como esperado. (16666)
- A geração de PDF nativo falha com um erro relacionado à obtenção de dependências para Node.js. (14445)
- `<Conref>` não é resolvido no modo `Preview` do Editor da Web e da saída PDF nativa. (17827)
- As referências de conteúdo não serão resolvidas corretamente para a saída de PDF nativo se o arquivo que contém as definições de chave não estiver na mesma pasta que o mapa DITA. (15062)
- Quando um mapa DITA contém níveis de cabeçalho até 7 ou superiores, o cabeçalho de nível 7 é tratado incorretamente como um cabeçalho de nível 1 na saída de PDF nativo. (19698)
- Quando uma parte do conteúdo (texto) é encapsulada dentro de um elemento, os espaços antes e depois do texto não são exibidos nos formatos de Pré-visualização ou Saída. (19308)
- Os fluxos de trabalho de pós-geração acionados manualmente falham devido a uma EXCEÇÃO DE PONTEIRO NULO no fluxo de trabalho, resultando no upload do conteúdo 11 vezes. (18880)
- O **Painel de Publish em massa** mostra em branco para mapas que ainda estão no processo de tradução. (19352)


## Gerenciamento

- O caminho para a funcionalidade de sobreposição é codificado para o arquivo de idioma coreano e não está selecionado corretamente. (17089)
- As alterações/personalização feitas na caixa de diálogo **Salvar versão** não refletem ao usar a Estrutura de Extensão de Guias. (17828)
- A conversão do InDesign em DITA tem um caminho de configuração codificado, de modo que os arquivos de configuração personalizados não são escolhidos. (16891)
- Referências/ativos completos não são baixados quando um mapa DITA contendo grandes dependências/referências é baixado usando a Linha de base. (1909)


### Revisar

- Se a contagem de usuários exceder 25, a busca da lista de usuários ao criar uma tarefa de revisão falhará. (17329)
- Se um tópico de tarefa contiver a tag `<cmd>` em uma ou mais etapas, o painel de revisão exibirá o atributo `importance` como um prefixo em todas as etapas que contêm a tag. (1969)

## Tradução

- As referências de ativos traduzidos não são atualizadas. 18086)
- As referências não são filtradas corretamente como Diretas ou Indiretas ao serem traduzidas para vários idiomas. (17891)
- Não é possível criar projetos XLIFF com tradução humana. (16964)
- Adicionar um tópico atualizado em um projeto de tradução ativo resulta em um tópico duplicado e o processo falha. (7688)
- Os projetos de tradução criados ao selecionar a opção **Criar estrutura somente** não têm UUIDs atribuídos. (18980)
- Ao selecionar um projeto de tradução com o **Status da tradução** como **Em andamento**, uma página incorreta será aberta. (13248)
- O título com `<conref>` não é resolvido nos painéis Linha de Base e Tradução do Editor da Web. (16961)

## Problemas conhecidos

- Abrir uma predefinição do AEM Sites (não herdada) marca o tópico como sujo.
- O painel selecionado não está sendo retido na atualização do navegador da guia Saída.
- Não é possível arrastar e soltar o tópico entre dois topicrefs na exibição **Autor**.
- A filtragem de condição aplicada na predefinição não está sendo aplicada via **Baixar como PDF**.
- A geração de um único tópico a partir do painel de mapa gera todos os tópicos selecionados na predefinição do AEM Sites (não herdados).
- A referência do tópico aparece quebrada na interface do usuário quando inserida na barra de ferramentas superior do mapa DITA.
- A geração de PDF nativo falha para um mapa DITA se houver referências ausentes.
- A publicação de um único tópico do site AEM com condições falha no ambiente habilitado para microsserviços.
- Depois que o estado do documento de um tópico for atualizado para **Concluído**, o ícone **Iniciar uma Nova Versão** só estará disponível no modo **Visualizar** do tópico.
