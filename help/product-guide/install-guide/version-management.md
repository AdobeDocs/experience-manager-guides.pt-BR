---
title: Gerenciamento de versão
description: Saiba como o Gerenciamento de versão funciona
exl-id: 24e44618-9c4e-4547-a00d-216ef3fb4854
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 0%

---

# Gerenciamento de versão {#id181GB000XY4}

O controle de versão é um aspecto importante de qualquer sistema de gerenciamento de conteúdo. Ele permite criar um instantâneo do seu ativo digital em um ponto específico do tempo. Com uma versão de um ativo digital em vigor, é possível restaurar a versão necessária do ativo e atualizá-lo. Normalmente, para criar uma versão de qualquer ativo, você faria check-out e check-in do ativo necessário.

Como administrador, você pode aplicar regras que impedirão os usuários de editar um arquivo sem fazer check-out. Da mesma forma, é possível garantir que todos os arquivos com check-out sejam verificados novamente para evitar perda de dados.

Em um ambiente multiuso, também é importante garantir que os usuários não excluam arquivos do sistema. Esse requisito é mais crítico para arquivos cujo check-out tenha sido feito por outros usuários.Você pode permitir ou impedir que os usuários substituam arquivos cujo check-out tenha sido feito por outros usuários. Para impedir que os usuários excluam acidentalmente arquivos verificados do sistema, o Guia AEM fornece uma configuração que pode ser usada. Além dos arquivos com check-out, também é possível controlar a exclusão de arquivos que contêm referências ou são referenciados a partir de outros arquivos. Além disso, você também pode criar uma nova versão para o arquivo carregado.

## Criar nova versão para o arquivo carregado

>[!NOTE]
>
> Essa configuração é aplicável somente durante o upload de arquivos.

Para criar uma nova versão do arquivo carregado, execute as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. Selecione o **Criar nova versão para o arquivo carregado** opção.

   Por padrão, essa opção está desativada.

   Quando a opção é selecionada, ocorre um novo mecanismo de gerenciamento de versão e substitui o comportamento de upload padrão para qualquer upload subsequente. Ele salva o conteúdo do arquivo carregado como uma nova versão. Se a opção estiver desmarcada, os Guias do AEM usarão o mecanismo de gerenciamento de versão padrão do AEM.

1. Clique em **Salvar**.


>[!NOTE]
>
> Você pode fazer upload de arquivos em lotes de 70 ou menos, se ativar a propriedade **Criar nova versão para o arquivo carregado** \(create.ver.new.content\) e use o **Interface do usuário do Assets** para carregar ativos em massa.

## Definir configurações para permitir a edição de arquivos com check-out

O Editor da Web do Guia AEM permite criar e atualizar tópicos DITA. Você pode configurar o Editor da Web para permitir a edição apenas dos documentos que foram submetidos a check-out no repositório. Isso garante que nenhum outro autor substitua acidentalmente um tópico que esteja aberto para edição por outro autor. Quando um tópico é aberto para edição, um autor pode fazer check-in do arquivo no momento de fechá-lo.

Outra regra importante é garantir que os arquivos dos quais foi feito check-out sejam devolvidos ao sistema. Isso impede que os usuários fechem os arquivos acidentalmente sem fazer o check-in deles novamente.

Execute as seguintes etapas para ativar esses recursos:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacote.

1. Selecione o **Desativar Edição Sem Check-Out** opção.

   ![](assets/xml-editor-config.png){width="650" align="left"}

   Com essa opção, os usuários não verão a opção Editar na barra de ferramentas até que façam check-out de um arquivo.

1. Selecione o **Solicitar check-in ao fechar** opção para mostrar uma mensagem de aviso sempre que um arquivo com check-out for fechado sem salvar ou fazer check-in novamente no repositório.

1. Clique em **Salvar**.


>[!NOTE]
>
> Independentemente de você ativar ou desativar esse recurso, as opções de Arquivo Fazer check-out e Check-in estarão sempre disponíveis em uma visualização de tópico.

## Substituir arquivo com check-out ao fazer upload

>[!NOTE]
>
> Essa configuração é aplicável somente quando você cria arquivos da interface do Assets e não quando você faz upload de arquivos usando a ferramenta WebDAV.

Para permitir que os usuários substituam o arquivo durante o upload cujo check-out foi feito por eles ou por algum outro usuário, execute as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. Selecione o **Substituir arquivo com check-out ao fazer upload** opção.

   Por padrão, essa opção está ATIVADA. Com essa opção selecionada, os usuários poderão substituir arquivos com check-out. Se a opção não estiver selecionada, o arquivo não poderá ser substituído se for submetido a check-out por eles ou por algum outro usuário.

1. Clique em **Salvar**.


## Impedir exclusão de arquivos com check-out

Para impedir que os usuários excluam acidentalmente os arquivos cujo check-out foi feito por eles ou por algum outro usuário, execute as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacote.

1. Selecione o **Impedir Exclusão de Conteúdo com Check-out** opção.

   Por padrão, essa opção está ATIVADA. Com essa opção selecionada, os usuários não poderão excluir arquivos com check-out.

1. Clique em **Salvar**.


Para dar suporte a esse recurso, uma nova propriedade de índice `drivelock` é adicionado em `oak:index`:

`/oak:index/damAssetLucene/indexRules/dam:Asset/properties/drivelock`

![](assets/index-property-oak-index-drivelock.png){width="800" align="left"}

Além da nova propriedade index, verifique se as seguintes propriedades estão definidas em `/oak:index/damAssetLucene`:

- `jcr:primaryType`=`"oak:QueryIndexDefinition"`
- `async`=`"async"`
- `compatVersion`=`"{Long}2"`
- `evaluatePathRestrictions`=`"{Boolean}true"`
- `reindex`=`"{Boolean}false"`
- `reindexCount`=`"{Long}3"` *\(essa é a contagem de quantas vezes a reindexação é feita, ela é substituída pela instalação do nosso pacote\)*
- `type`=`"lucene"`

>[!NOTE]
>
> É possível alterar o valor de `reindex` para `"{Boolean}true"`. Isso permitirá resultados de pesquisa mais rápidos para os arquivos com check-out dentro de uma hierarquia de pastas.

## Impedir exclusão de arquivos referenciados

Como administrador, você pode controlar quem pode excluir arquivos do repositório AEM. Especificamente, se um arquivo contiver referências ou for referenciado por algum outro arquivo, você poderá definir quem poderá excluir esses arquivos.

Usando essa configuração, você pode permitir ou impedir que todos os usuários excluam arquivos, ou permitir que apenas um grupo de usuários específico exclua arquivos. Se a exclusão de arquivos for permitida, o seguinte processo será seguido:

- Se você estiver excluindo uma pasta, que contém todos os arquivos referenciados e referenciados, todos os arquivos serão excluídos. Primeiro, o processo excluirá todos os arquivos que não contêm nenhuma referência, seguido dos arquivos que contêm referências ou são mencionados.

- Se você estiver excluindo uma pasta, e qualquer arquivo dentro da pasta for referenciado por um arquivo fora dessa pasta, será solicitado que você remova a referência antes de excluir o arquivo.


Para definir quem pode excluir um arquivo que contenha referências ou seja referenciado por outros arquivos, execute as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. Localize o **Exclusão de bloco para ativos referenciados** opção.

1. Dependendo de quem você deseja conceder acesso para exclusão, especifique uma das seguintes constantes:

   - allow\_unsafe\_delete\_for\_all: dê permissão a todos os usuários para excluir arquivos. Nesse caso, se o arquivo\(s\) contiver referências ou for referenciado por outros arquivos, você também poderá excluí-lo à força\(s\). Antes de excluir o arquivo, você verá um prompt com as referências. Você pode cancelar a operação de exclusão, remover as referências e finalmente excluir o arquivo\(s\). Ou você pode forçar a exclusão do arquivo\(s\) sem remover as referências.

     ![](assets/allow_unsafe_delete-force-delete.PNG){width="550" align="left"}

   - allow\_unsafe\_delete\_for\_delete\_assets\_group: um administrador ou usuário pertencente à *delete-assets* grupo tem permissão para excluir arquivos. Se qualquer outro usuário tentar excluir arquivos com qualquer referência, não será permitido excluir esses arquivos até que todas as referências sejam removidas. A captura de tela a seguir é exibida quando um usuário sem permissões tenta excluir arquivos.

     ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG){width="550" align="left"}

   - block\_unsafe\_delete\_for\_all: proibir todos os usuários \(incluindo Administradores\) de excluir arquivos até que as referências para e do arquivo\(s\) sejam removidas.

1. Clique em **Salvar**.


## Limpar versões anteriores de arquivos DITA

Quando você atualiza o conteúdo e cria novas versões, as versões anteriores dos arquivos DITA são mantidas no repositório. Muitas versões podem ser criadas para seus arquivos DITA durante um período e podem ocupar uma grande quantidade de espaço no repositório. O Guias do AEM permite configurar as versões mais antigas que devem ser excluídas do repositório.

Você pode acessar esse utilitário usando o URL fornecido, se tiver direitos administrativos:

`<server folder path> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`

A versão de um arquivo DITA que atende a qualquer um dos critérios fornecidos é mantida e não é removida:

- É a primeira versão de um arquivo
- Está incluído em uma linha de base
- Está incluído em qualquer fluxo de trabalho de tradução ou revisão
- Tem um rótulo aplicado a ele
- Atende à idade ou ao número de critérios de versão definidos

Execute as seguintes etapas para expurgar as versões mais antigas:

1. Informe os seguintes detalhes sobre os arquivos que deseja expurgar:

   ![](assets/preview-purge-report.png){width="350" align="left"}

1. 
   - **Número de versões a serem mantidas da versão mais recente**: Informe o número de versões que devem ser retidas e não expurgadas. Por exemplo, se informarmos 5, as últimas 5 versões serão retidas e as versões anteriores serão qualificadas para expurgação caso outras condições de expurgação sejam atendidas.
- **Reter Versões Criadas Dentro Do Período \(Em Dias\)**: insira a idade máxima de uma versão em dias. As versões anteriores ao número de dias especificado são qualificadas para expurgação caso outras condições de expurgação sejam atendidas. Por exemplo, se informarmos 100, todas as versões criadas antes de 100 dias serão qualificadas para expurgação caso outras condições de expurgação sejam atendidas.
- **Caminho**: selecione o caminho do arquivo ou pasta cujos arquivos você deseja limpar.

  >[!NOTE]
  >
  > Você só pode limpar arquivos DITA.

1. Clique em **Visualizar relatório de limpeza**.

   >[!NOTE]
   >
   > Só pode haver uma tarefa de limpeza por vez. Você não pode iniciar outra operação de expurgação de versão se uma estiver em processo.

   O relatório de limpeza de versão é gerado.

1. Baixe o relatório de limpeza de versão e verifique os arquivos e as versões que serão removidos.
1. Você pode optar por **Cancelar limpeza** ou **Iniciar Expurgação**.

   ![](assets/download-purge-report.png){width="350" align="left"}

   O status de expurgação é exibido.

   Clique em **Baixar relatório de limpeza de versão** para exibir as versões expurgadas. Esse relatório fornece o status de limpeza em todas as versões, juntamente com os motivos pelos quais uma versão específica foi retida ou foi removida.


>[!NOTE]
>
> O relatório é baixado no seguinte local: /var/dxml/versionpurge
