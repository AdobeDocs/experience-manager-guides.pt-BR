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
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '484'
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

Você pode ativar ou desativar as seguintes opções com base nas suas preferências:

![Configurações do editor](./images/editor-settings-dialog.png){width="350"}

- **Espaços não separáveis**: habilite esta opção para mostrar um indicador para os espaços não separáveis ao editá-lo no Editor. É visível somente na exibição Autor para o tópico DITA e mapas DITA
- **Comentários XML**: permite que os autores exibam, editem e insiram comentários XML diretamente no modo Autor, para melhor visibilidade do conteúdo. Quando ativados, os autores podem exibir, inserir, editar e excluir comentários XML diretamente no conteúdo no próprio modo Autor, facilitando a adição de notas contextuais para colaboradores. Quando desativados, os comentários XML ficam ocultos no modo Autor e não podem ser inseridos ou modificados nesse modo, garantindo uma experiência de criação mais limpa para os usuários que não precisam deles. Você pode continuar a exibir e criar comentários XML no modo de origem usando a sintaxe `<!-- test comment -->`.

  ![Configurar comentários XML](./images/config-xml-comments.png){width="650"}

- **Marcas**: controla a visibilidade das marcas no Editor. Quando ativadas, as tags estruturais são exibidas no conteúdo, permitindo que os autores visualizem e gerenciem a estrutura DITA subjacente. Quando desativadas, essas tags ficam ocultas para fornecer uma experiência de criação mais limpa e focada.

  ![Marcas de configuração](./images/config-tags.png){width="650"}

  Quando as configurações de **Mostrar marcas** estão habilitadas, você também pode habilitar **Exibir atributos** para exibir e validar os atributos associados a um elemento. Quando um elemento tiver mais de três atributos associados a ele, um indicador de contagem será exibido. Passar o mouse sobre o indicador exibe a lista completa de atributos aplicados a esse elemento.

  ![Configurar marcas com atributos](./images/config-tags-attributes.png) {width="650"}

- **Menu de inserção rápida no editor**: permite adicionar elementos diretamente ao editar no modo Autor, na posição do cursor, sem navegar até a barra de ferramentas. Os elementos usados com frequência também podem ser configurados em **Favoritos** para agilizar o acesso. O menu de inserção rápida está disponível diretamente no Editor quando você pressiona **Control + /** no Windows ou **Command + /** no macOS na posição do cursor.

  ![Menu de inserção rápida no editor](./images/quick-insert-menu-in-editor.png){width="650"}

  Você pode pesquisar e adicionar elementos aos seus Favoritos, remover os elementos adicionados anteriormente e reorganizá-los usando o simples arrastar e soltar. Os favoritos incluem os elementos usados com mais frequência e a ordem definida aqui é refletida no menu Inserção rápida quando acessado do editor.

  Este é um vídeo curto sobre como trabalhar com o menu de Inserção rápida no Novo editor.

  >[!VIDEO](https://video.tv.adobe.com/v/3491343)


