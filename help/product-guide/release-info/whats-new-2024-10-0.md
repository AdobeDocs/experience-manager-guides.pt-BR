---
title: Notas de versão | Novidades da versão 2024.10.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2024.10.0 do Adobe Experience Manager Guides
role: Leader
source-git-commit: 545e51cbd970aa3df01a0fe2461a2e730c0db66a
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 0%

---

# Novidades da versão 2024.10.0 (outubro de 2024)

Este artigo aborda os recursos novos e aprimorados introduzidos na versão 2024.10.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2024.10.0](fixed-issues-2024-10-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2024.10.0](../release-info/upgrade-instructions-2024-10-0.md).


## Aprimoramentos de publicação

As seguintes melhorias de publicação de conteúdo foram feitas na versão 2024.10.0:




### Melhorias na publicação do fragmento de conteúdo

O Experience Manager Guides também fornece algumas melhorias úteis nos Fragmentos de conteúdo:

- O Experience Manager Guides permite publicar um tópico ou seus elementos em um fragmento de conteúdo.

- Você pode publicar e exibir os Fragmentos de Conteúdo de um tópico da seção **Saídas** em **Propriedades do Arquivo**.


- Você pode criar facilmente variações de fragmentos de conteúdo filtrando o conteúdo com condições enquanto publica em um fragmento de conteúdo.

- Use a nova interface de mapeamento para selecionar e publicar facilmente os elementos em um Fragmento de conteúdo.

Agora, a publicação do Fragmento de conteúdo substitui somente o conteúdo mapeado, em vez de substituir o Fragmento de conteúdo completo. Esse recurso permite que um fragmento de conteúdo contenha dados de várias fontes, como vários tópicos ou o editor de fragmento de conteúdo.

![Adicionar o modelo do fragmento e os detalhes do mapeamento na caixa de diálogo Publish como Fragmento de Conteúdo](assets/content-fragment-mapping.png)

Para obter mais detalhes, consulte [Fragmentos de conteúdo do Publish](../user-guide/publish-content-fragment.md).


### Variantes do Fragmento de experiência do Publish com base em filtros de condição

O Experience Manager Guides permite publicar um tópico ou seus elementos em um Fragmento de experiência. Agora, você também pode criar variantes de Fragmento de experiência usando os filtros condição ou DITAVAL e reutilizá-los em diferentes canais ou para públicos diferentes.

Saiba mais sobre como [Fragmentos de experiência do Publish](../user-guide/publish-experience-fragment.md).


### Predefinição do AEM Sites reorganizada para facilitar o uso

As configurações foram reorganizadas para ajudar você a configurar rapidamente a predefinição de saída e gerar a saída do AEM Sites.
Você pode criar as predefinições existentes do AEM Sites selecionando a opção **Usar mapeamento de componente herdado** na caixa de diálogo **Nova predefinição de saída**.

Exiba as guias **Geral**, **Conteúdo** e **Referência de mapa cruzado** nas predefinições do AEM Sites:
- **Geral**: contém as configurações gerais para gerar a saída. Você pode especificar o site e o caminho de saída, excluir ou substituir páginas de saída existentes, excluir as páginas geradas anteriormente para tópicos removidos, selecionar o modelo de design, reter os arquivos temporários e especificar o fluxo de trabalho de pós-geração.
- **Conteúdo**: contém as configurações aplicáveis ao conteúdo para geração de saída. É possível selecionar os filtros, a linha de base do mapa DITA e as propriedades de metadados para publicação.
- **Referências de mapa cruzado**: esta lista contém tópicos que contêm referências de mapa cruzado com escopo =&quot;par&quot;. É possível especificar o contexto de publicação para uma lista de referências de mapa cruzado com scope=&quot;peer&quot; para tópicos disponíveis em outros mapas DITA. Essa guia será exibida se você usar a versão do Experience Manager Guides (UUID).



### Referências de mapa cruzado de predefinições do AEM Sites no Editor da Web

O aprimoramento mais recente do Experience Manager Guides introduz referências de mapa cruzado nas predefinições de AEM Sites do Editor da Web.
As referências entre mapas no Experience Manager Guides ajudam a melhorar a navegação do conteúdo, aumentar a reutilização do conteúdo e aprimorar a experiência do usuário.


É possível especificar o contexto de publicação para uma lista de referências entre mapas a tópicos disponíveis em outros mapas DITA com scope=&quot;peer&quot;. Por exemplo, o Tópico 1 no Mapa A contém uma referência ao Tópico 2. O tópico 2 pode estar presente em mapas únicos ou múltiplos.  Você pode selecionar o mapa principal e uma predefinição específica ou a saída publicada mais recentemente para cada link.

Se o mesmo tópico for referido mais de uma vez em um arquivo, será possível adicionar um contexto de publicação diferente para cada instância. Isso proporciona maior flexibilidade e controle sobre o conteúdo. Por exemplo, o Tópico 3 está presente no Mapa B e no Mapa C. O Tópico 1 contém duas referências ao Tópico 3. Você pode escolher o Mapa B como o mapa principal do primeiro link e o Mapa C como principal do segundo link.

![Predefinição herdada do AEM Sites](assets/aem-sites-legacy.png)

*Especifique o contexto de publicação para os tópicos vinculados da guia **Referências entre mapas**da predefinição **AEM Sites**.*

Saiba mais sobre [Predefinições do AEM Sites](../user-guide/generate-output-aem-site.md).

### Opção para escolher uma hierarquia de arquivos simples ou aninhada para saída HTML5

Agora, o Experience Manager Guides permite que você mantenha a hierarquia de pastas simples para os arquivos temporários em que todo o conteúdo é publicado no formato de saída HTML5 e salvo em uma única pasta.
Se você não optar por nivelar a hierarquia de arquivos, a saída HTML5 será gerada em uma hierarquia de pastas aninhada. Isso significa que a estrutura de pastas original do conteúdo, com arquivos organizados em subpastas, é replicada na saída. Essa hierarquia de pastas aninhada permite uma organização mais complexa e a categorização de arquivos, facilitando o gerenciamento e a navegação de grandes volumes de dados.


Saiba mais sobre como [gerar saída de HTML5](../user-guide/generate-output-html5.md).


## Aprimoramentos do editor

Os seguintes aprimoramentos do editor foram adicionados na versão 2024.10.0:

### Acesso somente leitura ao modo Autor e Source para arquivos bloqueados

Se outro usuário bloquear ou fizer check-out de um arquivo DITA ou Markdown, você não poderá editar nem alterar o conteúdo. Além da Visualização, também é possível exibi-lo como um arquivo somente leitura no modo Autor ou Source.
No modo somente leitura, você pode exibir o conteúdo junto com as marcas e os atributos no modo **Autor** ou **Source** e editar as propriedades do arquivo.

Você também pode acessar o modo de exibição **Layout** para mapas DITA somente leitura.
>[!NOTE]
>
> Os administradores do perfil da sua pasta devem atualizar o *ui_config.json* para que você possa acessar harmoniosamente os arquivos somente leitura nos modos Autor, Source e Layout.

![editor de arquivo bloqueado](./assets/locked-file-editor.png)
*Exibir os arquivos bloqueados no modo Autor e Source.*


Saiba como [abrir arquivos bloqueados nos modos Autor e Source](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes).


### Condições agrupadas para a organização aprimorada de conteúdo

O Experience Manager Guides agora permite agrupar condições e apresentá-las em uma hierarquia aninhada, permitindo adicionar várias condições a um único grupo. Ao agrupar condições, é possível organizá-las e aplicá-las melhor em todo o conteúdo.

![condições organizadas em uma hierarquia aninhada](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Saiba mais sobre a descrição do recurso **Condições** na seção [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).




