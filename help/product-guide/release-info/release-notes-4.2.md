---
title: Notas de versão | Versão do Adobe Experience Manager Guides 4.2
description: Saiba mais sobre as correções de erros e como atualizar para as versões 4.2 do Adobe Experience Manager Guides
exl-id: 8a7fef77-63af-462f-89c5-054ab31e079b
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 1%

---

# Versão 4.2 do Adobe Experience Manager Guides (fevereiro de 2023)

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão 4.2 do Adobe Experience Manager Guides (mais tarde chamados de *Guias do AEM*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão 4.2 dos Guias do Adobe Experience Manager](whats-new-4.2-release.md).

## Atualização para a versão 4.2 dos Guias do AEM

Você pode facilmente atualizar sua versão atual dos Guias do AEM para a versão 4.2. Antes de prosseguir com a atualização para a versão 4.2 dos Guias do AEM, você deve considerar os seguintes pontos:
* Se você estiver usando a versão 4.0, 4.1 ou 4.1.x, é possível atualizar diretamente para a versão 4.2.
* Se você estiver usando a versão 3.8.5, será necessário atualizar para a versão 4.0 antes de atualizar para a versão 4.2.
* Se você estiver em uma versão anterior à 3.8.5, consulte a *Atualizar guias do AEM* no guia de instalação específico do produto.

>[!NOTE]
>
>Você deve instalar o service pack AEM antes de atualizar a versão dos Guias AEM.

Para obter detalhes, consulte [Instruções de atualização](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software suportados pela versão 4.2 dos Guias AEM.

### Adobe Experience Manager

**Não UUID**
Versão 6.5 Service Pack 15, 14, 13 ou 12

**UUID**
Versão 6.5 Service Pack 15, 14, 13 ou 12

Para obter mais detalhes, consulte *Requisitos técnicos* no guia Instalar e configurar o Adobe Experience Manager Guides.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2 (Não UUID) | 2022 ou superior | 2020.2 ou superior* | 2022 ou superior | 2020.3 ou superior |
| 4.2 (UUID) | 2022 ou superior | 2020.2 ou superior* | 2022 ou superior | 2020.4 ou superior |
| | | | |

*A linha de base e as condições criadas no AEM são compatíveis com as versões do FMPS a partir de 2020.2.

### Conector de oxigênio

| Versão | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2 (Não UUID) | 2.1-regular-4 | 2.1-regular-4 | 1,6 | 1,6 |
| 4.2 (UUID) | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |   |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Criação  

* O painel esquerdo é interrompido ao adicionar uma guia. (11126)
* As alterações no html do Editor da Web causam problemas com `<dl>` e `<dlentry>`. (11024)
* Alguns atributos não estão sendo tratados como condicionais e estão causando problemas. (10895)
* Três níveis ou mais aninhados `<indexterm>` não estão aninhados na exportação de PDF nativa. (10799)
* O conteúdo desaparece no corpo de uma tarefa ao alternar da visualização Autor para Fonte. (10735)
* Comentários de revisão são colocados fora do lugar em uma tarefa de revisão. (10625)
* `<conref>` a nota em uma tag para não é exibida no modo de visualização. (10559)
* Acertar o espaço traseiro no final de um item de lista remove a lista inteira. (10540)
* A tela é exibida em branco no Chrome v106 ao arrastar e soltar qualquer elemento da interface do usuário ( por exemplo, no painel Condições ). (10524)
* O botão Recuo automático está ausente na barra de ferramentas no **Origem** exibição. (10448)
* O primeiro caractere de um item de lista é perdido às vezes quando a lista está sendo criada no editor.(10447)
* **Desfazer** ou **Refazer** O não está funcionando corretamente em alguns arquivos. (10373)
* Os metadados personalizados não são mantidos na ação de copiar e colar. (10367)
* Ocorre um erro ao fazer uma cópia (ctrl+c) e colar (ctrl+v) de conteúdo. (10304)
* O painel Estrutura de Tópicos não exibe o conteúdo quando alternado do modo Autor para o modo Origem. (10296)
* O Submapa não é criado quando se refere a um mapa principal em Modelos DITA. (10231)
* Problemas de navegação ocorrem no Editor da Web após a atualização 4.0. (10159)
* A opção Desfazer no Editor de XML leva o usuário para a parte superior da página. (10091)
* As propriedades do nó são removidas após a operação de copiar e colar de um ativo. (10053)
* Os arquivos SVG adicionados aos tópicos DITA não são exibidos no modo de visualização do editor. (10010)
* Os resultados da pesquisa para localizar e substituir no Editor da Web não são legíveis no modo Escuro. (9978)
* Não existe carregador ao criar um mapa a partir do modelo de mapa. (9891)
* O Conref no modelo de tópico não funciona e a ID de hash copiada não é atualizada na cópia de conteúdo. (9890)
* Nenhuma opção é exibida para procurar os tópicos ou mapear modelo dentro das subpastas do tópico ou da pasta do mapa. (9889)
* Não há opção para criar um novo modelo nas subpastas de tópicos ou mapas. (9888)
* O Editor de XML não atualiza as imagens nos tópicos. (9500)
* O mimeType é codificado para criação e atualização de ativos DITA. (8979)
* Um hífen normal é inserido ao selecionar Hífen não-separável no **Inserir caractere especial** diálogo. (8919)
* O nome do criador de versão no Histórico de versão é &quot;fmdita-serviceuser&quot; para os arquivos carregados pela interface do usuário do Assets. (8910)
* A opção Editar não funciona para imagens ao trabalhar na exibição Coluna da interface do usuário do Assets. (8758)
* O tópico DITA não é atualizado automaticamente com alterações feitas em **Propriedades** página. (8745)
* Ao mover elementos dentro do tópico no Editor da Web, as IDs atribuídas nos elementos são substituídas pelas IDs atribuídas automaticamente. (7895)

### Gerenciamento

* Copiar um ativo de mapa DITA (da interface do usuário do Assets ) causa linhas de base incorretas no ativo copiado. (11218)
* A mensagem de aviso não é exibida no upload de um arquivo maior do que o limite permitido no AEM (2 GB por padrão). (10817)
* Editor da Web - Linha de base | O comportamento da coluna Mais recente é diferente no novo painel da linha de base no Editor da Web. (10808)
* Tradução | A tarefa de tradução não é iniciada devido a /libs/fmdita/i18n/ja.json inválido. (10543)
* Tradução | Ocorre um erro em um projeto de tradução de escopo criado a partir do painel de tradução (Tradução humana). (10526)
* Tradução | O pós-processamento está bloqueado para toda a pasta de idioma cujos ativos estão presentes em um projeto de tradução ativo. (10332)
* Tradução | Os metadados e as tags não estão sendo propagados para as cópias traduzidas. (4696)
* Vários pop-ups são exibidos para qualquer ativo se a versão for alterada e salva no editor de linha de base. (10399)
* O vazamento da sessão ocorre em com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210). (10279)
* O arquivo de vídeo está ausente na linha de base se a pasta pai contiver espaço no nome. (10031)

### Publicação

* A regeneração de tópico não está funcionando para alguns cenários. (10635)
* A publicação de PDF falha ao gerar a saída para uma predefinição duplicada (de uma predefinição existente). (10584)
* O botão Visualizar log não funciona caso a geração de PDF falhe para uma predefinição. (10576)
* O Publishlistener não exibe os dados solicitados em logs de informações e também contém alguns logs de lixo eletrônico.(10567)
* PDF nativo | Falha na geração de PDF com uma exceção de Null Pointer. (10950)
* PDF nativo | conkeyref não está sendo resolvido na saída gerada. (10564)
* PDF nativo | Problemas ocorrem com os metadados de um mapa que precisa ser referido na saída do PDF.(10556)
* PDF nativo | Problemas ao girar o cabeçalho da tabela. (10555)
* PDF nativo | Ocorrem problemas ao remover tópicos com função de processamento=&#39;resource-only&#39;. (10554)
* PDF nativo | Teclas vazias são exibidas na saída do PDF. (10553)
* PDF nativo | Aninhado `<indexterm>` não estão aninhados na exportação de PDF nativa. (10521)
* PDF nativo | O PDF nativo usa o estilo em linha em vez do nome da classe para as tags geradas. (10498)
* PDF nativo | Tópicos aninhados nos apêndices são todos transformados em h1 no HTML temporário.(10454)
* PDF nativo | Não é possível ocultar tópicos do assunto principal do sumário. (10355)
* PDF nativo | Atributo de quadro de tabela não propagado para o HTML temporário (como classe). (10353)
* PDF nativo | Arquivos de HTML temporários adicionam as classes colsep e rowsep a <td> e <th> mesmo que o valor seja 0 no DITA de origem. (10352)
* PDF nativo | Reiniciar os números de página no layout do capítulo inicia aleatoriamente a numeração a partir do final do capítulo anterior. (10154)
* PDF nativo | As referências principais de keydefs com imagem ou links externos não estão sendo resolvidas. (10063)
* PDF nativo | O apêndice está sendo exibido como um capítulo no PDF gerado. (9829)
* A guia Modelo no editor xml não está sendo exibida para os administradores de Perfil de pasta. (10266)
* Falha na publicação da linha de base para o PDF gerado usando o FrameMaker Publishing Server 2020. (10551)
* Ocorre um erro de aplicativo ao clicar no botão Editar após marcar todas as predefinições por meio da caixa de seleção Predefinições de saída na janela pop-up Geração rápida. (10388)
* Se a guia Saída no Editor da Web estiver tendo mais predefinições, a seção Predefinições não será rolável verticalmente e não exibirá todas as predefinições disponíveis. (9787)
* Não é possível excluir predefinições do Fluxo de trabalho de saída durante a publicação pelo Editor. (9100)
* O link par é renderizado como texto normal em vez de um link na página gerada. (7774)

## Problema conhecido

o Adobe identificou o seguinte problema conhecido para a versão AEM Guides 4.2:

* Os usuários podem executar operações de revisão mesmo após a conclusão da tarefa de revisão.
