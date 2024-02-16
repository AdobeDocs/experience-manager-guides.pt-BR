---
title: Notas de versão | Instruções de atualização e problemas corrigidos na versão 4.3.1 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros e como atualizar para as versões 4.3.1 do Adobe Experience Manager Guides
exl-id: 3fb6dc31-ec6e-40f5-ab3f-a6e591da315e
feature: Release Notes
role: Leader
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 1%

---

# Versão 4.3.1 do Adobe Experience Manager Guides (outubro de 2023)

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão 4.3.1 do Adobe Experience Manager Guides (mais tarde chamados de *Guias do Experience Manager*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 4.3.1 dos Guias do Adobe Experience Manager](./whats-new-4-3-1-release.md).

## Atualização para a versão 4.3.1 dos Guias do Experience Manager


Você pode atualizar facilmente sua versão atual do Guides para a versão 4.3.1. Antes de prosseguir com a atualização para a versão 4.3.1 dos Guias do Experience Manager, você deve considerar os seguintes pontos: Você pode atualizar sua versão atual dos Guias do Experience Manager para a versão 4.3.1


- Se você estiver usando a versão 4.3.0, 4.2 ou 4.2.1, é possível atualizar diretamente para a versão 4.3.1.
- Se você estiver usando a versão 4.1 ou 4.1.x, será necessário atualizar para a versão 4.3.0, 4.2 ou 4.2.x antes de atualizar para a versão 4.3.1.
- Se você estiver usando a versão 4.0, será necessário atualizar para a versão 4.2 antes de atualizar para a versão 4.3.1.
- Se você estiver usando a versão 3.8.5, será necessário atualizar para a versão 4.0 antes de atualizar para a versão 4.2.
- Se você estiver em uma versão anterior à 3.8.5, consulte a seção Guias de atualização de Experience Manager no guia de instalação específico do produto.


>[!NOTE]
>
>Você deve instalar o service pack AEM antes de atualizar a versão dos Guias do Experience Manager.

Para obter detalhes, consulte [Instruções de atualização](../install-guide/upgrade-xml-documentation.md).

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade para os aplicativos de software suportados pelos Guias Experience Manager versão 4.3.1.

### Adobe Experience Manager

**4.3.1 Não UUID**
Versão 6.5 Service Pack 18, 17, 16, 15 ou 14

**4.3.1 UUID**
Versão 6.5 Service Pack 18, 17, 16, 15 ou 14

Para obter mais detalhes, consulte *Requisitos técnicos* no guia Instalar e configurar o Adobe Experience Manager Guides.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1 (Não UUID) | 2022 ou superior | 2020.2 ou superior* | 2022 ou superior | 2020.3 ou superior |
| 4.3.1 (UUID) | 2022 ou superior | 2020.2 ou superior* | 2022 ou superior | 2020.4 ou superior |
| | | | |

*A linha de base e as condições criadas no AEM são compatíveis com as versões do FMPS a partir de 2020.2.

### Conector de oxigênio

| Versão | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.1 (Não UUID) | 2.3-regular-5 | 2.3-regular-5 | 1,6 | 1,6 |
| 4.3.1 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   |



### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| Experience Manager Guias Componentes Pacote de conteúdo para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Criação  

- As horas da tarde não estão definidas no **Data** para criar linhas de base. (12712)
- Não é possível colar o código JSON no `<codeblock>` elemento do Editor da Web. (12326)
- Alterações de versão não salvas e os indicadores para elas não são exibidos para arquivos grandes. (11784)
- Ao editar no idioma coreano, o primeiro caractere é alterado para o padrão. (10049)

- O prefixo é duplicado no modo de visualização do Editor da Web. (13133)
- `Choicetable` não são exibidas ou não podem ser selecionadas. (12616)
- O Editor da Web lança erros de validação em cenários específicos ao criar um tópico usando um esquema personalizado. (12576)
- As referências de modelo de tópico diferencial não criam uma cópia na pasta de conteúdo ao criar um mapa a partir do modelo de mapa. (12150)

- A caixa de pesquisa nos mapas DITA não tem um botão Fechar. (11867)
- Ao salvar arquivos longos no Editor da Web, `DirtyChecker` lança uma exceção com um rastreamento de pilha longa e preenche os arquivos de log. (11860)
- A criação de tópicos DITA requer a permissão Excluir no nó de pasta correspondente, embora o mapa possa ser criado com a permissão Gravar. (11706)
- O Editor da Web mostra um título incorreto quando uma barra está presente. (10949)

- Se o título de um tópico contiver uma barra &quot;/&quot;, a guia no editor mostrará apenas as letras que vêm depois disso. (13455)
- A visualização da imagem não desaparece após ser exibida no Editor. (13454)
- Algumas das versões existentes ou seus rótulos não são exibidos no Histórico de versões após a atualização para 4.x. (13247)
- O painel Histórico de versões na interface do usuário do Assets mostra um carimbo de data e hora incorreto para o **Atual** campo. (12624)
- O tópico com título conref não é resolvido na Exibição do Repositório ou na Exibição do Mapa.(13304)


### Publicação

- PDF nativo | A ordem dos tópicos não é corrigida quando a saída de PDF é gerada. (13157)
- PDF nativo| Nenhuma tag de estilo padrão está disponível para `<p>`elemento. (12559)
- PDF nativo | Os estilos embutidos aplicados à região de conteúdo não se aplicam aos tópicos em primeiro e segundo plano. (13510)
- A variável `DeliveryTarget` O atributo não é propagado ao gerar a saída do site AEM.  (13132)
- A variável **Publish** O fluxo de trabalho fica travado ao gerar a saída do site AEM para conteúdo com determinados erros. (12000)

- PDF nativo | A inclusão de várias referências cruzadas estende o texto além da largura da coluna. (13004)
- PDF nativo | Quando o tópico e o título têm a mesma ID, isso resulta em uma geração mal formada da saída em PDF. (12644)
- PDF nativo | Ao adicionar uma classe de saída a um pai `<topicref>` elemento em um mapa DITA e aplicando um estilo personalizado à classe de saída, o estilo é aplicado aos elementos no corpo do tópico, incluindo títulos de seção. (12166)
- A publicação incremental não funciona se um mapa DITA tiver várias ditavalrefs. (12117)
- Site AEM | Ao criar um mapa com keydef apontando para um tópico como uma variável e adicionar processing-role=resource-only, você cria algumas páginas inesperadas. (12099)
- Se quaisquer ativos do DAM do AEM forem usados em qualquer saída diferente do site AEM, os metadados &quot;jcr:createdBy&quot; não refletirão o nome do editor ou o nome do usuário que modificou o mapa ou tópico DITA por último. (12090)
- AEM Sites | O mapa DITA com cabeçalho de tópico no navtitle (com caracteres não compatíveis) resulta em URLs de página inválidos. (1978)
- PDF nativo | Problemas ocorrem no suporte a topichead / topicmeta / navtitle no Frontmatter e Backmatter. (1969)
- PDF nativo | Gerar PDF para documentos grandes é um processo demorado. (1955)
- PDF nativo | Renomear uma predefinição gera uma NullPointerException ao gerar uma saída de PDF. (11889)
- A variável `<conref>` o conteúdo não é exibido na saída do PDF. (11131)
- Um espaço extra é adicionado dentro do `<div>` elementos sobre como alternar entre a visualização Autor e Fonte no editor de layout de página. (10750)
- O conteúdo replicado no gerenciador de nuvem AEM não está visível na instância de publicação. (9564)


### Gerenciamento

- O Histórico de versões não é exibido mesmo se a variável `dc:format` A propriedade não está presente para um ativo. (10463)
- A referência de conteúdo é quebrada ao copiar e colar arquivos DITA quando a ID do tópico não é a mesma que o GUID. (12614)
- Nas linhas de base dinâmicas, a lista de rótulos não é retirada das referências diretas da cópia de trabalho de um mapa DITA. (1917)
- A Linha de Base mostra o número incorreto de arquivos no Painel do Mapa ao usar a funcionalidade Procurar todos os tópicos. (13265)
- No Editor da Web, a linha de base mostra o título da versão anterior em vez da versão selecionada do arquivo DITA. (13444)

### Revisar

- A opção Revisar um tópico mostra comentários incorretos. (13453)
- O botão Fechar na página Revisar nos Guias do Experience Manager leva os usuários para a Página inicial do AEM. (13535)
- Os anexos não são exibidos no painel direito do editor para um tópico Em revisão. (13011)



### Tradução

- A linha de base exportada do **Tradução** o painel falha e não abre no idioma de destino. (13466)

- Novos projetos de tradução são criados em vez de adicionar novos trabalhos aos projetos de tradução existentes selecionados.  (10214)
- O título do arquivo traduzido é exibido no lugar do título do arquivo de origem. (11630)
- A aprovação automática às vezes não funciona e ocorrem exceções se um valor incorreto for definido no Status da tradução. (13607)
- A linha de base exportada do painel Tradução falha e não abre no idioma de destino. (12993)
- Alguns arquivos estão ausentes ao usar Linhas de Base na tradução. (13021)
