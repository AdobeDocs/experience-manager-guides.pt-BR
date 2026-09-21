---
title: Notas de versão | Correção de problemas na versão Adobe Experience Manager Guides 5.2.0 Service Pack 1
description: Saiba mais sobre as correções de erros na versão 5.2.0 Service Pack 1 do Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 429d2abf0aad8722ac30c08c9c9d134be0759ff4
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 0%
---
# Correção de problemas na versão 5.2.0 do Service Pack 1 (setembro de 2026)

Este artigo aborda os bugs corrigidos em várias áreas da versão 5.2.0 Service Pack 1 do Adobe Experience Manager Guides.

Saiba mais sobre as [instruções de atualização para o 5.2.0 Service Pack 1 versão](upgrade-instructions-5-2-0-sp1.md).

## Criação

- Em telas de baixa resolução, a caixa de diálogo Inserir Palavra-chave não é exibida ao inserir uma palavra-chave na barra de ferramentas, enquanto abre conforme esperado ao usar a opção **Mais**. (GUIDES-48304)
- Inserir uma referência cruzada usando a opção **Link da Web** adiciona um link `scope=local` e modifica o valor `href`, em vez de inserir um link `scope=external`, conforme esperado. (GUIDES-48457)
- Salvar um mapa de referência resulta em uma referência quebrada, em vez de resolver para o mapa correto quando um autor move o mapa referenciado enquanto outro autor adiciona simultaneamente uma referência a ele em um mapa não salvo. (GUIDES-47467)
- Os termos alfanuméricos adicionados ao dicionário ainda são sinalizados pelo verificador ortográfico do AEM em vez de serem ignorados. (GUIDES-48587)
- Ao alternar o foco entre os campos **Largura** e **Altura** na caixa de diálogo de propriedades de imagem usando tamanhos baseados em unidade, como `in`, `mm` ou `px`, os valores continuam aumentando de forma incremental em vez de permanecerem estáveis. (GUIDES-45929)

## Editor 2.0

- Espaço em branco inserido imediatamente antes da exclusão de uma marca embutida em uma célula de tabela `<entry>`. (GUIDES-49144)
- Inserir um elemento na posição `tgroup` exibe um aviso **#text não é permitido aqui**, impedindo que uma tabela normal seja inserida nessa posição. (GUIDES-47446)
- Copiar uma tabela de uma planilha do Excel e colá-la no Novo editor coloca todo o conteúdo da célula copiada em uma única célula de tabela, em vez de distribuí-la pelas células correspondentes. (GUIDES-47435)
- Um botão **Exportar como PDF** personalizado configurado por meio de `editor_toolbar.json` é renderizado e permanece clicável no modo de Visualização, mas não executa nenhuma ação quando clicado. (GUIDES-47402)
- A abertura de determinados tópicos contendo tabelas adiciona uma tag `<foreign>` inesperada com duas novas colunas, mesmo quando não foram feitas alterações no tópico. (GUIDES-46748)
- Quando uma equação do MathML é inserida como `conref`, ela não é renderizada corretamente. (GUIDES-46601)
- Os elementos MathML e SVG não renderizam seu conjunto completo de atributos, causando a quebra das classes CSS personalizadas e dos atributos condicionais aplicados a esses elementos. (GUIDES-46371)
- O atributo **Scale** não se aplica a imagens na exibição Autor. (GUIDES-45996)
- Aplicar um atributo `scale` a uma tabela não renderiza a tabela no tamanho configurado nos modos Autor e Visualização. (GUIDES-45984)
- Colar imagens copiadas de fontes externas, como Tinta ou a Ferramenta de recorte, não insere a imagem no tópico. (GUIDES-45983)
- Copiar e colar `<keywords>` dentro de `<topicmeta>` dentro de `<keydef>` ou `<topicref>` faz com que as palavras-chave sejam inseridas dentro de marcas estrangeiras indesejadas. (GUIDES-45800)
- Na exibição &#39;Marca&#39; de uma tabela, pressionar a tecla de seta para cima quando o cursor estiver posicionado na célula logo abaixo de uma marca de entrada recolhida salta sobre a marca recolhida e move o cursor para o início do documento. (GUIDES-45408)
- A execução de qualquer operação na barra de ferramentas contextual da tabela fecha a barra de ferramentas inesperadamente, interrompendo as operações de tabela subsequentes. (GUIDES-45405)
- A opção **Editar MathML** é exibida incorretamente no modo somente leitura ou quando outro usuário faz check-out de um arquivo, permitindo que os usuários atualizem o conteúdo do MathML mesmo que o arquivo não seja editável. (GUIDES-45172)
- Depois de usar **Inserir depois de** ou **Inserir antes de** no modo de exibição de Estrutura de Tópicos ou na navegação estrutural, o cursor se move para uma posição arbitrária em vez de dentro da marca recém-adicionada. (GUIDES-45147)
- Ao executar uma operação de arrastar e soltar com a visualização de tag ativada, a seleção do conteúdo juntamente com as tags XML ou DITA parciais deixa para trás tags órfãs indesejadas, resultando em conteúdo ou visualização incorretos. (GUIDES-28191)

## Gerenciamento de ativos

- O utilitário de limpeza de versão falha ao ser concluído em vários cenários, incluindo determinados tipos de arquivos, ativos com metadados ausentes e relatórios grandes, em vez de concluir a limpeza e gerar um relatório preciso. (GUIDES-43453)

## Publicação

- Nomes de arquivo em idioma diferente do inglês nos nomes de página gerados são substituídos por hifens, dificultando a identificação do tópico ou arquivo ao qual está associado, ao publicar a saída do AEM Sites usando o mapeamento de componente herdado. (GUIDES-48387)
- Os JARs `jackson-databind` vulneráveis (versão 2.9.8) agrupados com o AEM Guides no pacote DITA-OT são identificados. (GUIDES-43081)

## Revisar

- Abrir o modo de exibição **lado a lado** no painel Comentários exibe a cópia de trabalho junto com a versão comentada, mas os painéis não rolam em sincronia horizontalmente e clicar em um comentário não move o cursor para o texto correspondente. (GUIDES-44083)

## Platform

- Usar `scope="external"` para uma referência ao conteúdo DAM em um tópico ou mapa faz com que o caminho relativo do ativo seja substituído por um GUID. (GUIDES-35605)
- Para conteúdo criado antes da migração UUID, o download de um mapa com as opções **Manter hierarquia de arquivos** e **Usar nome de arquivo real** selecionadas converte incorretamente os valores `href` de elementos `topicref`, `xref` e `conref` com `scope="external"` em nomes de arquivo baseados em GUID, em vez de reter os caminhos de arquivo relativos originais. Como resultado, as referências externas são quebradas. (GUIDES-46526)
- Ao fazer upload de ativos por meio da interface do Assets, o status do upload não é exibido. (GUIDES-7207)

## Problemas conhecidos

- Ao executar uma operação de revisão dentro de um bloco de código, um aviso **Operação não permitida** é exibido na primeira tentativa, mas a operação é bem-sucedida quando repetida. (GUIDES-56749)
- Quando uma tarefa de revisão é criada para conteúdo que contém um `code block`, a formatação tachada não se aplica corretamente após a importação e o conteúdo destacado está ausente na exibição de comparação lado a lado. (GUIDES-56811)
- Em alguns casos, a guia **Lista de tópicos** do painel Relatórios não exibe resultados, mesmo quando o mapa contém vários tópicos. (GUIDES-56893) <br> **Solução alternativa:** reindexe o conteúdo afetado para recompilar as relações pai-mapa. Os tópicos são exibidos na guia Topic list, conforme esperado.
- Selecionar um elemento de instrução de processamento na exibição de Estrutura de Tópicos realça a tag principal inteira em vez do elemento selecionado. (GUIDES-48318)
- Ao executar operações de exclusão, algumas pequenas inconsistências no movimento e na navegação do cursor podem ocorrer em mapas de imagem, elementos estruturados, tags de formatação em linha e blocos não mescláveis, ocasionalmente resultando em um comportamento inesperado de cursor ou exclusão. (GUIDES-46756)
- Uma equação de MathML encapsulada dentro de um bloco `foreign` e `equation` resulta em espaçamento indesejado, e digitar dentro da equação causa problemas mesmo após ajustar o recuo. (GUIDES-46606)
- Não é possível colocar um cursor dentro de um `topicref` dentro de um `reltable` quando a opção **Mostrar marcas** está habilitada e a opção **Exibir atributos** está desabilitada nas configurações do Editor. (GUIDES-46565)
- Pressionar a tecla backspace no início de um parágrafo imediatamente após o conteúdo somente leitura (como um parágrafo conref) pode excluir ou mesclar inesperadamente o parágrafo editável, resultando na exclusão inesperada do parágrafo editável. (GUIDES-45049)
- Quando uma tag integrada é renomeada usando a opção Renomear elemento, a navegação estrutural não é atualizada imediatamente e reflete a alteração somente depois que o cursor é movido para a tag ou o modo de exibição é alterado. (GUIDES-44993)<br>**Solução alternativa:** atualize o navegador após renomear a marca embutida para atualizar a navegação estrutural.
- Quando os indicadores de condição são aplicados a elementos como body div, os indicadores sobrecarregam as tags adjacentes na Exibição de tags completas, resultando na renderização visual incorreta. (GUIDES-44971)

