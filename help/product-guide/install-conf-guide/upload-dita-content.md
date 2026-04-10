---
title: Fazer upload de conteúdo DITA existente
description: Saiba como fazer upload do conteúdo DITA existente no Experience Manager Guides usando a ferramenta WebDAV e o FrameMaker
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---

# Fazer upload de conteúdo DITA existente usando a ferramenta WebDAV e o FrameMaker para no local

Provavelmente você teria um repositório de conteúdo DITA existente que gostaria de usar com o AEM Guides. Para tal conteúdo existente, você pode usar qualquer uma das seguintes abordagens para fazer upload em massa de conteúdo para o repositório do AEM.

- [Usar uma ferramenta WebDAV](#use-a-webdav-tool)
- [Usar o FrameMaker](#use-framemaker)

## Usar uma ferramenta WebDAV

Se estiver criando tópicos e mapas em qualquer outro editor DITA, você pode usar qualquer ferramenta WebDAV para fazer upload dos arquivos. O procedimento fornecido nesta seção usa o WinSCP como a ferramenta WebDAV para fazer upload de conteúdo.

Execute as seguintes etapas para usar o WinSCP para fazer upload de arquivos:

1. Baixe e instale o WinSCP em seu computador.

1. Inicie o aplicativo WinSCP.

   A caixa de diálogo Login é exibida.

1. Na caixa de diálogo Logon, especifique uma configuração Novo Site escolhendo WebDAV como o **Protocolo de Arquivo** e fornecendo outros detalhes de conexão, como:

   - o URL onde o servidor do AEM está hospedado,

   - o número da porta `\(default is 4502\)` e

   - o nome de usuário e a senha para acessar o servidor do AEM.

1. Selecione **Logon**.

   Em uma conexão bem-sucedida, você verá o conteúdo do AEM Assets na interface do usuário WinSCP. Você pode navegar, criar, atualizar ou excluir conteúdo facilmente usando o explorador de arquivos WinSCP.

## Fazer upload de conteúdo com UUID usando uma ferramenta WebDav {#id201MI0I04Y4}

Você pode usar qualquer um dos métodos a seguir para fazer upload de conteúdo com UUID:

- Arraste e solte conteúdo do seu sistema local.
- Use o fluxo de trabalho **Criar** \> **Arquivos** da interface do Assets da AEM.
- Use uma ferramenta como o WinSCP.

Caso use uma ferramenta como o WinSCP, você poderá definir a ação a ser executada em um arquivo duplicado definindo a opção **Mover arquivo antigo com a mesma UUID para a nova pasta** no configMgr. Essa opção define que ação é executada em um arquivo que está disponível em algum outro local no repositório do AEM. Esta configuração está disponível no pacote `*com.adobe.fmdita.config.ConfigManager*` no configMgr.

Por padrão, a opção **Mover arquivo antigo com Mesmo UUID para Nova Pasta** está ATIVADA. Isso implica que, quando o arquivo que está sendo carregado estiver presente em alguma outra pasta no repositório, o arquivo existente será movido para o local atual e substituído pelo arquivo que está sendo carregado. Se você não selecionar essa opção, o arquivo será substituído em seu local existente.

**Observações adicionais sobre o trabalho com arquivos baseados em UUID**:

Os seguintes pontos devem ser considerados ao mover ou copiar conteúdo no repositório do AEM:

- Ao copiar um ou mais arquivos de um local para outro, um novo UUID é gerado para arquivos que não têm UUID. Essa UUID é adicionada aos metadados do arquivo.

- Se um arquivo tiver um conflito ou uma duplicata, um nome de arquivo exclusivo será gerado para o novo arquivo que está sendo copiado ou movido.

- Dois arquivos não podem ter a mesma UUID. Um UUID exclusivo é atribuído a todos os novos arquivos.


Os seguintes pontos devem ser considerados ao mover ou copiar o conteúdo do sistema local para o repositório do AEM:

- Se um arquivo estiver sendo carregado por dois usuários diferentes ao mesmo tempo, o arquivo processado posteriormente substituirá o arquivo anterior. No entanto, essa prática é rara e deve ser evitada.

- Ao fazer check-out do conteúdo do repositório do AEM e fazer alterações no sistema local, verifique se o nome do arquivo não foi alterado no momento do upload do arquivo.

## Usar o FrameMaker

O Adobe FrameMaker vem com um poderoso conector AEM que permite carregar facilmente seu DITA existente e outros documentos do FrameMaker `\(.book and .fm\)` no AEM. Você pode usar várias funcionalidades de upload de arquivos, como fazer upload de um único arquivo, fazer upload de uma pasta completa com ou sem dependências \(como referências de conteúdo, referências cruzadas e elementos gráficos\).

Execute as seguintes etapas para usar o AEM Connector do FrameMaker para fazer upload de conteúdo:

1. Inicie o FrameMaker.

1. Abra a caixa de diálogo **Gerenciador de Conexões**.

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Insira os seguintes detalhes para se conectar ao repositório do AEM:

   - **Nome**: insira um nome descritivo para identificar a conexão com o servidor do AEM.
   - **Servidor**: insira a URL e o número da porta do servidor AEM.

   - **Nome de Usuário**/**Senha**: digite o nome de usuário e a senha para acessar o servidor AEM.

1. Selecione **Conectar**.

   Depois que a conexão for estabelecida, o Assets do repositório do AEM será exibido na janela Gerenciador do repositório.

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Clicar com o botão direito do mouse em qualquer arquivo ou pasta permite executar operações relacionadas. Por exemplo, se você clicar com o botão direito do mouse em uma pasta, receberá opções para carregar um arquivo, carregar um arquivo com dependências, carregar uma pasta inteira e assim por diante.






**Tópico pai:**&#x200B;[&#x200B; Migrar conteúdo existente](migrate-content.md)
