---
title: Experience Manager Guides e Edge Delivery Services (Beta)
description: Entenda como o Edge Delivery Services (Beta) expande as possibilidades de criação e publicação do Experience Manager Guides.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 7ca2eeb0356f3c82a8d970f291006fc6d19aca23
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 0%

---

# Experience Manager Guides e Edge Delivery Services (Beta)

O Adobe Experience Manager Guides permite publicar seu conteúdo DITA diretamente no Edge Delivery Services (EDS), atualmente disponível no *Beta*, por meio de um perfil de publicação dedicado com base no GitHub. Esse recurso permite que as organizações forneçam experiências de documentação responsivas de alto desempenho enquanto mantêm fluxos de trabalho de criação baseados em DITA no Experience Manager Guides.

Para obter mais detalhes sobre o uso do EDS no Adobe Experience Manager, consulte [Visão geral do Edge Delivery Services](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-service/content/edge-delivery/overview).

Para habilitar a publicação do Experience Manager Guides no EDS (Beta), você deve concluir uma série de etapas de configuração no GitHub e no Experience Manager Guides. As seções abaixo descrevem cada etapa em sequência e explicam como elas funcionam juntas no fluxo de trabalho de publicação geral.

1. [Instale e configure o GitHub para EDS (Beta)](#set-up-and-configure-github-for-eds-beta)
2. [Criar e configurar um perfil de publicação para EDS (Beta) no Experience Manager Guides](#create-and-configure-a-publish-profile-for-eds-beta-in-experience-manager)
3. [Personalizar saída usando blocos EDS](#customize-output-using-eds-blocks)

Para obter uma apresentação rápida em vídeo, exiba [Publicação no AEM Guides](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/publishing-in-aem-guides-aug25).



## Instale e configure o GitHub para EDS (Beta)

Esta seção descreve como instalar e configurar o GitHub para uso com o EDS (Beta). Ele aborda a criação de um repositório usando a matriz do Adobe, a conexão do GitHub ao Adobe Experience Manager por meio da Sincronização de código do AEM, a configuração dos aplicativos GitHub e OAuth necessários e a definição do ponto de montagem do repositório usado para publicar conteúdo.

### Criar um repositório GitHub para EDS (Beta)

O EDS (Beta) requer um repositório GitHub com uma estrutura predefinida. O Adobe fornece um repositório padrão oficial projetado especificamente para usuários do Experience Manager Guides.

Execute as seguintes etapas para criar seu repositório:

1. Abra o repositório de modelos padronizados do Experience Manager Guides [`aem-guides-boilerplate`](https://github.com/adobe/aem-guides-boilerplate).
   ![](assets/eds-boilerplate-template.png){align="left"}

2. Crie um novo repositório usando este modelo. Saiba mais sobre [Criação de um repositório a partir de um modelo](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template). Verifique se a visibilidade do repositório está definida como *Pública* para que possa ser acessada pelo EDS.

   ![](assets/eds-create-new-repo.png){align="left"}

O repositório agora é criado e se alinha à estrutura do modelo padronizado.

![](assets/eds-repo-created-github-view.png){align="left"}

### Conectar o GitHub à Adobe por meio da sincronização de código do AEM

O Adobe Experience Manager usa um aplicativo GitHub chamado **Sincronização de código do AEM** para enviar conteúdo do Experience Manager Guides para o GitHub.

Execute as seguintes etapas para instalar e configurar o aplicativo *AEM Code Sync*:

1. Navegue até a página [Sincronização de Código AEM](https://github.com/apps/aem-code-sync) e selecione **Instalar**.
2. A *Sincronização de Código AEM* monitora as alterações no repositório e garante que as atualizações sejam enviadas corretamente para o GitHub.

   >[!NOTE]
   >
   > Ao instalar o aplicativo, certifique-se de usar a mesma conta GitHub que possui o repositório.

   ![](assets/eds-aem-code-sync-page.png){align="left"}
3. Na próxima página, conceda acesso ao repositório criado. Para fazer isso, selecione a opção **Selecionar apenas repositórios** e selecione seu repositório na lista suspensa.

   ![](assets/eds-aem-code-sync-install-authorize.png){width="350" align="left"}
4. Selecione **Instalar e autorizar**.

Você é redirecionado para a página de configuração do GitHub, confirmando o registro bem-sucedido do aplicativo *AEM Code Sync*. Você também pode salvar a Visualização e os URLs em tempo real do seu site nesta página.

![](assets/eds-aem-code-sync-registered.png){align="left"}

### Criar um novo aplicativo GitHub

1. No GitHub, navegue até a barra lateral esquerda e selecione **Configurações do desenvolvedor**.
2. Na barra lateral esquerda, selecione **Aplicativos do GitHub**.
3. Selecione **Novo aplicativo GitHub**.

   ![](assets/eds-new-github-app.png){width="650" align="left"}
4. Na página **Registrar novo aplicativo GitHub**, forneça os seguintes detalhes:
   - **Nome do aplicativo GitHub**: digite um nome para o aplicativo. Por exemplo, `USERNAME-eds-app` onde USERNAME é seu nome de usuário do GitHub.
   - **URL da Página Inicial**: Insira a URL para a instância do Experience Manager Guides.

     Amostra da URL (formato): `https://<aem-author-url>/libs/fmdita/clientlibs/xmleditor/page.html`

     Amostra da URL: `https://author-p16602-e335172-cmstg.adobeaemcloud.com/libs/fmdita/clientlibs/xmleditor/page.html`
   - **URL de retorno**: igual à URL da Página Inicial.
   - **URL do Webhook**: desabilite esta opção.
   - **Permissões do repositório**: Defina **Permissões de Leitura e Gravação** para *Ações, Administração e Atestado*.
5. Selecione **Criar aplicativo GitHub**.

Seu aplicativo está pronto agora. Você é redirecionado para a página **Configurações** do seu aplicativo GitHub.

![](assets/eds-github-app-registered-page.png){align="left"}

### Criar um novo aplicativo OAuth

Um aplicativo OAuth é necessário para autenticar usuários ao criar um perfil de publicação EDS (Beta) no Experience Manager Guides. Habilita um fluxo de logon seguro usando uma *ID de Cliente* e um *Segredo do Cliente*.

Execute as seguintes etapas para criar um novo aplicativo OAuth:

1. No GitHub, navegue até a barra lateral esquerda e selecione **Configurações do desenvolvedor**.
2. Na barra lateral esquerda, selecione **Aplicativos OAuth**.
3. Selecione **Novo aplicativo OAuth**.

   ![](assets/eds-new-oauth-app.png){width="650" align="left"}
4. Registre seu aplicativo fornecendo os seguintes detalhes obrigatórios:
   - **Nome do aplicativo**: insira o nome do seu repositório EDS
   - **URL da Página Inicial**: Insira a URL para a instância do Experience Manager Guides. (Para formato de URL de exemplo, consulte a etapa 4 da seção [Criar um novo Aplicativo GitHub](#create-a-new-github-app)).
   - **URL de retorno de chamada**: Igual à URL da Página Inicial
5. Selecione a opção **Habilitar Fluxo de Dispositivo** e selecione **Registrar aplicativo** para concluir o registro.

   ![](assets/eds-new-github-app-register.png){width="650" align="left"}

Seu aplicativo está pronto agora. Anote a *ID do cliente*. Você pode gerar até cinco *Segredos do Cliente* agora ou posteriormente, ao configurar o perfil de publicação no Experience Manager Guides.

![](assets/eds-new-oauth-app-page.png){align="left"}


### Configurar o URL do ponto de montagem no repositório do EDS (Beta)

O EDS (Beta) lê o conteúdo de um caminho de repositório do GitHub definido como uma URL de *ponto de montagem* no arquivo `fstab.yaml`.

Para configurar a URL do ponto de montagem no arquivo `fstab.yaml`:

1. Abra o arquivo `fstab.yaml` em seu repositório e atualize o seguinte:
   - `your-user-name`
   - `your-repo-name`

   >[!NOTE]
   >
   > Na URL do ponto de montagem, `main` indica a ramificação na qual você deseja publicar o conteúdo e `docs` indica a pasta raiz do repositório EDS (Beta) no qual você está trabalhando. Se preferir alterar o nome da ramificação no GitHub, atualize o mesmo nome de ramificação na URL *mountpoint* (no arquivo `fstab.yaml`) e o perfil de publicação de EDS correspondente no Experience Manager Guides.

   ![](assets/eds-fstab-yaml-file.png){width="650" align="left"}
2. Selecione **Confirmar alterações**, insira os detalhes da confirmação e confirme.
3. Retorne às [Configurações do desenvolvedor](https://github.com/settings/apps), localize seu aplicativo e selecione **Editar**.

   ![](assets/eds-edit-github-app.png){width="650" align="left"}
4. Navegue até a página **Instalar aplicativo** e selecione **Instalar**.

   ![](assets/eds-install-eds-app.png){width="650" align="left"}
5. Repita as etapas 2 e 3 da seção [Conectar o GitHub à Adobe por meio da Sincronização de Código AEM](#connect-github-to-adobe-via-aem-code-sync) para autorizar o repositório.

## Criar e configurar um perfil de publicação para EDS (Beta) no Experience Manager

As seções abaixo descrevem cada etapa em sequência e explicam como configurar o perfil de publicação do EDS (Beta), configurar uma predefinição de saída e gerar saída usando o EDS (Beta) no Experience Manager Guides.

### Criar o perfil de publicação do EDS (Beta)

1. Vá para **[Configurações do Workspace](/help/product-guide/cs-install-guide/workspace-settings.md)** **>** **Publicar perfis**.
2. Selecione o ícone **+** para criar um novo perfil de publicação e fornecer os seguintes detalhes:
   - **Tipo de servidor**: selecione **GitHub Edge Delivery Services (Beta)** na lista suspensa.
   - **Nome**: insira um nome para este perfil.
   - **Nome do repositório**: use o nome do repositório GitHub criado a partir do modelo padrão.
   - **Nome de usuário**: digite seu nome de usuário do GitHub.
   - **Ramificação principal**: definir como principal (padrão).
   - **Pasta raiz**: definir como documentos (padrão).
   - **ID do Cliente e Segredo do Cliente**: busque-os no Aplicativo GitHub (Consulte a seção [Criar um novo Aplicativo OAuth](#create-a-new-oauth-app) para obter detalhes).
3. Selecione **Logon** para autenticar.

   ![](assets/eds-publish-profile.png){width="650" align="left"}
4. Na autenticação bem-sucedida, selecione **Salvar**.

O perfil de publicação de EDS (Beta) agora está configurado.

### Criar uma predefinição de Saída para EDS (Beta) e gerar saída

1. Abra o mapa no console Mapa.
2. Na guia **Predefinições de saída**, selecione **+** para criar uma nova predefinição de saída.
3. Na caixa de diálogo **Nova predefinição de saída**, forneça os seguintes detalhes:
   - **Tipo**: Selecionar **Serviço Edge Delivery (Beta)**
   - **Nome**: forneça um nome para esta predefinição
4. Selecione **Adicionar**.

   ![](assets/eds-output-preset.png){width="650" align="left"}
5. Abra a predefinição de saída do EDS (Beta) recém-criada e navegue até a guia **Config**.
   - Selecione o perfil de publicação criado na etapa anterior.
   - Habilitar **Push para ativação**.

   Quando **Push para live** está habilitado, a saída gerada é confirmada no GitHub, e as atualizações correspondentes são propagadas para o site imediatamente.

   ![](assets/eds-output-preset-config-tab.png){width="650" align="left"}

6. Selecione **Salvar** e depois **Gerar saída**.

>[!NOTE]
>
> A saída gerada é armazenada na pasta **docs** do repositório EDS (Beta).

A saída de EDS (Beta) agora é gerada. O conteúdo é apresentado em um layout limpo e responsivo. Inclui elementos regulares, como o título da página, navegações estruturais, conteúdo do corpo e quaisquer blocos usados no tópico. O índice à esquerda (gerado pelo mapa) ajuda a navegar pelos tópicos, enquanto um mini índice à direita destaca as seções na página atual. A saída inteira responde totalmente, garantindo uma experiência de leitura otimizada e consistente em todos os dispositivos.

![](assets/eds-site-output.png){align="left"}

## Personalizar saída usando blocos EDS

O EDS usa `blocks` para controlar como partes diferentes do conteúdo são estilizadas e exibidas. Você pode modificar blocos existentes ou criar blocos personalizados.

Os exemplos descritos abaixo orientam você na personalização de um bloco existente e na criação de um novo bloco para estilizar a saída final do EDS (Beta) no Experience Manager Guides.

### Personalizar um bloco de navegação estrutural para atualizar a cor do texto

As navegações estruturais são usadas em páginas para ajudar os usuários a entender onde eles estão na documentação. Como esse bloco aparece de forma consistente em todo o site, a atualização de seu estilo permite uma atualização de design unificada.

Execute as seguintes etapas para personalizar um bloco de navegação estrutural para atualizar sua cor de texto:

1. Vá para o repositório do GitHub e abra a pasta `blocks`.
2. Selecione o bloco **navegações estruturais**.

   ![](assets/eds-breadcrumbs.png){width="650" align="left"}
3. Abra o arquivo `css` e atualize a cor do texto.
4. Confirme as alterações no GitHub.
5. Atualize o site para ver as atualizações.

### Atualizar scripts EDS (Beta) para criar elemento personalizado na saída publicada

Em alguns casos, convém estilizar apenas uma parte específica do conteúdo. Execute as seguintes etapas para fazer isso usando um bloco personalizado.

1. Abra o arquivo de tópico e selecione o texto dentro de um elemento de tag.

   Na captura de tela a seguir, o conteúdo dentro da tag `example` é selecionado.
   ![](assets/eds-example-tag-org-output.png){width="650" align="left"}
2. Para configurar o texto dentro da tag `example`:
   - Navegue até **Propriedades do conteúdo**.
   - Adicione o atributo `outputclass`.
   - Defina o valor como `example eds-force-block`.
   - Selecione **Adicionar**.
     ![](assets/eds-example-tag.png){width="650" align="left"}
3. Salve e gere novamente a saída.
4. Crie uma nova pasta com o mesmo nome que `outputclass` dentro do diretório `blocks`. Saiba mais sobre [adicionando arquivos a um repositório](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository#adding-a-file-to-a-repository-using-the-command-line).

   ![](assets/eds-example-folder.png){width="650" align="left"}
5. Adicione os arquivos `css` necessários e `js` opcionais.

   ![](assets/eds-example-folder-subfolders.png){width="650" align="left"}
6. Confirme as alterações e gere novamente a saída.

O conteúdo selecionado agora exibe o estilo personalizado definido no bloco.

![](assets/eds-example-output.png){width="650" align="left"}