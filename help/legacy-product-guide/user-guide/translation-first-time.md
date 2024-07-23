---
title: Práticas recomendadas para tradução de conteúdo
description: Conhecer as práticas recomendadas para tradução de conteúdo no AEM Guides. Saiba como configurar o serviço de tradução, criar um novo projeto de tradução e iniciar o trabalho de tradução.
feature: Translation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 1%

---

# Práticas recomendadas para tradução de conteúdo {#id1678G0S702F}

Considere o seguinte ponto para a tradução de conteúdo:

- A pasta e os nomes de arquivo devem estar em conformidade com os padrões de nomenclatura de arquivo, como: não deve haver espaços, apóstrofo, chaves, sinal de igual, caracteres especiais ou não ASCII.

- Se você traduzir o conteúdo em idiomas diferentes, deverá criar pastas correspondentes a cada idioma. Cada uma dessas pastas de idioma conterá o conteúdo correspondente a esse idioma. Por exemplo, você pode criar pastas usando o designador de idioma como `de` para alemão, `fr` para francês e assim por diante. Ou você pode criar pastas usando os designadores de idioma e região como `fr-FR` para francês, como usado na França, ou `fr-CA` para francês, como usado no Canadá.
- O idioma de destino também deve ter as localidades reais selecionadas de acordo com as pastas de idioma de destino em sua instância.
- A configuração da nuvem deve ser igual à da pasta de origem e deve haver apenas uma configuração da nuvem em uma pasta. É possível criar várias pastas em /conf, se desejar usar vários conectores de tradução.
- Uma pasta não deve conter mais de 1000 arquivos.
- Certifique-se de que o usuário encarregado de iniciar o processo de tradução tenha permissões de Leitura, Modificação, Criação e Exclusão nas pastas de idioma de origem e destino.
- Como a tradução de conteúdo requer a criação de um projeto de tradução, o usuário deve ter acesso para criar um projeto no AEM.
- Se você quiser usar Predefinições condicionais com o mapa, é necessário criá-las antes de iniciar o processo de tradução. Como as Predefinições condicionais também são agrupadas na versão traduzida do mapa, criar as predefinições antes de iniciar o processo de tradução garante que elas estejam disponíveis na versão traduzida.
- O processo de tradução de conteúdo deve ser iniciado no console de mapas DITA, não na interface do usuário do AEM Assets.
- O fluxo de trabalho de tradução DITA baseado em componentes não deve ser usado se você estiver traduzindo conteúdo por meio de tradução humana. No entanto, essa opção deve ser usada para tradução automática.
- O conteúdo e a mídia usados globalmente que não exigem localização devem ser mantidos fora das cópias de idioma.
- Todo o conteúdo comum que deve ser localizado deve ser mantido em uma pasta comum na pasta de idiomas.

A ilustração a seguir mostra um exemplo de estrutura de pastas no AEM quando você tem conteúdo usado globalmente e três cópias de idioma.

![](images/aem-directory_structure.png){width="800" align="left"}

## Configurar serviço de tradução

Execute as seguintes etapas para configurar o serviço de tradução humana ou automática a ser usado:

1. Na interface do usuário do Assets, selecione a pasta do idioma de origem.

1. Abra as propriedades da pasta e vá para a guia **Cloud Service**.

1. Na guia **Cloud Service**, configure o serviço de tradução que deseja usar.

   Você pode configurar tradução humana ou baseada em máquina.

   Verifique se há apenas uma configuração para o conector de tradução em uma pasta. Várias pastas podem ser criadas em /conf, se houver vários conectores de tradução. A pasta de idioma de origem deve ter uma configuração de nuvem selecionada antes de iniciar o processo de tradução.

   >[!NOTE]
   >
   > Consulte [Configurando a estrutura de integração de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) na documentação do AEM para obter detalhes sobre a integração com serviços de tradução de terceiros.

1. Clique em **Salvar e fechar** para salvar as propriedades atualizadas da pasta.


>[!TIP]
>
> Consulte a seção *Tradução* no guia de Práticas recomendadas para obter as práticas recomendadas sobre a tradução de conteúdo.

## Criar um novo projeto de tradução

Execute as seguintes etapas para criar um projeto de tradução:

>[!NOTE]
>
> Antes de executar etapas neste procedimento, verifique se você criou a raiz de idioma e as pastas de destino necessárias, conforme descrito nas [Práticas recomendadas para tradução de conteúdo](#id1678G0S702F).

1. Na interface do Assets, clique no arquivo de mapa DITA.

1. Clique na guia **Tradução**.

1. Na lista **Idiomas de destino**, selecione o local para o qual deseja traduzir seu projeto e clique em **Concluído**.

   Um Resumo e Detalhes de tópicos e ativos associados são mostrados.

   >[!IMPORTANT]
   >
   > Os **Idiomas de Destino** mostram apenas os idiomas para os quais uma pasta de idioma é criada paralelamente ao idioma de origem. Uma pasta de idioma criada em qualquer outro nível, como um nível abaixo da pasta de idioma de origem, também não é exibida. Crie todas as pastas de idioma de destino no mesmo nível que a pasta de idioma de origem.

1. Selecione os tópicos que deseja enviar para tradução.

   Você também pode usar as seguintes opções de filtragem de tópico:

   >[!NOTE]
   >
   > Depois de aplicar o filtro necessário, clique em **Concluído** no painel Filtro para filtrar os tópicos com base na sua seleção.

   - **Status da tradução**: escolha filtrar tópicos com base em seu status de tradução. As opções disponíveis são: Out of Sync, Missing Copy, In Progress e In Sync.
   - **Pesquisa**: insira um ou vários termos para pesquisar nos títulos dos tópicos.
   - **Tipo de Source**: escolha filtrar tópicos com base em seus tipos de arquivo. As opções disponíveis são: All, DITA, DITA Map, Resource.
   - **Versão do Source Modificada Após**: escolha filtrar o tópico com base na data e hora de modificação. Todos os tópicos modificados após a data e hora especificadas são mostrados na lista.
   - **Linha de Base**: clique em Usar Linha de Base e escolha uma linha de base criada no mapa. Todos os arquivos que fazem parte da Linha de base selecionada são mostrados na página Tradução. Você pode escolher os arquivos desejados na linha de base e prosseguir com o processo de tradução. Depois que o conteúdo for traduzido, você poderá exportar a Linha de base traduzida. Para obter mais detalhes sobre como exportar a Linha de Base traduzida, consulte [Exportar Linha de Base traduzida](generate-output-use-baseline-for-publishing.md#id196SE600GHS).
1. Clique em **Criar/Atualizar Cópias de Idioma** na parte inferior do painel Filtro.

1. Na lista **Projeto**, selecione **Criar um Novo Projeto de Tradução**.

   >[!NOTE]
   >
   > Se você já tiver um projeto de tradução, poderá adicionar tópicos a esse projeto. Selecione a opção **Adicionar ao projeto de tradução existente** da lista **Projeto** e escolha um projeto da lista **Projeto de tradução existente**.

1. No campo **Título do projeto**, informe um título para o projeto.

1. Selecione a opção **Incluir mapa DITA** para enviar o mapa para tradução.
1. Clique em **Iniciar** para criar um novo projeto de tradução.

   Um novo projeto de tradução é criado com a versão selecionada dos tópicos. No momento, uma mensagem pop-up é exibida confirmando que o projeto de tradução foi criado. Quando todas as cópias de idioma de destino estiverem disponíveis no projeto de tradução, você receberá uma notificação na Caixa de entrada. Depois que a área de cópias do idioma de destino estiver disponível no projeto de tradução, você poderá continuar e iniciar o trabalho de tradução.

   ![](images/status-translation-uuid.png){width="800" align="left"}


A guia Tradução tem as seguintes seções:

- **Resumo**: mostra o número de tópicos e o idioma de origem referenciados junto com seu código.
- **Detalhes**: mostra o título do tópico, o tipo de tópico, o código do idioma do tópico, o idioma de origem, a versão do tópico de origem, o rótulo adicionado ao tópico e o status da tradução.




## Iniciar o trabalho de tradução {#id225IK030OE8}

Execute as seguintes etapas para iniciar o trabalho de tradução:

1. No console **Projetos**, navegue até a pasta do projeto que você criou para localização.

1. Clique no projeto de localização para abrir a página de detalhes.

1. Clique na seta no bloco **Trabalho de tradução** e selecione **Iniciar** na lista para iniciar o fluxo de trabalho de tradução.

   >[!NOTE]
   >
   > Se você estiver usando o serviço de tradução humana, será necessário exportar o conteúdo para tradução. Depois de ter o conteúdo traduzido, é necessário importá-lo de volta para o projeto de tradução.

1. Para exibir o status do trabalho de tradução, clique nas reticências na parte inferior do bloco **Trabalho de tradução**.


Após a conclusão da tradução, o status do trabalho de tradução é alterado para *Pronto para Revisão*. Para concluir o processo de tradução, você precisa aceitar a cópia traduzida e os metadados do ativo do bloco Tarefa de tradução no console Projeto.

>[!NOTE]
>
> Se você rejeitar a tradução de um ou mais tópicos em um trabalho de tradução, o status de tradução **Em andamento** de todos os tópicos rejeitados será revertido para seu status original. O status dos tópicos referenciados é verificado e revertido de acordo com o estado de tradução mais recente. Além disso, os arquivos de tradução criados no projeto de destino não são excluídos, mesmo que a tradução seja rejeitada para eles.

**Tópico pai:**[ Traduzir conteúdo](translation.md)
