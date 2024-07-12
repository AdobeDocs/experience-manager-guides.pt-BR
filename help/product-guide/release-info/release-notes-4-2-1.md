---
title: Notas de versão | Instruções de atualização e problemas corrigidos na versão 4.2.1 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros e como atualizar para as versões 4.2.1 do Adobe Experience Manager Guides
exl-id: a75ec83f-564b-4243-b5c5-341049521adb
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Versão 4.2.1 do Adobe Experience Manager Guides (maio de 2023)

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão 4.2.1 do Adobe Experience Manager Guides (mais tarde chamada de *AEM Guides*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 4.2.1 do Adobe Experience Manager Guides](whats-new-4-2-1-release.md).

## Atualização para a versão 4.2.1 do AEM Guides


É possível atualizar facilmente sua versão atual do AEM Guides para a versão 4.2.1 Antes de continuar com a atualização para a versão 4.2.1 do AEM Guides, você deve considerar os seguintes pontos:
Você pode atualizar sua versão atual do AEM Guides para a versão 4.2.1
* Se você estiver usando a versão 4.1, 4.1.x ou 4.2, é possível atualizar diretamente para a versão 4.2.1.
* Se você estiver usando a versão 4.0, será necessário atualizar para a versão 4.2 antes de atualizar para a versão 4.2.1.
* Se você estiver usando a versão 3.8.5, será necessário atualizar para a versão 4.0 antes de atualizar para a versão 4.2.
* Se você estiver em uma versão anterior à 3.8.5, consulte a seção Atualizar o AEM Guides no guia de instalação específico do produto.

>[!NOTE]
>
>Você deve instalar o service pack AEM antes de atualizar a versão do AEM Guides.

Para obter detalhes, consulte [Instruções de atualização](../install-guide/upgrade-xml-documentation.md).

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade para os aplicativos de software compatíveis com o AEM Guides 4.2. versão 1.

### Adobe Experience Manager

**Não UUID**
Versão 6.5 Service Pack 15, 14, 13 ou 12

**UUID**
Versão 6.5 Service Pack 15, 14, 13 ou 12

Para obter mais detalhes, consulte a seção *Requisitos técnicos* no guia Instalar e configurar o Adobe Experience Manager Guides.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2.1 (Não UUID) | 2022 ou superior | 2020.2 ou superior* | 2022 ou superior | 2020.3 ou superior |
| 4.2.1 (UUID) | 2022 ou superior | 2020.2 ou superior* | 2022 ou superior | 2020.4 ou superior |
| | | | |

*A linha de base e as condições criadas no AEM são compatíveis com as versões do FMPS a partir de 2020.2.

### Conector de oxigênio

| Versão | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2.1 (Não UUID) | 2.2-regular-3 | 2.2-regular-3 | 1,6 | 1,6 |
| 4.2.1 (UUID) | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |   |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Criação  

* Navtitle é removido do conteúdo ao alternar da exibição de layout para a exibição de autor ou fonte. (12174)
* O botão Fechar no Editor da Web não leva à página Navegação por AEM. (1948)
* Às vezes, ocorre um erro no aplicativo ao clicar em um mapa DITA. (11842)
* Ocorre um problema ao mover (arrastar e soltar) no lugar de um item de lista existente com o Controle de alterações ativado. (11570)
* Ocorre um problema ao mover (arrastar e soltar) como um novo item de lista com a opção Controlar alterações ativada. (11569)
* O recuo ou o recuo de itens de lista não funciona como esperado quando a opção Controlar alterações está ativada. (11568)
* Adicionar conteúdo em uma linha com a opção Controlar alterações ativada e desativar Controlar alterações não o desativa realmente. (11567)
* Dificuldade em arrastar e soltar um item de lista, o texto é movido no lugar do item de lista. (11566)
* Ao criar no elemento exibido em verde (Controlar alterações), o novo conteúdo é exibido como rastrear alteração mesmo que a opção rastrear alteração esteja desativada. (7021)
* O navegador (Editor da Web) congela ao carregar conteúdo com um esquema personalizado. (11211)
* PDF nativo | Ao criar uma predefinição de saída com a opção &quot;Adicionar ao perfil de pasta&quot;, a geração de PDF falha com uma exceção de ponteiro nulo. (10950)
* PDF nativo | A tag de imagem adiciona o atributo display-inline a todas as imagens. (10653)
* A inserção de arquivos multimídia de áudio e vídeo falha no formato YouTube sob o ícone **Inserir multimídia**. (11320)
* O erro de validação ocorre quando um mapa é criado usando o modelo que tem um elemento de título especializado. (11212)
* Editor da Web | O espaço sem quebra é adicionado no Editor de XML ao editar um tópico. (11786)

### Gerenciamento

* A guia Relatórios na interface do Editor da Web não exibe a lista de tópicos de mapas DITA antigos criados antes da atualização 4.2. (11708)

* A funcionalidade do botão Fazer upload de arquivos na interrupção da interface do usuário do Assets na versão 4.2. (11633)


### Publicação

* PDF nativo | A publicação de conteúdo que tem uma classe de saída com colchetes() leva a um congelamento da publicação. (1936)
* Saída JSON | Mapear metadados com o valor de propriedade como `"value in spaces and double quotes"` leva a um erro de publicação. (1933)
* Problema ocorre na pesquisa do site AEM (não funciona além de 2-3 nós de nível). (11352)
* Editor da Web | O caminho de saída e o modelo não podem ser selecionados na Predefinição de AEM. (11530)
* Ao atualizar da versão 4.1.x para a 4.2, o mecanismo de PDF nativo não funciona e lança NullPointerException mesmo para o sistema operacional suportado.(11526)
* O processo de PDF de download não está funcionando adequadamente no Editor da Web. (11496)
* PDF nativo | Comentários de rascunho são ocultos por padrão na saída gerada. (10560)
* PDF nativo | navtitle não é homenageado por topichead. (10509)
* PDF nativo | Adicionar `xref` a uma imagem não renderiza a imagem no PDF gerado. (11346)
* PDF nativo | a nota de rodapé presente no cabeçalho da tabela leva a negrito e texto alinhado ao centro no rodapé da página correspondente na saída do PDF. (10610)

### Tradução

* Com a atualização para a versão 4.2, todo o conteúdo da tradução fica Fora de sincronia ou sem cópia. (11834)

### Revisar

* A revisão concluída não abre no modo somente leitura. (11387)
