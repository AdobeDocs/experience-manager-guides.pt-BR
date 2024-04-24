---
title: Criar uma coleção de mapas de ativação em massa
description: Saiba como criar uma coleção de mapas de ativação em massa em guias AEM.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: 1be8cddcbf58696a53bfccf887a04e5807f2198e
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Criar uma coleção de mapas de ativação em massa {#id214GG0E90EV}

Para criar uma coleção de mapas de ativação em massa, execute as seguintes etapas:

1. Selecionar **Guias** na lista de ferramentas.

1. Selecione o link Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecione o **Painel de publicação em massa** bloco.

   Pela primeira vez, uma página de coleções em branco é exibida. Se você tiver criado coleções de ativação em massa anteriormente, elas serão exibidas nesta página.

1. Clique em **Criar**.

1. Insira um título para a coleção de mapas de ativação em massa e clique em **Criar**.

   Uma mensagem de sucesso é exibida ao criar a coleção de mapas de ativação em massa.

1. Clique em **Abertura** na mensagem de sucesso.

1. Selecionar **Editar** e selecione **Adicionar mapas**.

1. Localize e adicione os mapas DITA que deseja adicionar à coleção de mapas de ativação em massa.

   Por padrão, todas as predefinições e localidades associadas ao mapa são adicionadas automaticamente.

1. Selecione a saída desejada ativando ou desativando o botão deslizante.

   Você pode escolher várias predefinições de saída entre os locais disponíveis.

1. Clique em **Concluído**.

Os arquivos de mapa DITA são adicionados à sua coleção de mapas de ativação em massa.

![ coleção de ativação em massa criada](images/bulk-activation-collection-created.png){width="800" align="left"}

## Guia Mapas e predefinições

A variável **Mapas e predefinições** A guia apresenta informações nas seguintes colunas:

- **Mapa**: mostra o título do arquivo de mapa DITA.
- **Caminho do mapa**: mostra o caminho completo do arquivo de mapa DITA.

- **UUID**: mostra o identificador exclusivo associado ao arquivo.

- **Idioma**: mostra o código de idioma do mapa DITA.
- **Predefinição**: mostra o título da predefinição de saída configurada no arquivo de mapa. Ela também exibe o ícone com base no tipo de predefinição de saída.

  >[!NOTE]
  >
  > Os pequenos ![](images/global-preset-icon.svg) O ícone indica uma predefinição no nível do perfil de pasta.

- **Modificado**: indica se o mapa DITA foi atualizado após a última publicação. Com base nessas informações, você pode decidir se deseja ativar ou não a saída para esse mapa DITA.
- **Gerado**: mostra a data e a hora da última saída gerada.
- **Publicado**: mostra a data e a hora da última saída publicada (ou ativada). Se você selecionar o link, a variável **Resultados da ativação** será exibida, contendo os logs com informações sobre o caminho raiz onde o conteúdo é ativado.

## Guia Histórico de auditoria

A variável **Histórico de auditoria** tab apresenta informações sobre as saídas do mapa ativado nas seguintes colunas:
- **Mapa**: mostra o título do arquivo de mapa DITA.
- **Caminho do mapa**: mostra o caminho completo do arquivo de mapa DITA.
- **UUID** : mostra o identificador exclusivo associado ao arquivo.
- **Idioma**: mostra o código de idioma do mapa DITA.
- **Predefinição**: mostra o título da predefinição de saída configurada no arquivo de mapa. Ela também exibe o ícone com base no tipo de predefinição de saída.
- **Status**: mostra o status de ativação como bem-sucedido ou malsucedido.
- **Destino**: se você gerar a saída no Experience Manager Guides as a Cloud Service, poderá visualizar o destino da saída como Publicar ou Pré-visualizar.

  >[!NOTE]
  >
  > Os pequenos ![](images/global-preset-icon.svg) O ícone indica uma predefinição no nível do perfil de pasta.

- **Modificado**: indica se o mapa DITA foi atualizado após a última publicação. Com base nessas informações, você pode decidir se ativará a saída para esse mapa DITA.
- **Publicado**: mostra a data e a hora da última saída publicada (ou ativada). Se você selecionar o link, a página Resultados da ativação será exibida, contendo os logs com informações sobre o caminho raiz onde o conteúdo é ativado.
  ![ guia histórico de auditoria de coleção de ativação em massa criada](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Exibir as informações sobre as saídas do mapa ativado na **Histórico de auditoria**guia.*


  >[!NOTE]
  >
  > As saídas no **Histórico de auditoria** são classificadas com base no **Publicado** coluna.



## Painel esquerdo

As seguintes opções de filtro estão disponíveis no painel esquerdo:

- **Modificado**: Você pode selecionar Sim ou Não. Se você selecionar sim, somente os mapas DITA modificados serão exibidos. Um mapa modificado é um mapa gerado desde a última publicação.
- **Predefinição**: selecione uma predefinição para a qual deseja filtrar os arquivos de mapa. Essa coluna mostra o título da predefinição de saída configurada no arquivo de mapa. Por exemplo, se você escolher *Site AEM* predefinido, serão exibidos apenas os mapas que tiverem a *Site AEM* predefinição de saída configurada neles.
- **Idioma**: é possível selecionar qualquer um dos códigos de idioma disponíveis e exibir somente o idioma selecionado na guia Mapas e predefinições.

Os filtros são atualizados quando você alterna da variável **Mapas e predefinições** para a guia **Histórico de auditoria** e vice-versa.

**Tópico principal: **[Ativação em massa de conteúdo publicado](conf-bulk-activation.md)
