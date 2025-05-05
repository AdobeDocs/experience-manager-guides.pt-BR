---
title: Criar uma coleção de mapas de ativação em massa
description: Saiba como criar uma coleção de mapas de ativação em massa nos guias do AEM.
feature: Publishing, Bulk Activation
role: User
hide: true
exl-id: a242efde-2b29-4d2b-8a50-fd4ae7e8f239
source-git-commit: 4801f0d327b4bd0641aa195d39ec2c4be2a2ce74
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Criar uma coleção de mapas de ativação em massa {#id214GG0E90EV}

Para criar uma coleção de mapas de ativação em massa, execute as seguintes etapas:

1. Selecione **Guias** na lista de ferramentas.

1. Selecione o link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecione o bloco **Painel de publicação em massa**.

   Pela primeira vez, uma página de coleções em branco é exibida. Se você tiver criado coleções de ativação em massa anteriormente, elas serão exibidas nesta página.

1. Clique em **Criar**.

1. Insira um título para a coleção de mapas de ativação em massa e clique em **Criar**.

   Uma mensagem de sucesso é exibida ao criar a coleção de mapas de ativação em massa.

1. Clique em **Abrir** na mensagem de êxito.

1. Selecione **Editar** e **Adicionar mapas**.

1. Localize e adicione os mapas DITA que deseja adicionar à coleção de mapas de ativação em massa.

   Por padrão, todas as predefinições e localidades associadas ao mapa são adicionadas automaticamente.

1. Selecione a saída desejada ativando ou desativando o botão deslizante.

   Você pode escolher várias predefinições de saída entre os locais disponíveis.

1. Clique em **Concluído**.

Os arquivos de mapa DITA são adicionados à sua coleção de mapas de ativação em massa.

![ criou a coleção de ativação em massa](images/bulk-activation-collection-created.png){width="800" align="left"}

## Guia Mapas e predefinições

A guia **Mapas e Predefinições** apresenta informações nas seguintes colunas:

- **Mapa**: mostra o título do arquivo de mapa DITA.
- **Caminho do mapa**: mostra o caminho completo do arquivo de mapa DITA.

- **UUID**: mostra o identificador exclusivo associado ao arquivo.

- **Idioma**: mostra o código de idioma do mapa DITA.
- **Predefinição**: mostra o título da predefinição de saída configurada no arquivo de mapa. Ela também exibe o ícone com base no tipo de predefinição de saída.

  >[!NOTE]
  >
  > O ícone pequeno ![](images/global-preset-icon.svg) indica uma predefinição de nível de perfil de pasta.

- **Modificado**: indica se o mapa DITA é atualizado após a última publicação. Com base nessas informações, você pode decidir se deseja ativar ou não a saída para esse mapa DITA.
- **Gerado**: mostra a data e a hora da última saída gerada.
- **Publicado**: mostra a data e a hora da última saída publicada (ou ativada). Se você selecionar o link, a página **Resultados da Ativação** será exibida, contendo os logs com informações sobre o caminho raiz onde o conteúdo é ativado.

## Guia Histórico de auditoria

A guia **Histórico de Auditoria** apresenta informações sobre as saídas de mapa ativadas nas seguintes colunas:
- **Mapa**: mostra o título do arquivo de mapa DITA.
- **Caminho do mapa**: mostra o caminho completo do arquivo de mapa DITA.
- **UUID** : mostra o identificador exclusivo associado ao arquivo.
- **Idioma**: mostra o código de idioma do mapa DITA.
- **Predefinição**: mostra o título da predefinição de saída configurada no arquivo de mapa. Ela também exibe o ícone com base no tipo de predefinição de saída.
- **Status**: mostra o status de ativação como bem-sucedido ou malsucedido.
- **Destino**: se você gerar a saída no Experience Manager Guides as a Cloud Service, poderá exibir o destino da saída como Publicar ou Visualizar.

  >[!NOTE]
  >
  > O ícone pequeno ![](images/global-preset-icon.svg) indica uma predefinição de nível de perfil de pasta.

- **Modificado**: indica se o mapa DITA foi atualizado após a última publicação. Com base nessas informações, você pode decidir se ativará a saída para esse mapa DITA.
- **Publicado**: mostra a data e a hora da última saída publicada (ou ativada). Se você selecionar o link, a página Resultados da ativação será exibida, contendo os logs com informações sobre o caminho raiz onde o conteúdo é ativado.
  ![ criou a guia de histórico de auditoria da coleção de ativação em massa](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Exiba as informações sobre as saídas do mapa ativado na guia **Histórico de Auditoria**.*


  >[!NOTE]
  >
  > As saídas na guia **Histórico de Auditoria** são classificadas com base na coluna **Publicado**.



## Painel esquerdo

As seguintes opções de filtro estão disponíveis no painel esquerdo:

- **Modificado**: você pode selecionar Sim ou Não. Se você selecionar sim, somente os mapas DITA modificados serão exibidos. Um mapa modificado é um mapa gerado desde a última publicação.
- **Predefinição**: selecione uma predefinição para a qual deseja filtrar os arquivos de mapa. Essa coluna mostra o título da predefinição de saída configurada no arquivo de mapa. Por exemplo, se você escolher a predefinição *Site do AEM*, serão exibidos apenas os mapas que tiverem a predefinição de saída *Site do AEM* configurada.
- **Idioma**: você pode selecionar qualquer um dos códigos de idioma disponíveis e exibir somente o idioma selecionado na guia Mapas e Predefinições.

Os filtros são atualizados quando você alterna da guia **Mapas e Predefinições** para a guia **Histórico de Auditoria** e vice-versa.

**Tópico pai: &#x200B;** [Ativação em massa de conteúdo publicado](conf-bulk-activation.md)
