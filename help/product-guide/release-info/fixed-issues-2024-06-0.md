---
title: Notas de versão | Correção de problemas no Adobe Experience Manager Guides, versão 2024.06.0
description: Saiba mais sobre as correções de erros na versão 2024.06.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: dff625a841ea9fc758de83b1d830ddffa15646cd
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 1%

---


# Correção de problemas na versão 2024.06.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2024.06.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão 2024.06.0](whats-new-2024-06-0.md).

Saiba mais sobre [instruções de atualização da versão 2024.06.0](upgrade-instructions-2024-06-0.md).

## Criação  

- A operação de copiar e colar de tópicos acima de 15 KB falha com um erro inesperado. (17171)
- A funcionalidade para alterar o estado do documento de  **Propriedades do arquivo** O painel não está funcionando corretamente e o muda para a *Rascunho* estado. (17088)
- Ao alterar as configurações do editor XML usando um perfil de pasta personalizado, `ui_config.json` é atualizado com um arquivo incorreto. (17011)
- No **Repositório** painel, o **Filtro** a pesquisa não retém o valor de **Retirado por** ao reabrir a variável **Filtro avançado** caixa de diálogo. (16935)
- As imagens vinculadas dos tópicos não aparecem na linha de base após a criação da versão. (16931)
- Os painéis de conteúdo reutilizáveis não listam elementos quando a variável **Preferências do usuário** estão configurados para exibir arquivos por **Nome do arquivo**. (16896)
- Os subelementos no elemento de título da tabela não são renderizados na variável **Visualizar** modo de Guias de Experience Manager. (16691)
- A execução do script postprocess falha devido a **ArquivoExceçãoNãoEncontrada** exceção. (16517)
- Os vídeos do Vimeo não são compatíveis com a funcionalidade de tela cheia nos Guias do Experience Manager. (15996)
- Colagem de longas sequências de texto pré-formatadas no `<pre>` ou `<codeblock>` Os elementos do levam a um texto truncado. (15859)
- A exclusão de conteúdo ocorre devido a GUIDs duplicados quando os modelos são instalados por meio de código, mas permanecem não processados. (15858)
- Os Guias do Experience Manager não aderem à **Função de processamento** atributo em **Visualizar** modo. (15787)
- O Editor exclui intermitentemente texto extra além da área selecionada.  (15708)
- Incapacidade de copiar e colar tabelas grandes de documentos do Word ou HTML no Editor da Web. (15369)
- A variável **Copiar** falha para pastas vazias no Experience Manager Guides as a Cloud Service. (15353)
- Falta de APIs ou eventos para capturar a adição de atributo a um elemento ou a inserção de um novo elemento. (15351)
- Incapacidade de adicionar `<data>` tag no `<ol>` no Editor da Web. (15161)
- Quando o Unified Shell estiver ativado, a variável **Gerenciamento de etiqueta de versão** é exibida incorretamente **Conteúdo principal** para versões sem rótulos. (15039)
- Arquivos grandes são carregados lentamente no Editor da Web, com um atraso de alguns segundos. (14958)
- Pressionando o **Enter** A tecla em uma célula de tabela no texto não divide o parágrafo conforme esperado. (14251)
- O Guia DITA do Experience Manager não aciona o **Salvar** após o uso do recurso de recuo automático. (16482)
- Os tópicos de revisão não aparecem na ordem correta. (16319)
- No **Autor** Na visualização, um problema do tipo copiar e colar ocorre ao usar espaços não separáveis e resulta em excesso de texto. (15541)

- Entrada `<othermeta>` elemento dentro `<topicmeta>`, sobre a adição de um `<conref>`Em outro mapa DITA, a ID do mapa também é anexada junto com a ID do elemento. (15226)
- A variável `<conref>` não pode ser atualizado do **Atributos** ao fazer alterações. (15209)
- Ao selecionar uma imagem em uma célula de tabela, a célula inteira é selecionada. (15188)

## Publicação


- A vinculação entre mapas falha ao exibir todos os mapas principais nas configurações de contexto de publicação para um link que tem a variável `peer @scope`. (16700)
- Ao adicionar novos atributos ou remover atributos existentes, os atributos antigos são mantidos no **Predefinições de condição**. (15890)
- O conteúdo da linguagem RTL não é manipulado corretamente na saída de publicação PDF nativo. (15709)
- A versão do primeiro PDF não é criada quando uma saída de PDF nativo é gerada. (10305)
- No PDF nativo, os tópicos DITA aninhados são exibidos incorretamente no índice. (16742)
- As miniaturas geradas no Dynamic Media para arquivos de vídeo não persistem na saída publicada. (15656)
- Falha na geração de saída para Publicação de PDF Nativo em um processador ARM64. (16968)

## Gerenciamento

- A edição de uma linha de base existente e a seleção de uma versão específica aciona erros de aplicação. (14451)

## Tradução

- Os projetos de tradução não conseguem adicionar novos trabalhos de idioma ao Adobe Experience Manager 6.5 SP18 com a versão de outubro de 2023 dos Guias do Experience Manager. (15398)

## Serviço em nuvem

- A navegação das Ferramentas do Adobe Experience Manager não responde. (17118)
- A fase de Transformação de compilação na implantação do Cloud Service falha com erros da base de código DITA. (14432)

## Relatórios

- A imprecisa **Lista de tópicos** contagens na interface do usuário dos Guias de Experience Manager devido a propriedades sem patch ao copiar ativos DITA afetam os relatórios gerados para um mapa DTIA. (15529)
- Tópicos contendo referências externas com *%20* na URL, exiba referências de arquivo corrompidas. (15347)


## Problemas conhecidos

O Adobe identificou os seguintes problemas conhecidos para a versão 2024.06.0:

- A publicação do PDF nativo falha quando o conteúdo do Vimeo é adicionado ao tópico.
- A variável **Propriedades do tópico** não são exibidos conforme o formato selecionado nos campos de metadados de um layout de página.
- `xrefs` não são clicáveis no **Assets** exibir quando o Dynamic Media está ativado.
