---
title: Criar uma coleção de mapas de ativação em massa
description: Saiba como criar uma coleção de mapas de ativação em massa em guias AEM.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Criar uma coleção de mapas de ativação em massa {#id214GG0E90EV}

Para criar uma coleção de mapas de ativação em massa, execute as seguintes etapas:

1. Selecionar **Guias** na lista de ferramentas.

1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Clique no link **Painel de publicação em massa** bloco.

   Pela primeira vez, uma página de coleções em branco é exibida. Se você tiver criado coleções de ativação em massa anteriormente, elas serão exibidas nesta página.

1. Clique em **Criar**.

1. Insira um título para a coleção de mapas de ativação em massa e clique em **Criar**.

   Uma mensagem de Sucesso é exibida ao criar a coleção de mapas de ativação em massa.

1. Clique em **Abertura** na mensagem Success (Êxito).

1. Clique em **Editar** e clique em **Adicionar mapas**.

1. Localize e adicione os mapas DITA que deseja adicionar à coleção de mapas de ativação em massa.

   Por padrão, todas as predefinições e localidades associadas ao mapa são adicionadas automaticamente.

1. Selecione a saída desejada ativando ou desativando o botão deslizante.

   Você pode escolher várias predefinições de saída entre os locais disponíveis.

1. Clique em **Concluído**.

   Os arquivos de mapa DITA são adicionados à sua coleção de mapas de ativação em massa.

   ![](images/bulk-activation-collection-created.png){width="800" align="left"}


A guia Mapas e Predefinições apresenta informações nas seguintes colunas:

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


As seguintes opções de filtro estão disponíveis no painel esquerdo:

- **Modificado**: Você pode selecionar Sim ou Não. Se você selecionar sim, somente os mapas DITA modificados serão exibidos. Um mapa modificado é um mapa gerado desde a última publicação.
- **Predefinição**: selecione uma predefinição para a qual deseja filtrar os arquivos de mapa. Por exemplo, se você escolher *Site AEM* predefinido, serão exibidos apenas os mapas que tiverem a *Site AEM* predefinição de saída configurada neles.
- **Idioma**: é possível selecionar qualquer um dos códigos de idioma disponíveis e exibir somente o idioma selecionado na guia Mapas e predefinições.

- **Filtro:** O painel inferior mostra os seguintes filtros:
- **Mapas e predefinições** tabela: A tabela Mapas e Predefinições mostra as seguintes colunas:

**Tópico pai:**[ Ativação em massa de conteúdo publicado](conf-bulk-activation.md)
