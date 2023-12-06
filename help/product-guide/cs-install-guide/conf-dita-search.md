---
title: Configurar pesquisa para a interface do usuário do AEM Assets
description: Saiba como configurar a pesquisa para a interface do usuário do AEM Assets
exl-id: 125d247f-1017-4450-9e3f-9ecc7188ca8f
source-git-commit: 9d34a029d174655d9e3176ce9c6a89f0a03af691
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 1%

---

# Configurar pesquisa para a interface do usuário do AEM Assets {#id192SC800MY4}

Por padrão, o AEM não reconhece o conteúdo DITA e, portanto, não fornece nenhum mecanismo para pesquisar conteúdo DITA em seu repositório. Além disso, não há recurso de OOTB para pesquisar conteúdo com base em sua UUID. Guias de AEM permitem adicionar os recursos de pesquisa de conteúdo DITA e pesquisa baseada em UUID no repositório AEM.

A configuração da pesquisa de conteúdo DITA envolve as seguintes tarefas:

1. [Adicionar componente de pesquisa do elemento DITA na interface do usuário do Assets](#id192SF0F50HS)
1. [Adicionar componente de pesquisa baseado em UUID na interface do usuário do Assets](#id2034F04K05Z)
1. [Fornecer permissões aos usuários](#id192SF0G0RUI)
1. [Adicionar elementos ou atributos personalizados na pesquisa](#id192SF0G10YK)
1. [Extrair metadados de conteúdo existente](#id192SF0GA0HT)

Além de adicionar o recurso de pesquisa, você também pode configurar as pastas que não devem ser incluídas na pesquisa. Para obter mais detalhes, consulte [Excluir arquivos temporários dos resultados da pesquisa](#id197AHI0035Z).

## Adicionar componente de pesquisa do elemento DITA na interface do usuário do Assets {#id192SF0F50HS}

Execute o seguinte para adicionar o componente de pesquisa de conteúdo DITA na interface do usuário do AEM Assets:

1. Faça logon no Adobe Experience Manager como administrador.

1. Clique no link **Adobe Experience Manager** vincule na parte superior e escolha **Ferramentas**.

1. Selecionar **Geral** na lista de ferramentas e clique no link **Pesquisar no Forms** bloco.

1. No **Pesquisar no Forms** , selecione a **Trilho de pesquisa do administrador de ativos**.

1. Clique em **Editar**.
1. No **Selecionar predicado** , role até o final da lista.

1. Arrastar e soltar **Predicado do elemento DITA** no local necessário no formulário de pesquisa.

   ![](assets/drag-search-predicate.png)

1. Clique em **Concluído** para salvar as alterações.

   Ao acessar a opção Filtros na interface do usuário do Assets, você obterá a opção de filtragem de pesquisa Elemento DITA.

   ![](assets/search-filter-asset-console.png)


## Adicionar componente de pesquisa baseado em UUID na interface do usuário do Assets {#id2034F04K05Z}

Execute o seguinte para adicionar o componente de pesquisa baseada em UUID na interface do usuário do AEM Assets:

1. Faça logon no Adobe Experience Manager como administrador.

1. Clique no link **Adobe Experience Manager** vincule na parte superior e escolha **Ferramentas**.

1. Selecionar **Geral** na lista de ferramentas e clique no link **Pesquisar no Forms** bloco.

1. No **Pesquisar no Forms** , selecione a **Trilho de pesquisa do administrador de ativos**.

1. Clique em **Editar**.
1. No **Selecionar predicado** escolha **Predicado da propriedade** e arraste-o e solte-o no local desejado no formulário de pesquisa.

1. No **Configurações** , forneça os seguintes detalhes para o novo **Predicado da propriedade** componente:

   - **Rótulo do campo**: UUID
   - **Nome da propriedade**: jcr:content/fmUuid
1. Clique em **Concluído** para salvar as alterações.

   Ao acessar a opção Filtros na interface do usuário do Assets, você terá a opção de filtragem de pesquisa baseada em UIS.


## Fornecer permissões aos usuários {#id192SF0G0RUI}

Os autores e editores precisariam receber permissões explícitas para acessar os recursos de pesquisa na interface do usuário do Assets. Se você não conceder essas permissões, os usuários não poderão pesquisar conteúdo DITA com base em seus valores de elemento/atributo ou UUID.

Execute as seguintes etapas para fornecer acesso ao recurso Pesquisa DITA:

1. Acesse a página de permissões do usuário e do grupo.

1. Procure o grupo de usuários ou um usuário individual ao qual você deseja conceder acesso. Por exemplo, para conceder acesso a todos os usuários no grupo de autores, insira autores no campo **Filtrar consulta** e pressione **Enter**.

   ![](assets/authors-group-permission.png)

1. Selecione o **autores** grupo.

1. No painel direito, selecione a opção **Permissões** guia.

1. Navegue até o seguinte local da pasta:

   /conf/global/settings/dam/search

1. Dê a **Ler** permissão na pasta de pesquisa.

   ![](assets/read-permission-authors.png)

1. Clique em **Salvar**.


O usuário ou grupo de usuários selecionado terá acesso ao recurso de conteúdo DITA de pesquisa na interface do usuário do Assets.

## Adicionar elementos ou atributos personalizados na pesquisa {#id192SF0G10YK}

Para que a pesquisa DITA funcione, é necessário algum pré-processamento do conteúdo DITA. Essa etapa de pré-processamento extrai conteúdo seletivo de mapas e tópicos DITA individuais para que ele possa ser indexado para uma pesquisa mais rápida. Internamente, esse processo é chamado de *Serialização*. A serialização de arquivos DITA ocorre durante o upload do conteúdo ou também pode ser executada sob demanda. Ele usa um arquivo de configuração para determinar quanto conteúdo de cada arquivo DITA deve ser indexado. O local padrão do arquivo de serialização é:

/libs/fmdita/config/serializationconfig.xml

A configuração de pesquisa padrão permite procurar todos os elementos e atributos no DITA `prolog` elemento. Se quiser pesquisar com base em outros elementos ou atributos, será necessário configurar o arquivo de serialização de pesquisa.

>[!NOTE]
>
> Se você quiser usar a configuração de pesquisa padrão na variável `prolog` elemento, você poderá ignorar esse processo.

Esse arquivo contém duas seções principais: conjunto de atributos e conjunto de regras. Um trecho da seção do conjunto de regras é fornecido abaixo:

```
<ruleset filetypes="xml dita"><!-- Element rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]//*[not(*)]" text="yes" attributeset="all-attrs" /><!-- Attribute rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]///@[local-name() != 'class']" /></ruleset>
```

Na seção do conjunto de regras, você pode especificar:

- Regras para extrair os elementos

- Regras para extrair atributos


Uma regra consiste no seguinte:

xpath : esta é a consulta XPath que recupera os elementos ou atributos de arquivos DITA. A configuração padrão para a regra de elemento recupera todas `prolog` elementos. E a configuração padrão para a regra de atributo recupera todos os atributos de `prolog` elementos. Você pode especificar uma consulta XPath para serializar os elementos ou atributos que deseja pesquisar.

A consulta XPath contém o nome de classe do tipo de documento. A variável `topic/topic` classe é usada para documentos DITA do tipo tópico. Se você quiser criar uma regra para outros documentos DITA, use os seguintes nomes de classe:

| Tipo de documento | Nome da classe |
|-------------|----------|
| Tópico | - tópico/tópico |
| Tarefa | - tópico/tópico tarefa/tarefa |
| Conceito | - tópico/tópico conceito/conceito |
| Referência | - tópico/tópico referência/referência |
| Mapa | - mapa/mapa |

texto : se você quiser pesquisar o texto dentro do elemento especificado, especifique o valor yes. Se você especificar não como valor, apenas os atributos dentro do elemento serão serializados. Os atributos que você deseja pesquisar precisam ser especificados na seção de conjunto de atributos.

conjunto de atributos : especifique a ID do conjunto de atributos que você deseja associar a esta regra. O valor all-attrs é um caso especial para indicar que todos os atributos para essa regra devem ser serializados.

Um conjunto de atributos contém uma lista de atributos que você deseja pesquisar no conteúdo DITA. O conjunto de atributos contém o seguinte:

id : um identificador exclusivo para o conjunto de atributos. Essa ID é especificada no parâmetro attributeset de um conjunto de regras.

atributo : uma lista de atributos que você deseja pesquisar. Para cada atributo, você precisa criar uma entrada individual no `attribute` elemento.

Execute as seguintes etapas para adicionar elementos ou atributos DITA personalizados no arquivo de serialização de pesquisa:

1. Use o Gerenciador de pacotes para baixar o arquivo /libs/fmdita/config/serializationconfig.xml.

1. Crie um nó de sobreposição do `config` pasta dentro do `apps` nó.

1. Navegue até o arquivo de configuração disponível no `apps` nó:

   `/apps/fmdita/config/serializationconfig.xml`

1. Adicione o elemento necessário ou os conjuntos de regras de atributo.

1. Confirme as alterações e execute o pipeline \(CI/CD\) do Cloud Manager para implantar alterações de configuração.


As novas informações de serialização são armazenadas e ativadas para pesquisa. No entanto, é necessário extrair os metadados do conteúdo DITA existente para disponibilizá-los para pesquisa.

## Extrair metadados de conteúdo existente {#id192SF0GA0HT}

Depois de fazer qualquer alteração no arquivo de serialização de pesquisa padrão, você deve ativar a opção Extração de metadados DITA no *com.adobe.fmdita.config.ConfigManager* agrupar e executar o fluxo de trabalho para extrair metadados. Isso extrai os metadados necessários dos arquivos DITA existentes, e os mesmos são então disponibilizados para pesquisa.

Caso você crie novos arquivos ou edite qualquer arquivo após atualizar o arquivo de serialização, os metadados serão automaticamente extraídos desses arquivos. O processo de extração de metadados só é necessário para arquivos que já existem no repositório AEM.

A extração de metadados de arquivos DITA existentes envolve duas tarefas:

1. Ativação da opção de extração de metadados no configMgr
1. Execução do workflow de extração de metadados

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(property\) para configurar a opção de extração de metadados:

| PID | Chave de propriedade | Valor da propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `dita.serialization` | Booleano \(true/false\).<br> **Valor padrão**: `false` |

Execute as seguintes etapas para executar o fluxo de trabalho de extração de metadados:

1. Faça logon no Adobe Experience Manager como administrador.

1. Clique no link **Adobe Experience Manager** vincule na parte superior e escolha **Ferramentas**.

1. Selecionar **Guias** na lista de ferramentas e clique no botão **Extração de metadados DITA** bloco.

1. Se quiser extrair metadados de um único arquivo e suas dependências, clique no link **Selecionar um arquivo** vincular e procurar um arquivo.

1. Para extrair metadados de vários arquivos de uma pasta, clique no link **Selecionar pasta\(s\)** e selecione a pasta desejada. Clique em **Adicionar** botão para adicionar a pasta à lista de tarefas de serialização.

   >[!NOTE]
   >
   > Você pode selecionar e adicionar várias pastas a uma tarefa de serialização.

1. Clique em **Início**.

1. Na caixa de diálogo Confirmar extração de metadados, clique em **OK**.


## Excluir arquivos temporários dos resultados da pesquisa {#id197AHI0035Z}

Por padrão, a pesquisa é executada em todo o repositório do AEM. Pode haver alguns locais que você gostaria de excluir da pesquisa. Por exemplo, ao iniciar o fluxo de trabalho de tradução de conteúdo, os arquivos não aprovados permanecem em um local de pasta temporária. Quando você executa a pesquisa, os arquivos desse local temporário também são retornados nos resultados da pesquisa.

Para impedir que os Guias do AEM pesquisem o local da pasta de tradução temporária, é necessário adicionar o local da pasta temporária na lista de exclusões.

Execute as seguintes etapas para excluir a pasta de tradução temporária da pesquisa:

>[!NOTE]
>
> Você pode adicionar qualquer outro local de pasta à lista de exclusões usando esse procedimento. Para obter mais detalhes sobre como trabalhar com índices, consulte [Pesquisa e indexação de conteúdo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=pt-BR).

1. Adicione a seguinte propriedade no índice damAssetLucene personalizado:

   | Nome da propriedade | Tipo | Valor |
   |-------------|----|-----|
   | excludedPaths | String\[\] | Adicione o seguinte valor a essa propriedade:<br> `/content/dam/projects/translation\_output` |

1. Navegue até o nó lucene disponível no seguinte local:

   /oak:index/lucene

1. Adicione a seguinte propriedade no nó lucene:

   | Nome da propriedade | Tipo | Valor |
   |-------------|----|-----|
   | excludedPaths | String\[\] | Adicione os seguintes valores a essa propriedade:<br> `/content/dam/projects/translation\_output` |
