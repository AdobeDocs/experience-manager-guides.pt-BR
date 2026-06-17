---
title: Usar nova coleção de mapas para geração de saída
description: Saiba como criar e excluir uma nova coleção de mapas e adicionar ou excluir um mapa DITA. Configure, gere e cancele uma tarefa de geração de saída de uma coleção de mapas no AEM Guides.
feature: Publishing
role: User
TQID: https://experienceleague.adobe.com/4ZtP8sNNhuZwJ-bTKThXiRZwVXvJ2PvfKyyo91HO1bE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: f7c0b10f032c2584fb6e951da898faaeb4ca7aaf
workflow-type: tm+mt
source-wordcount: 1447
ht-degree: 0%

---

# Usar nova coleção de mapas para geração de saída (Beta)

>[!IMPORTANT]
>
> A nova coleção de mapas está disponível no Experience Manager Guides as a Cloud Service a partir da versão 2026.06.0. Entre em contato com a equipe de Sucesso do cliente para habilitar esse recurso.

A coleção de mapas no Adobe Experience Manager Guides permite que os especialistas de publicação organizem vários documentos em uma única coleção, controlem a saída gerada para cada documento e gerem e publiquem saídas em lotes com eficiência, a partir de um painel centralizado. Ele também oferece visibilidade do progresso da geração de saída, destaca as alterações feitas nos mapas desde a última saída publicada e permite republicar o conteúdo quando necessário.

A Nova coleção de mapas consolida a funcionalidade anteriormente distribuída pela antiga coleção de mapas e a publicação em massa em uma única interface unificada. Após a ativação, é possível gerenciar mapas, predefinições, histórico de geração, histórico de publicação, metadados e associação à coleção de um único local.

## Criar uma coleção de mapas e adicionar mapas DITA

Para criar uma coleção de mapas e adicionar mapas a ela, execute as seguintes etapas:

1. Abra a página inicial do Experience Manager Guides e selecione **Novas coleções de mapas**.

   A página **Mapear coleções** é aberta.

   ![](images/new-maps-collection.png){width="650"}


1. Na página **Coleções de mapas**, selecione **Criar** no canto superior direito e forneça um **Nome** para sua nova coleção de mapas.

   ![](images/create-new-map-collection.png){width="350"}

1. Selecione **Criar**.

   Uma mensagem de sucesso é exibida na criação da coleção de mapas.

1. Abra a coleção de mapas desejada à qual deseja adicionar os mapas.

   ![Editar nova coleção de mapas](./images/edit-new-map-collection.png)

   Ao passar o mouse sobre o título da coleção de mapas, você pode executar as seguintes ações:

   - **Gerar histórico**: Navega diretamente para a guia Histórico gerado listando todos os mapas com saídas geradas para as predefinições definidas.
   - **Publicar histórico**: Navega diretamente para a guia Histórico publicado, listando todos os mapas com saída publicada para as predefinições definidas.
   - **Renomear**: renomeia a coleção de mapas.

1. Selecione **Editar coleção** e **Adicionar mapas**.

   ![Adicionar mapas](./images/add-maps-new-collection.png)

1. Selecione os mapas desejados e habilite o botão de alternância **Selecionar traduções disponíveis** para adicionar automaticamente todas as cópias de tradução disponíveis desse mapa à coleção de mapas. Se o mapa não tiver cópias de tradução, o idioma padrão será adicionado ao mapa.

   ![Selecionar mapas](./images/select-maps-new-collection.png)

1. Selecione **Adicionar**.

   Os arquivos de mapa são listados junto com todas as cópias traduzidas disponíveis. Para mapas que não têm cópias traduzidas, o idioma padrão é exibido.

   ![Buscar predefinições](./images/fetch-presets.png)

1. Selecione os mapas necessários ou todos os mapas listados e, em seguida, selecione o botão **Buscar predefinições** para recuperar as predefinições disponíveis para os mapas selecionados.

   Você verá uma lista de todas as predefinições disponíveis para os mapas selecionados, agrupadas em duas categorias: **Predefinições de perfil de pasta** e **Outras predefinições**. **As predefinições de perfil de pasta** são comuns a todos os mapas selecionados, enquanto **Outras predefinições** são específicas de mapas individuais. Para predefinições em **Outras predefinições**, o mapa associado é indicado ao lado do botão de alternância correspondente.

   ![Buscar tipos de predefinições](./images/fetch-presets-types.png)

1. Selecione **Habilitar todas as predefinições** ou **Habilitar todas as predefinições de perfil de pasta**, dependendo da sua necessidade. Também é possível usar o ícone Filter à direita para restringir a lista. O filtro fornece dois níveis de filtragem: **Tipos de predefinição** para restringir as predefinições listadas e **Status do mapa** para escolher mapas específicos no painel Mapas.

   ![Habilitar todas as predefinições](./images/enable-all-presets.png)

1. Selecione **Salvar**.

Você obtém uma lista de todos os mapas desejados com o Título do mapa, o Nome do arquivo correspondente, o Idioma em que está disponível e as predefinições configuradas.

![Guias de mapas e predefinições](./images/maps-presets-tab.png)

A guia **Mapas e Predefinições** apresenta informações com base nos mapas selecionados para um idioma específico nas seguintes colunas:

- **Predefinição**: mostra o tipo de predefinição de saída configurado no arquivo de mapa.
- **Linha de Base**: mostra a linha de base que é usada pela predefinição de saída.  Se nenhuma linha de base for usada, ela mostrará um hífen `-`.
- **Modificado desde a geração**: indica se o mapa DITA é atualizado após a geração. Com base nessas informações, você pode decidir se deseja publicar a saída desse mapa DITA ou não.
- **Modificado desde a publicação**: indica se o mapa DITA é atualizado após a última publicação. Com base nessas informações, você pode decidir se deseja republicar a saída desse mapa DITA ou não.
- **Última geração**: mostra a data e a hora da última saída gerada.
- **Última publicação**: mostra a data e a hora da última saída publicada.

**Opções de filtragem**

As seguintes opções de filtro estão disponíveis no painel direito da página Mapas e predefinições:

- **Modificado desde a geração**: você pode selecionar Sim, Não ou Ainda não gerado. Se você selecionar Sim, somente os mapas que foram modificados desde a geração serão exibidos na guia Mapas e Predefinições.
- **Modificado desde a publicação**: você pode selecionar Sim, Não ou Ainda não gerado. Se você selecionar Sim, somente os mapas que foram modificados desde a publicação serão exibidos na guia Mapas e predefinições.
- **Predefinições**: selecione uma predefinição para a qual deseja filtrar os arquivos de mapa. Por exemplo, se você escolher a predefinição *Site do AEM*, serão exibidos apenas os mapas que tiverem a predefinição de saída *Site do AEM* configurada.
- **Idioma**: você pode selecionar qualquer um dos códigos de idioma disponíveis e exibir somente o idioma selecionado na guia Mapas e Predefinições.

  ![Filtros em guias de mapas e predefinições](./images/filters-maps-presets.png)


## Gerar a saída usando uma coleção de mapas

Para gerar a saída usando uma Coleção de Mapas, execute as seguintes etapas:

1. Abra a Coleção de mapas. É possível visualizar as várias predefinições de saída, como AEM Sites, PDF (incluindo PDF nativo), HTML5, EPUB e predefinições personalizadas, de acordo com sua configuração.

1. Para gerar a saída dos mapas selecionados, selecione os arquivos de mapa necessários e as predefinições específicas e selecione **Gerar**.

   >[!IMPORTANT]
   >
   > Se um processo de geração de saída para uma predefinição ou um mapa DITA estiver na fila ou em andamento, não será possível iniciar outra tarefa de geração de saída para a mesma predefinição ou mapa.


1. Depois que a saída for gerada, navegue até a guia **Histórico gerado** para exibir a lista de todos os mapas gerados. Você pode acompanhar o progresso da geração na coluna **Status**, que indica se uma geração está em Execução ou Concluída.


   ![Status da geração](./images/generated-tab-status.png)

1. Selecione **Atualizar** para exibir o status mais recente do processo de geração. A coluna Status é atualizada para refletir o estado atual de cada mapa e suas predefinições associadas:

   - **Concluído (Verde)**: geração concluída com êxito.
   - **Concluído (Vermelho)**: geração concluída com erros. Os detalhes do erro podem ser exibidos nos logs.
   - **Em execução (Azul)**: a geração está em andamento.

   ![Tipos de status](./images/status-types.png)

1. Você também pode cancelar a tarefa de geração de saída até que o status da tarefa seja executado selecionando o ícone **Cancelar geração**.

   ![geração de campanha](./images/cancel-generation.png)


1. Além disso, você pode exibir a saída gerada para mapas cuja geração de saída foi concluída selecionando o ícone **Abrir Saída** que aparece ao passar o mouse sobre o nome do mapa ou exibir os logs de geração selecionando o ícone adjacente **Logs**.

   ![ícones](./images/hovering-icon.png)


## Publicar a saída usando uma coleção de mapas

Para publicar (se configurada) a saída usando uma Coleção de mapas, execute as seguintes etapas:

1. Selecione os mapas desejados na guia **Mapas e Predefinições** ou na guia **Histórico gerado** e selecione **Publicar em**.
1. Selecione o ambiente de destino no qual você deseja publicar a saída: **Visualizar** ou **Publicar** instância.

   ![Publicar saída](./images/publish-output.png)

1. Alterne para a guia **Histórico publicado** para monitorar o status da tarefa de publicação.

   ![Publicar status](./images/publish-status.png)

1. Selecione **Atualizar** para exibir o status mais recente da tarefa.
1. Depois que o status for alterado para **Successful**, verifique o conteúdo publicado na instância de destino selecionada.


## Configurar as propriedades dos metadados

Na coleção de mapas, é possível configurar as propriedades de metadados em massa para os mapas DITA. Selecione o ícone **Configurar Metadados** na guia **Mapas e predefinições** para abrir a página **Metadados de ativos**. Na página **Metadados de ativos**, todos os mapas presentes na coleção são listados à esquerda.

![configurar metadados](images/map-collection-asset-metadata.png)

Execute as seguintes etapas para configurar as propriedades de metadados:

1. Você pode escolher os mapas para os quais deseja atualizar os metadados. Por padrão, todos os mapas DITA presentes são selecionados.

1. Depois de selecionar os mapas DITA, você pode visualizar propriedades como metadados, agendar (des)ativação, referências, estado do documento e muito mais.

1. Atualize as propriedades dos metadados.

1. Selecione **Salvar e fechar** na parte superior para salvar as atualizações.
1. (Opcional) Ao atualizar as tags, você também pode selecionar Anexar na lista suspensa **Salvar e fechar** para anexar as novas tags à lista existente.
1. Selecione **Enviar** na lista suspensa **Salvar e fechar**.
As propriedades de metadados são atualizadas em massa para os mapas DITA selecionados na coleção de mapas.

>[!NOTE]
> 
>Na lista suspensa **Estado do documento**, você pode selecionar apenas os estados do documento permitidos em comum para todos os mapas DITA selecionados. Para saber mais, exiba [**Estado do Documento**](./web-editor-document-states.md).

As propriedades de metadados estão sincronizadas com as propriedades do arquivo. Depois de atualizá-los, você poderá exibi-los no painel **Propriedades do arquivo** do Editor.


**Tópico pai:**&#x200B;[&#x200B; Geração de saída](generate-output.md)
