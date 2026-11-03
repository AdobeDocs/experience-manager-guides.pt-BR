---
title: Configurações do editor
description: Saiba como definir as configurações do Editor no AEM Guides.
feature: Web Editor
role: User
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 43e3af5a6d753e6124acf1d56e99497f6b9c4cd9
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 0%
---
# Configurações do editor

>[!NOTE]
>
> Este artigo se aplica somente ao Novo editor. Para ativar esse recurso em seu ambiente, entre em contato com a equipe de Sucesso do cliente da AEM Guides.

As configurações do Editor fornecem um painel de configuração centralizado que permite personalizar o comportamento do Editor em um nível de autor individual. Ele oferece maior flexibilidade, consistência e controle durante o processo de criação.

Esse painel de configurações centralizado permite gerenciar as principais preferências do Editor de um único local, reduzindo a necessidade de configurações dispersas ou manuais. As configurações do Editor podem ser acessadas de **Mais ações** na barra de guias.

![Configurações do editor](./images/conf-editor-settings.png){width="650"}

## Opções de configuração compatíveis

As configurações do editor permitem personalizar várias opções, incluindo Controlar alterações, Mostrar tags, Menu de inserção rápida e muito mais, de acordo com suas preferências.

![Configurações do editor](./images/editor-settings-dialog.png){width="350"}

### Rastrear alterações

>[!NOTE]
>
>- Esse recurso é ativado por padrão. Para desativá-lo, entre em contato com a equipe de Sucesso do cliente da AEM Guides.
>- Ao trabalhar com tabelas, a inserção de uma linha ou coluna é acompanhada, mas a exclusão de uma linha ou coluna não é acompanhada no painel Controlar alterações.

Habilite o modo **Controlar alterações** para registrar as edições feitas em um tópico. Uma vez habilitado, cada inserção e exclusão é capturada enquanto você trabalha, e todas as alterações são listadas no painel **Controlar alterações**. Edições consecutivas feitas na mesma posição são agrupadas e exibidas como uma única alteração no painel **Controlar alterações**.

O conteúdo excluído aparece com tachado, enquanto o conteúdo inserido aparece no texto verde. Além disso, as barras de alteração aparecem ao longo da borda da página de tópico, com barras vermelhas indicando o conteúdo excluído e barras verdes indicando o conteúdo adicionado. Se uma linha contiver adições e deleções, ambas as barras de alteração serão exibidas.

Quando vários usuários trabalham no mesmo tópico, o Rastrear alterações permite que visualizem as edições de cada um. Quando o conteúdo estiver pronto para ser finalizado, os usuários poderão revisar as alterações controladas e aceitá-las ou rejeitá-las.

![Configurações do editor](./images/track-changes-all.png){width="350"}

**Mostrar exclusões controladas embutidas**

Controla como o conteúdo excluído é exibido no Editor enquanto a opção Rastrear alterações está ativada. Quando ativado, o conteúdo excluído permanece visível em linha, em sua posição original, como texto tachado. Quando desativado, o conteúdo excluído não é exibido. Em vez disso, um ícone de lápis é exibido no local onde o conteúdo foi removido, fornecendo uma visualização mais clara do tópico. Selecione o ícone de lápis para ir para o conteúdo excluído correspondente no painel Alterações controladas.

![As configurações do editor controlam as alterações](./images/deletion-inline-off.png){width="350"}

**Aceitar ou rejeitar alterações controladas**

Para revisar as alterações, selecione o ícone **Controlar alterações** no painel direito para abrir o painel Alterações controladas e execute as seguintes etapas:

1. Selecione uma alteração controlada no painel. O conteúdo alterado é selecionado no documento.
1. Aceite a alteração selecionando o ícone **Aceitar alteração** ou rejeite-a selecionando o ícone **Rejeitar alteração**.

   ![Painel de alterações controladas](./images/track-changes-individual.png){width="650"}

1. Para aceitar ou rejeitar todas as alterações com um único clique, selecione **Aceitar todas as alterações** ou **Rejeitar todas as alterações** na parte superior do painel.

   ![Painel de alterações controladas](./images/track-changes-all-comment.png){width="650"}


### Espaços não separáveis

Habilite esta opção para mostrar um indicador para os espaços não separáveis ao editá-lo no Editor. É visível somente na exibição Autor para o tópico DITA e mapas DITA.

### Comentários XML

Permite que os autores visualizem, editem e insiram comentários XML diretamente no modo Autor, para melhorar a visibilidade do conteúdo. Quando ativados, os autores podem exibir, inserir, editar e excluir comentários XML diretamente no conteúdo no próprio modo Autor, facilitando a adição de notas contextuais para colaboradores. Quando desativados, os comentários XML ficam ocultos no modo Autor e não podem ser inseridos ou modificados nesse modo, garantindo uma experiência de criação mais limpa para os usuários que não precisam deles. Você pode continuar a exibir e criar comentários XML no modo de origem usando a sintaxe `<!-- test comment -->`.

>[!NOTE]
>
> Para comentários XML, **Controlar alterações** registra somente a inserção ou exclusão do comentário inteiro. As edições feitas em um comentário XML existente não são registradas.

![Configurar comentários XML](./images/config-xml-comments.png){width="650"}

### Tags

Controla a visibilidade das tags no Editor. Quando ativadas, as tags estruturais são exibidas no conteúdo, permitindo que os autores visualizem e gerenciem a estrutura DITA subjacente. Quando desativadas, essas tags ficam ocultas para fornecer uma experiência de criação mais limpa e focada.

![Marcas de configuração](./images/config-tags.png){width="650"}

Quando as configurações de **Mostrar marcas** estão habilitadas, você também pode habilitar **Exibir atributos** para exibir e validar os atributos associados a um elemento. Quando um elemento tiver mais de três atributos associados a ele, um indicador de contagem será exibido. Passar o mouse sobre o indicador exibe a lista completa de atributos aplicados a esse elemento.

    ![Marcas de configuração com atributos](./images/config-tags-attributes.png) {width=&quot;650&quot;}

### Menu de inserção rápida no editor

Permite adicionar elementos diretamente durante a edição no modo Autor, na posição do cursor, sem navegar até a barra de ferramentas. Os elementos usados com frequência também podem ser configurados em **Favoritos** para agilizar o acesso. O menu de inserção rápida está disponível diretamente no Editor quando você pressiona **Control + /** no Windows ou **Command + /** no macOS na posição do cursor.

![Menu de inserção rápida no editor](./images/quick-insert-menu-in-editor.png){width="650"}

Você pode pesquisar e adicionar elementos aos seus Favoritos, remover os elementos adicionados anteriormente e reorganizá-los usando o simples arrastar e soltar. Os favoritos incluem os elementos usados com mais frequência e a ordem definida aqui é refletida no menu Inserção rápida quando acessado do editor.

Este é um vídeo curto sobre como trabalhar com o menu de Inserção rápida no Novo editor.

>[!VIDEO](https://video.tv.adobe.com/v/3491343)


