---
title: Práticas recomendadas para tradução de conteúdo
description: Conhecer as práticas recomendadas para tradução de conteúdo no AEM Guides. Saiba como configurar o serviço de tradução, criar um novo projeto de tradução e iniciar o trabalho de tradução.
exl-id: f2a4df86-bba7-434c-b7f9-3587b8a4f9bc
feature: Translation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 0%

---

# Práticas recomendadas para tradução de conteúdo {#id1678G0S702F}

Considere o seguinte ponto para a tradução de conteúdo:

- A pasta e os nomes de arquivo devem estar em conformidade com os padrões de nomenclatura de arquivo, como: não deve haver espaços, apóstrofo, chaves, sinal de igual, caracteres especiais ou não ASCII.

- Se você traduzir o conteúdo em idiomas diferentes, deverá criar pastas correspondentes a cada idioma. Cada uma dessas pastas de idioma conterá o conteúdo correspondente a esse idioma. Por exemplo, você pode criar pastas usando o designador de idioma como `de` para alemão, `fr` para francês e assim por diante. Ou você pode criar pastas usando os designadores de idioma e região como `fr-FR` para francês, como usado na França, ou `fr-CA` para francês, como usado no Canadá.
- O idioma de destino também deve ter as localidades reais selecionadas de acordo com as pastas de idioma de destino em sua instância.
- A configuração da nuvem deve ser igual à da pasta de origem e deve haver apenas uma configuração da nuvem em uma pasta. É possível criar várias pastas em /conf, se desejar usar vários conectores de tradução.
- Uma pasta não deve conter mais de 1000 arquivos.
- Certifique-se de que o usuário encarregado de iniciar o processo de tradução tenha permissões de Leitura, Modificação, Criação e Exclusão nas pastas de idioma de origem e destino.
- Como a tradução de conteúdo requer a criação de um projeto de tradução, o usuário deve ter acesso para criar um projeto no Adobe Experience Manager.
- Se você quiser usar Predefinições condicionais com o mapa, é necessário criá-las antes de iniciar o processo de tradução. Como as Predefinições condicionais também são agrupadas na versão traduzida do mapa, criar as predefinições antes de iniciar o processo de tradução garante que elas estejam disponíveis na versão traduzida.
- O processo de tradução de conteúdo deve ser iniciado no console de mapas DITA, não na interface do usuário do Adobe Experience Manager Assets.
- O fluxo de trabalho de tradução DITA baseado em componentes não deve ser usado se você estiver traduzindo conteúdo por meio de tradução humana. No entanto, essa opção deve ser usada para tradução automática.
- O conteúdo e a mídia usados globalmente que não exigem localização devem ser mantidos fora das cópias de idioma.
- Todo o conteúdo comum que deve ser localizado deve ser mantido em uma pasta comum na pasta de idiomas.

A ilustração a seguir mostra um exemplo de estrutura de pastas no Adobe Experience Manager quando você tem conteúdo usado globalmente e três cópias de idioma.

![](images/aem-directory_structure.png){align="left"}

## Configurar serviço de tradução

Execute as seguintes etapas para configurar o serviço de tradução humana ou automática a ser usado:

1. Na interface do usuário do Assets, selecione a pasta do idioma de origem.

1. Abra as propriedades da pasta e vá para a guia **Cloud Services**.

1. Na guia **Cloud Services**, configure o serviço de tradução que deseja usar.

   Você pode configurar tradução humana ou baseada em máquina.

   Verifique se há apenas uma configuração para o conector de tradução em uma pasta. Várias pastas podem ser criadas em /conf, se houver vários conectores de tradução. A pasta de idioma de origem deve ter uma configuração de nuvem selecionada antes de iniciar o processo de tradução.

   >[!NOTE]
   >
   > Exiba [Configurando a estrutura de integração de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) na documentação do Adobe Experience Manager para obter detalhes sobre a integração com serviços de tradução de terceiros.

1. Selecione **Salvar e fechar** para salvar as propriedades atualizadas da pasta.


## Iniciar o trabalho de tradução {#id225IK030OE8}

Execute as seguintes etapas para iniciar o trabalho de tradução:

1. No console **Projetos**, navegue até a pasta do projeto que você criou para localização.

1. Selecione o projeto de localização para abrir a página de detalhes.

1. Selecione a seta no bloco **Trabalho de tradução** e selecione **Iniciar** na lista para iniciar o fluxo de trabalho de tradução.

   >[!NOTE]
   >
   > Se você estiver usando o serviço de tradução humana, será necessário exportar o conteúdo para tradução. Depois de ter o conteúdo traduzido, é necessário importá-lo de volta para o projeto de tradução.

1. Para exibir o status do trabalho de tradução, selecione as reticências na parte inferior do bloco **Trabalho de Tradução**.


Após a conclusão da tradução, o status do trabalho de tradução é alterado para *Pronto para Revisão*. Para concluir o processo de tradução, você precisa aceitar a cópia traduzida e os metadados do ativo do bloco Tarefa de tradução no console Projeto. Se quiser iniciar um novo projeto de tradução, exiba [Criar um projeto de tradução](translate-documents-web-editor.md#create-a-translation-project).

>[!NOTE]
>
>- Se você rejeitar a tradução de um ou mais tópicos em um trabalho de tradução, o status de tradução **Em andamento** de todos os tópicos rejeitados será revertido para seu status original. O status dos tópicos referenciados é verificado e revertido de acordo com o estado de tradução mais recente. Além disso, os arquivos de tradução criados na pasta de idioma de destino não são excluídos, mesmo que a tradução seja rejeitada para eles.
>- Se você rejeitar, excluir ou cancelar o trabalho de tradução de um tópico presente em vários projetos (para qualquer um dos projetos), o status de tradução **Em andamento** do tópico não será revertido, mas esse projeto será removido da lista de projetos **Em andamento** desse ativo específico.
>- Além disso, se você cancelar ou excluir o trabalho de tradução ou excluir o projeto inteiro, o status de tradução **Em andamento** será revertido para seu status original.

**Tópico principal:**[ Visão geral da tradução de conteúdo](translation.md)
