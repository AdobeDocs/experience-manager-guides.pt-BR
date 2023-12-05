---
title: Usar coleção de mapas para geração de saída
description: Saiba como criar e excluir uma coleção de mapas e adicionar ou excluir um mapa DITA. Configure, gere e cancele uma tarefa de geração de saída de uma coleção de mapas nos Guias AEM.
exl-id: 41152fa4-f739-44d2-9ccd-74072f53e31b
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 1%

---

# Usar coleção de mapas para geração de saída {#id1723F20G0HS}

Em qualquer organização, um produto pode ter vários tipos de documentação. Como um especialista em publicação, você gostaria de controlar qual saída deseja gerar para qual documento. Além disso, deve haver uma maneira de publicar vários documentos em lote com um único clique.

Os Guias do AEM oferecem a capacidade de organizar o conteúdo para publicação usando um painel chamado Coleção de mapas. Uma Coleção de Mapas permite reunir todos os diferentes tipos de documentos em uma única unidade. Você pode escolher o tipo de saída que deseja gerar para cada documento na Coleção de mapas. Além disso, também é possível gerar saída e ver o progresso da geração de saída no painel de publicação.

A Coleção de mapas oferece uma opção para visualizar se há alguma alteração em qualquer mapa desde a última saída publicada. É possível exibir os detalhes na guia Mapas e predefinições da Coleção de mapas e, em seguida, republicar a saída, se necessário. Para obter mais informações, consulte Adição de um mapa a uma coleção de mapas.

## Criar uma coleção de mapas e adicionar mapas DITA

Para criar uma Coleção de mapas e adicionar mapas DITA à coleção, execute as seguintes etapas:

1. Na interface do usuário do Assets, clique em **Mapear coleções**.

   Se o link Mapear Coleções não estiver disponível, selecione o **Navegação** no painel esquerdo e, em seguida, clique em **Mapear coleções**.

   ![](images/access-map-collection-left-rail.png){width="350" align="left"}

1. Insira um Título para sua coleção de mapas.
1. Clique em **Criar**.

   Uma mensagem de Sucesso é exibida ao criar a coleção de mapas.

1. Clique em **Fechar** na mensagem Success (Êxito).

   O arquivo de mapa recém-criado é mostrado na página Coleções de mapas.

1. Clique na caixa cinza no bloco da coleção que deseja editar.
1. Clique em **Editar** e clique em **Adicionar mapas**.
1. Localize e adicione os mapas DITA que deseja adicionar à Coleção de mapas.

   Por padrão, todas as predefinições e localidades associadas ao mapa são adicionadas automaticamente.

1. Selecione a saída desejada ativando ou desativando o botão deslizante.
1. Clique em **Concluído**.

   Os arquivos de mapa DITA são adicionados à Coleção de mapas.

   ![painel da coleção de mapas](./images/map-collection-dashboard.png){width="800" align="left"}

As seguintes opções de filtro e detalhes do mapa são mostrados na página de coleção:

- **Filtro:** O painel inferior mostra os seguintes filtros:
   - **Modificado**: Você pode selecionar Sim ou Não. Se você selecionar sim, somente os mapas DITA modificados serão exibidos na tabela Mapas e predefinições.
   - **Predefinição**: selecione uma predefinição para a qual deseja filtrar os arquivos de mapa. Por exemplo, se você escolher *Site AEM* predefinido, serão exibidos apenas os mapas que tiverem a *Site AEM* predefinição de saída configurada neles.
   - **Idioma**: é possível selecionar qualquer um dos códigos de idioma disponíveis e exibir apenas o idioma selecionado na tabela Mapas e predefinições.
- **Mapas e predefinições** tabela: A tabela Mapas e Predefinições apresenta informações nas seguintes colunas:
   - **Mapa**: mostra o título do arquivo de mapa DITA.
   - **Nome do arquivo**: mostra o nome de arquivo do mapa DITA.
   - **Idioma**: mostra o idioma do mapa DITA.
   - **Predefinição**: mostra o tipo de predefinição de saída configurado no arquivo de mapa.
   - **Linha de base**: mostra a linha de base usada pela predefinição de saída.  Se nenhuma linha de base for usada, ela mostrará um hífen &quot;-&quot;
   - **Modificado**: indica se o mapa DITA foi atualizado após a última publicação. Com base nessas informações, você pode decidir se deseja republicar a saída desse mapa DITA ou não.
   - **Gerado por último**: mostra a data e a hora da última saída gerada.

## Configurar e gerar a saída usando uma coleção de mapas

Para configurar e gerar a saída usando uma Coleção de mapas, execute as seguintes etapas:

1. Abra a Coleção de Mapas. Você pode visualizar as várias predefinições de saída, como o Site AEM, PDF (incluindo PDF Nativo), HTML5, EPUB e predefinições Personalizadas. Também é possível exibir as predefinições de perfil global e de pasta criadas pelo administrador.

   A variável ![](images/global-preset-icon.svg) O ícone indica uma predefinição no nível do perfil de pasta.
1. \(Opcional\) Siga qualquer um dos procedimentos a seguir com base em seus requisitos:
   - Aplique filtros no painel esquerdo para filtrar os mapas modificados, a predefinição de saída ou o idioma.
   - Se necessário, clique em **Editar** e altere a saída desejada ativando ou desativando o botão deslizante.



     >[!NOTE]
     >  
     > Por padrão, qualquer nova predefinição é desativada.

1. Você pode ativar as predefinições de um mapa DITA das seguintes maneiras:

   - Ativar qualquer predefinição individual.
   - Ativar **Todas as predefinições** para que um mapa DITA selecione todas as predefinições de uma só vez. Essa opção está desabilitada por padrão.
   - Ativar **Predefinições de perfil de pasta** para que um mapa DITA selecione todas as predefinições de perfil de pasta para ele. Essa opção está desabilitada por padrão.
     ![editar uma coleção de mapas nos serviços em nuvem](images/edit-map-collection-cs.png){width="800" align="left"}



1. Siga uma das seguintes opções:

   - Para gerar a saída de mapas selecionados, selecione os arquivos de mapa e clique em **Gerar seleção**.
   - Para gerar a saída de todos os mapas DITA com suas predefinições configuradas, clique em **Gerar tudo**.

   >[!IMPORTANT]
   >
   > Se um processo de geração de saída para uma predefinição ou um mapa DITA estiver na fila ou em andamento, não será possível iniciar outra tarefa de geração de saída para a mesma predefinição ou mapa.

## Configurar as propriedades dos metadados

Na coleção de mapas, é possível configurar as propriedades de metadados em massa para os mapas DITA. Selecionar **Configurar metadados**  para abrir o **Metadados do ativo** página. No **Metadados do ativo** todos os mapas presentes na coleção estão listados à esquerda.

![configurar metadados](images/map-collection-asset-metadata.png){width="800" align="left"}

Execute as seguintes etapas para configurar as propriedades de metadados:

1. Você pode escolher os mapas para os quais deseja atualizar os metadados. Por padrão, todos os mapas DITA presentes são selecionados.

1. Depois de selecionar os mapas DITA, você pode visualizar propriedades como metadados, agendar (des)ativação, referências, estado do documento e muito mais.

1. Atualize as propriedades dos metadados.

1. Clique em **Salvar e fechar** na parte superior para salvar as atualizações.
1. (Opcional) Ao atualizar as tags, você também pode selecionar Anexar na **Salvar e fechar** para anexar as novas tags à lista existente.
1. Clique em **Enviar** do **Salvar e fechar** lista suspensa.
As propriedades dos metadados são atualizadas para os mapas DITA selecionados em massa na coleção de mapas.

>[!NOTE]
> 
>Para o **Estado do documento** , é possível selecionar apenas os estados do documento permitidos em comum para todos os mapas DITA selecionados. Para saber mais, consulte [**Estado do documento**](./web-editor-document-states.md).

As propriedades de metadados estão sincronizadas com as propriedades do arquivo. Depois de atualizá-los, você pode visualizá-los na **Propriedades do arquivo** no Editor da Web.



## Excluir uma coleção de mapas ou um mapa DITA da coleção de mapas

- Para excluir uma coleção de mapas, selecione uma coleção na página Coleção de Mapas e clique em **Excluir**.
- Para excluir um mapa DITA de uma coleção de mapas, abra a Coleção de mapas no modo Editar, selecione o arquivo de mapa DITA e clique em **Remover da coleção**.

Isso também removerá quaisquer predefinições ou localidades associadas ao mapa DITA da Coleção de mapas.


## Cancelar uma tarefa de geração de saída de uma coleção de mapas

Semelhante à forma de cancelar uma tarefa de geração de saída do [Console de mapa DITA](generate-output-for-a-dita-map.md#id2061H100T5Z) ou o [Publicar painel](generate-output-publish-dashboard.md#), é possível cancelar uma tarefa de geração de saída a partir de uma coleção de mapas. Acesse a guia Saídas de uma Coleção de mapas, vá para a tarefa de publicação que deseja cancelar e clique no **Cancelar Este Trabalho** ícone para cancelar a tarefa de publicação.

![](images/cancel-publish-task-map-collection.png){width="800" align="left"}

**Tópico pai:**[ Geração de saída](generate-output.md)
