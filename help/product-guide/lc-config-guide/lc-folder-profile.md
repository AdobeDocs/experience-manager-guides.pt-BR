---
title: Configurar perfis de pasta
description: Saiba como configurar perfis de pastas ao trabalhar com o conteúdo de Aprendizado e treinamento no Experience Manager Guides.
feature: Authoring
role: Admin
level: Experienced
exl-id: dc26ae48-c953-492c-823a-5f65157b6902
source-git-commit: 64adc89966e60823f6b46fb062b7659ed150cfc3
workflow-type: tm+mt
source-wordcount: '1453'
ht-degree: 0%

---

# Configurar perfis de pasta

É necessário um perfil de pasta para separar as configurações de diferentes departamentos ou produtos em sua empresa. Para conteúdo de aprendizado e treinamento, você pode criar e configurar um perfil no nível da pasta para gerenciar modelos de criação, modelos de saída, predefinições de saída e outras configurações no nível da pasta.

Saiba mais sobre [Práticas recomendadas para configurar a estrutura de pastas](best-practices-folder-structure.md).

Para começar a usar a configuração do perfil de pasta para o conteúdo de Aprendizado e Treinamento, é necessário:

1. **Crie pastas diferentes para gerenciar modelos de criação e saída**: você pode criar pastas para Autores e Editores que trabalham em diferentes departamentos ou produtos da sua empresa. Essas pastas podem ser mapeadas para perfis de pastas específicos, cada um configurado com diferentes modelos de criação e saída para suportar a criação de cursos de aprendizado específicos do departamento e a administração descentralizada.

   Você pode criar uma nova pasta no painel Repositório.

   ![](assets/create-new-folder.png){width="350" align="left"}
2. **Criar pastas de idioma para gerenciar a tradução**: se você traduzir conteúdo em idiomas diferentes, deverá criar pastas correspondentes a cada idioma. Cada uma dessas pastas de idioma conterá o conteúdo correspondente a esse idioma.

3. **Criar uma pasta para gerenciar o Assets**: assim como as pastas, você também pode criar diferentes pastas do Assets para atender às necessidades de diferentes departamentos. Dessa forma, você também garante que Autores e Editores tenham acesso ao CSS correto configurado em seus modelos, imagens e outros ativos.

   ![](assets/configure-assets-folder.png){width="350" align="left"}
4. [Crie um perfil de pasta](../cs-install-guide/conf-folder-level.md#create-and-configure-a-folder-level-profile) para mapear pastas diferentes.
5. **Selecione o perfil de pasta a ser configurado**: depois que o perfil de pasta for criado, você precisará selecionar o perfil de Pasta na página [Preferências do Usuário](../user-guide/intro-home-page.md#user-preferences) para garantir que os Autores e Publicadores tenham acesso aos modelos corretos.

   ![](assets/folder-profile.png){width="650" align="left"}

6. **Definir configurações do perfil da pasta**: para conteúdo de Aprendizado e Treinamento, as seguintes configurações podem ser definidas no nível da pasta:
   - [Painéis](#configure-panels)
   - [Modelos](#configure-templates)
   - [Predefinições de saída](#configure-output-presets)
   - [editor do HTML](#html-editor-settings)
   - [Publicar perfis](#manage-publish-profiles)

Para acessar essas configurações, alterne para o modo de exibição Editor e selecione **Configurações** no menu **Opções**, conforme mostrado abaixo:

![](assets/access-editor-settings.png)

## Configurar painéis

Esta configuração controla os painéis que são mostrados nos painéis esquerdo e direito do **Editor** e do **Console de mapas** no Experience Manager Guides. Você pode alternar o botão para mostrar ou ocultar o painel desejado.

Para o conteúdo de aprendizado e treinamento, verifique se apenas os seguintes recursos estão ativados para o editor e o console de mapa.

![](assets/panels-settings.png){width="350" align="left"}


### Editor

**Painel esquerdo**

- **Coleções**: permite que você organize e salve arquivos usados com frequência ou acesse rapidamente arquivos compartilhados.
- **Repositório**: permite que você visualize e acesse todos os seus mapas, tópicos, imagens e outros ativos armazenados no repositório de conteúdo.
- **Gerenciador de cursos**: fornece um espaço de trabalho dedicado para a criação e o gerenciamento de cursos.
- **Fragmentos**: permite criar e reutilizar pequenos fragmentos de conteúdo em vários tópicos em seus cursos de aprendizado.
- **Condições**: permite configurar atributos condicionais em nível global e de pasta.
- **Variáveis**: permite criar e gerenciar variáveis para usar no conteúdo de aprendizado.
- **Variáveis de idioma**: permite definir cadeias de caracteres localizadas para saída publicada ou texto estático em modelos.
- **Modelos**: permite que você crie e gerencie modelos para serem usados pelos Autores.
- **Modelos de saída**: permite que você crie e gerencie modelos de saída para gerar saída em vários formatos.
- **Localizar e substituir**: fornece opções para procurar e substituir texto entre arquivos em um mapa ou uma pasta no seu repositório. 

**Painel direito**

- **Propriedades de conteúdo**: contém informações sobre o tipo e os atributos do elemento atualmente selecionado no Editor.
- **Propriedades do arquivo**: permite que você exiba e gerencie as propriedades do arquivo selecionado.
- **Estilos**: exiba as opções de estilo globais baseadas em classe para uso no seu conteúdo de aprendizado.
- **Filtros**: permite que você filtre o conteúdo com base nas condições aplicadas no modo de Visualização de um tópico.

### Mapear console

**Painel esquerdo**

- **Predefinições**: permite configurar as predefinições de saída para publicar o curso de aprendizado.
- **Tradução**: fornece opções para traduzir o conteúdo para vários idiomas.
- **Relatórios**: permite gerar e gerenciar relatórios para obter uma insight útil sobre a integridade geral do conteúdo do seu curso.
- **Predefinições de condição**: fornece opções para configurar predefinições de saída baseadas em condição para públicos-alvo, departamentos e muito mais.

**Painel direito**

- **Filtros**: permite que você use filtros ao trabalhar com relatórios e tradução.

## Configurar modelos

Essa configuração permite gerenciar os modelos de criação e publicação presentes no [painel esquerdo do Editor](../user-guide/web-editor-left-panel.md). É possível adicionar, remover ou reordenar modelos de criação e saída, que estarão acessíveis a Autores e Editores.

![](assets/templates-settings.png){width="350" align="left"}

Os modelos de Criação estão disponíveis em quatro categorias - Curso de aprendizado, Conteúdo de aprendizado, Questionário e Banco de perguntas. Se houver modelos predefinidos configurados na instância, eles serão exibidos por padrão.

![](assets/templates-list.png){width="350" align="left"}

### Adicionar modelos

Execute as seguintes etapas para adicionar um novo modelo:

1. Navegue até a categoria de modelo à qual deseja adicionar um modelo e selecione **Adicionar**.
2. Na caixa de diálogo Selecionar caminho, selecione o modelo desejado.
3. Escolha **Selecionar**.

   ![](assets/add-templates.png){width="350" align="left"}

O modelo é adicionado à respectiva categoria no painel Configurações.

Da mesma forma, é possível adicionar os outros templates de Criação e Saída. Depois de adicionados, esses modelos são disponibilizados para Autores e Editores nas respectivas caixas de diálogo do curso. Por exemplo, o modelo de curso de aprendizado adicionado pelo administrador estará disponível aos autores quando eles criarem um novo curso.

![](assets/templates-added-course.png){width="350" align="left"}

### Trabalhar com novos modelos de criação e saída

Para usar um modelo diferente daqueles mostrados na caixa de diálogo **Selecionar caminho**, crie um modelo de criação ou saída personalizado.

**Criar novos modelos de criação**

Para usar um modelo de mapa ou tópico diferente, crie um novo modelo de criação no painel Modelos no Editor. Use modelos de mapa para criar cursos de aprendizado e modelos de tópico para conteúdo de aprendizado, questionário ou resumo de aprendizado.

Para obter detalhes, consulte [Criar modelos personalizados no Editor](../user-guide/create-maps-customized-templates.md).

![](assets/authoring-templates-editor.png){width="350" align="left"}

**Criar novos modelos de saída**

Execute as seguintes etapas para criar um novo modelo de saída para o conteúdo de aprendizado e treinamento:

1. No painel esquerdo no Editor, selecione **Mais** > **Modelos de saída**.

   O painel Modelos de saída é exibido.

   ![](assets/output-templates-editor.png){width="350" height="" align="left"}
2. No painel Modelos de saída, selecione (+) para criar um novo modelo de saída.

   ![](assets/create-new-output-template.png){width="350" align="left"}
3. Selecione um Modelo de saída no menu suspenso.


   ![](assets/output-template-types.png){width="650" align="left"}
4. Com base no tipo de modelo de saída selecionado, uma caixa de diálogo é exibida onde você pode criar um novo modelo com base nos modelos disponíveis.

   ![](assets/new-scorm-template-dialog.png){width="350" align="left"}

5. Selecione **Criar**.

   Um novo Modelo de saída é criado.

6. Para acessar e adicionar o Modelo de saída para editores, navegue até **Configurações** > **Modelos** > **Modelos de saída** e selecione **Adicionar**.

   ![](assets/add-output-template-settings-panel.png){width="350" align="left"}

   O modelo de saída é exibido na caixa de diálogo Selecionar caminho.
7. Selecione o modelo e escolha **Confirmar**.

   ![](assets/select-scorm-template-dialog.png){width="350" align="left"}

   O modelo de saída selecionado agora é adicionado ao painel Configurações.

   ![](assets/scorm-template-added.png){width="350" align="left"}

### Remover ou reordenar modelos

Depois de adicionado, é possível remover ou reordenar os modelos no painel Configurações.

Para remover um modelo, selecione o ícone **Remover** ao lado dele.

![](assets/remove-teamplates.png){width="350" align="left"}

Você também pode definir a ordem em que os modelos presentes em uma categoria são exibidos. Para alterar a ordem de exibição dos modelos, selecione as barras pontilhadas e arraste um modelo para a posição desejada.

![](assets/reorder-templates.png){width="350" align="left"}


## Configurar predefinições de saída

A guia Output presets permite definir quais formatos de saída estão disponíveis para publicar um curso. Ele contém duas seções: **Tipos de predefinição de saída permitidos** e **Predefinições de saída comuns**.

![](assets/configure-course-output-presets.png){width="350" align="left"}

- **Tipos de predefinição de saída permitidos**: esta seção lista todas as predefinições de saída com suporte na instância do Experience Manager Guides. Para publicação do curso, somente os formatos **SCORM** e **PDF** são aplicáveis. É possível selecionar uma ou ambas as opções. As predefinições selecionadas estarão disponíveis para os editores ao gerar a saída do curso.

  ![](assets/allowed-output-presets.png){width="350" align="left"}

- **Predefinições de saída comuns**: esta seção exibe as predefinições de saída criadas e adicionadas com frequência pelos Publicadores a um perfil de pasta específico. Também é possível remover qualquer predefinição que não seja mais necessária.

  ![](assets/common-output-presets.png){width="350" align="left"}

## Configurações do editor do HTML

Essa configuração permite configurar o Editor para criação baseada em HTML. As principais opções de configuração presentes nessa configuração são as seguintes:

![](assets/configure-html-editor-setting.png){width="350" align="left"}

- **Ocultar estilo em linha**: habilite esta opção para impedir que os autores apliquem formatação em linha ao conteúdo do curso. Quando ativado, todas as opções de estilo em linha, como Fontes, Borda, Layout, Plano de fundo e Colunas presentes no painel direito do Editor permanecem ocultas para Autores. No entanto, os Autores ainda podem usar as opções de estilo baseadas em classe global disponíveis no painel **Estilos**. Isso ajuda a manter a consistência com as diretrizes de estilo de sua organização.
- **Ocultar o modo de exibição do Source para Autores**: habilite essa opção para restringir o acesso ao código-fonte do HTML. Isso é útil quando você deseja simplificar a experiência de edição ou evitar alterações acidentais no código subjacente.

## Gerenciar perfis de publicação

Esta seção permite exibir, criar e gerenciar os perfis de publicação usados para publicar cursos na Nuvem SCORM. Cada perfil define as configurações de conexão e os detalhes de configuração necessários para publicar um curso de aprendizado em um ambiente específico da SCORM Cloud.

É possível criar vários perfis se você precisar publicar em diferentes contas do SCORM Cloud, garantindo flexibilidade e controle sobre o processo de publicação.

Forneça os detalhes do servidor, juntamente com a ID do cliente e o segredo do cliente do aplicativo de nuvem SCORM associado, para configurar o perfil de publicação para a nuvem SCORM.

![](assets/configure-publish-profiles.png){width="350" align="left"}
