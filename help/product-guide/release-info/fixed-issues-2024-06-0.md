---
title: Notas de versão | Correção de problemas na versão 2024.06.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2024.06.0 do Adobe Experience Manager Guides as a Cloud Service.
exl-id: 608e5b2c-72af-4498-9b63-935e698231d4
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 1%

---

# Correção de problemas na versão 2024.06.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2024.06.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2024.06.0](whats-new-2024-06-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2024.06.0](upgrade-instructions-2024-06-0.md).

## Criação  

- A operação de copiar e colar de tópicos acima de 15 KB falha com um erro inesperado. (17171)
- A funcionalidade para alterar o estado do documento do painel **Propriedades do Arquivo** não está funcionando corretamente e muda para o estado *Rascunho*. (17088)
- Ao alterar as configurações do editor XML usando um perfil de pasta personalizado, o `ui_config.json` é atualizado com um arquivo incorreto. (17011)
- No painel **Repositório**, a pesquisa **Filtro** não retém o valor do campo **Verificado por** ao reabrir a caixa de diálogo **Filtro avançado**. (16935)
- As imagens vinculadas dos tópicos não aparecem na linha de base após a criação da versão. (16931)
- Painéis de conteúdo reutilizáveis não listam elementos quando as **Preferências do usuário** estão definidas para exibir arquivos por **Nome do arquivo**. (16896)
- Os subelementos no elemento de título da tabela não são renderizados no modo de **Visualização** do Experience Manager Guides. (16691)
- Falha na execução do script postprocess devido à exceção **FileNotFoundException**. (16517)
- Os vídeos do Vimeo não são compatíveis com a funcionalidade de tela cheia no Experience Manager Guides. (15996)
- Colar longas sequências de texto pré-formatadas em elementos `<pre>` ou `<codeblock>` resulta em texto truncado. (15859)
- A exclusão de conteúdo ocorre devido a GUIDs duplicados quando os modelos são instalados por meio de código, mas permanecem não processados. (15858)
- A Experience Manager Guides não adere ao atributo **Função de Processamento** no modo **Visualização**. (15787)
- O Editor exclui intermitentemente texto extra além da área selecionada.  (15708)
- Incapacidade de copiar e colar tabelas grandes de documentos do Word ou HTML no Editor da Web. (15369)
- A função **Copiar** falha em pastas vazias no Experience Manager Guides as a Cloud Service. (15353)
- Falta de APIs ou eventos para capturar a adição de atributo a um elemento ou a inserção de um novo elemento. (15351)
- Incapacidade de adicionar a marca `<data>` dentro da marca `<ol>` no Editor da Web. (15161)
- Quando o Unified Shell está habilitado, a caixa de diálogo **Version Label Management** exibe incorretamente o **Main Content** para versões sem rótulos. (15039)
- Arquivos grandes são carregados lentamente no Editor da Web, com um atraso de alguns segundos. (14958)
- Pressionar a tecla **Enter** em uma célula de tabela dentro do texto não divide o parágrafo conforme esperado. (14251)
- O Guia DITA do Experience Manager não consegue acionar a função **Salvar** após o uso do recurso de recuo automático. (16482)
- Os tópicos de revisão não aparecem na ordem correta. (16319)
- No modo de exibição **Autor**, ocorre um problema de copiar e colar ao usar espaços não separáveis, o que resulta em excesso de texto. (15541)

- No elemento `<othermeta>` em `<topicmeta>`, ao adicionar um `<conref>` a outro mapa DITA, a ID do mapa também é anexada junto com a ID do elemento. (15226)
- O `<conref>` não pode ser atualizado do painel **Atributos** ao fazer alterações. (15209)
- Ao selecionar uma imagem em uma célula de tabela, a célula inteira é selecionada. (15188)

## Publicação


- A vinculação de mapa cruzado não exibe todos os mapas principais nas configurações de contexto de publicação para um link que tem o `peer @scope`. (16700)
- Ao adicionar atributos novos ou remover atributos existentes, os atributos antigos são retidos nas **Predefinições de condição**. (15890)
- O conteúdo da linguagem RTL não é manipulado corretamente na saída de publicação PDF nativo. (15709)
- A versão do primeiro PDF não é criada quando uma saída de PDF nativo é gerada. (10305)
- No PDF nativo, os tópicos DITA aninhados são exibidos incorretamente no índice. (16742)
- As miniaturas geradas no Dynamic Media para arquivos de vídeo não persistem na saída publicada. (15656)
- Falha na geração de saída para Publicação de PDF Nativo em um processador ARM64. (16968)

## Gerenciamento

- A edição de uma linha de base existente e a seleção de uma versão específica aciona erros de aplicação. (14451)

## Tradução

- Os projetos de tradução não conseguem adicionar novos trabalhos de idioma ao Adobe Experience Manager 6.5 SP18 com a versão de outubro de 2023 do Experience Manager Guides. (15398)

## Serviço em nuvem

- A navegação das Ferramentas do Adobe Experience Manager não responde. (17118)
- A fase de Transformação de compilação na implantação do Cloud Service falha com erros da base de código DITA. (14432)

## Relatórios

- A **Lista de Tópicos** imprecisa conta na interface do Experience Manager Guides devido a propriedades sem patch ao copiar ativos DITA afetar os relatórios gerados para um mapa DTIA. (15529)
- Tópicos contendo referências externas com *%20* na URL exibem referências de arquivo corrompidas. (15347)


## Problemas conhecidos

O Adobe identificou os seguintes problemas conhecidos para a versão 2024.06.0:

- A publicação do PDF nativo falha quando o conteúdo do Vimeo é adicionado ao tópico.
- As **propriedades de Tópico** não são exibidas de acordo com o formato selecionado nos campos de metadados de um layout de página.
- Não é possível clicar em `xrefs` na exibição **Assets** quando o Dynamic Media está habilitado.
