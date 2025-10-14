---
title: Usar predefinições de condição
description: Conhecer o uso de predefinições de condição no AEM Guides. Saiba como criar, editar, copiar e excluir predefinições de condição no AEM.
feature: Publishing
role: User
hide: true
exl-id: 991179c7-186e-4b23-b918-248f596644ec
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 1%

---

# Usar predefinições de condição {#id1825FL004PN}

Você pode definir atributos em seus tópicos DITA e usar a predefinição de condição para especificar o que acontece com o atributo na saída final. Por exemplo, você pode adicionar atributos como versão 1.0 e versão 2.0 no conteúdo e usar uma predefinição de condição para incluir a versão 1.0 para a versão 1.0 e excluir a versão 2.0. Da mesma forma, você pode adicionar atributos como SO Windows e OS Linux ao seu conteúdo e, em seguida, incluir ou excluir o conteúdo relevante para sua saída final de acordo com o sistema operacional.

É possível criar predefinições de condição de duas maneiras:

* No Editor da Web: permite criar e gerenciar as predefinições de condição para um mapa DITA no Editor da Web.
* No painel de mapa: permite criar e gerenciar as predefinições de condição para um mapa DITA no painel de mapa.


## Predefinições de condição do Editor da Web

O Experience Manager Guides permite gerenciar predefinições de condição no Editor da Web e usá-las nas predefinições de Saída para gerar a saída final.
Você pode criar e exibir as predefinições de condição, exibir os atributos e gerenciar as ações para o mapa atual na exibição **Predefinições de condição** no Editor da Web.

<img src="images//manage-condtions-presets.png" alt= "Predefinições de condição no editor da Web" width="800" border="1px">



### Criar uma predefinição de condição

A exibição **Predefinições de Condição** fornece informações detalhadas sobre as predefinições de condição, como atributos, valores e ações.
É possível criar uma predefinição de condição dos tópicos executando as seguintes etapas:

1. No painel **Repositório**, abra o arquivo de mapa DITA no Modo de Exibição de Mapa.
1. Selecione a guia **Gerenciar**.
1. Selecione **Predefinições de condição** à esquerda. A lista de predefinições de condições definidas para o mapa DITA é exibida.
1. Selecione o ícone + ao lado de **Predefinições de Condição** para abrir a caixa de diálogo **Nova Predefinição de Condição**.
1. Insira um nome exclusivo para a predefinição.

   >[!NOTE]
   >
   > Um erro é exibido se o campo de nome estiver vazio ou se você inserir um caractere inválido ou um nome que seja igual a uma predefinição de condição existente. Você pode usar um hífen &#39;-&#39; ou sublinhado &#39;_&#39; como separador.

1. Selecione **Criar**.
A nova predefinição de condição é adicionada à lista.
1. Clique duas vezes em uma predefinição de condição para exibir os atributos e as ações.
O painel **Atributos** mostra todos os atributos adicionados a quaisquer referências presentes no mapa. O painel direito mostra apenas as condições que você adicionou às predefinições de condição.
1. Siga qualquer um destes procedimentos para adicionar os atributos:
   * Selecione um ou mais atributos para adicionar todos os valores abaixo deles à predefinição de condição. Por exemplo, você pode selecionar o atributo `platform` para adicionar todos os seus valores.
   * Selecione um ou mais valores de atributo para adicioná-los à predefinição de condição. Por exemplo, você pode selecionar os valores `Unix` e `Win` do atributo platform
   * Selecione qualquer par de atributo e valor e arraste-o para o painel central. Por exemplo, você pode selecionar o valor `Unix` do atributo de plataforma e arrastá-lo.
   * **Selecione todos** para adicionar todos os atributos e seus valores à predefinição de condição.
Por padrão, a ação de um atributo é `Include`.

1. Selecione **Adicionar**. Você pode repetir essa etapa para adicionar mais atributos. Os atributos adicionados são movidos do painel central para o direito.
1. Selecione Remover na barra de ações na parte superior para remover os atributos selecionados no painel direito.
1. (Opcional) Se necessário, é possível substituir a ação aplicada aos atributos.
Siga uma das seguintes opções:
   * Para qualquer atributo, selecione uma das seguintes ações no menu suspenso Ação.
      * Incluir
      * Excluir
      * Passagem
      * Sinalizador
   * Selecione várias linhas de atributo no painel direito e escolha uma ação na barra de ações na parte superior. Por exemplo, você pode selecionar Excluir ação para os atributos selecionados.
1. Selecione **Salvar** para salvar a predefinição de condição.

   >[!NOTE]
   >
   > Um aviso será exibido se outra predefinição for selecionada ou se a predefinição for fechada sem ser salva.

Depois de criar uma predefinição de condição, ela aparecerá na lista suspensa **Predefinições de condição** das predefinições de Saída. Saiba mais sobre como [Publicar saída do PDF](/help/product-guide/web-editor/native-pdf-web-editor.md).

### Renomear uma predefinição de condição

Execute as seguintes etapas para renomear uma predefinição de condição:

1. Passe o mouse sobre uma predefinição de condição do painel **Predefinições de condição**.
1. Selecione **Renomear** no menu Opções para abrir a caixa de diálogo **Renomear predefinição de condição**.
1. Edite o nome da predefinição de condição.
1. Clique em **Renomear**.

### Duplicar uma predefinição de condição

Execute as seguintes etapas para duplicar uma predefinição de condição:

1. Passe o mouse sobre uma predefinição de condição do painel **Predefinições de condição**.
1. Selecione **Duplicar** no menu Opções para abrir a caixa de diálogo **Predefinição de condição de duplicação**.
   >[!NOTE]
   >
   > O nome padrão da predefinição é `<selected condition preset name>_1`. Você pode alterar o nome de acordo com suas necessidades.

1. Clique em **Duplicar**.

### Excluir predefinição de condição

Execute as seguintes etapas para excluir predefinições de condição:

1. Passe o mouse sobre uma predefinição de condição do painel **Predefinições de condição**.
1. Selecione **Excluir** no menu Opções para abrir a caixa de diálogo **Excluir predefinição de condição**.
1. Clique em **Excluir**.



## Predefinições de condição no painel de mapa


### Criar uma predefinição de condição

Execute as seguintes etapas para criar uma predefinição de condição:

1. Selecione a guia **Predefinições de condição** no console do mapa DITA.
1. Clique no botão **Criar**.
1. Insira um nome para a predefinição em **Condição de Nome**.
1. Selecione uma das seguintes ações padrão no menu suspenso **Definir ação padrão como**:

   * Incluir
   * Excluir
   * Passagem
   * Sinalizador
A ação é definida como ação padrão para todos os atributos, sejam eles adicionados à predefinição de condição ou não.

   Por exemplo, você tem 15 atributos de condição no documento e incluiu quatro deles na predefinição de condição. Se você selecionar **excluir** como ação padrão, ela será aplicada a todos os 15 atributos.

1. Siga qualquer um destes procedimentos para adicionar os atributos:
   * Clique em **Adicionar** a um atributo para a predefinição de condição. Você pode repetir essa etapa para adicionar mais atributos.
   * Clique em **Adicionar tudo** para adicionar todos os atributos à predefinição de condição.
1. \(Opcional\) Se necessário, é possível substituir a ação padrão aplicada aos atributos na Etapa 4. Siga uma das seguintes opções:
   * Selecione vários atributos, escolha uma ação de **Defina a ação para as condições selecionadas como** e clique em **Aplicar**.
   * Selecione uma ação para um atributo no menu suspenso **Ação**.
1. Clique em **Salvar**.

### Editar uma predefinição de condição

É possível fazer alterações em uma predefinição de condição existente para alterar as ações aplicadas aos atributos na predefinição de condição. Execute as seguintes etapas para editar uma predefinição de condição:

1. Selecione a guia **Predefinições de condição** no console do mapa DITA.
1. Clique no botão **Editar**.
1. Faça as alterações necessárias para todos os atributos na predefinição de condição.
1. Clique em **Salvar**.

### Criar uma cópia de uma predefinição de condição

É possível criar uma cópia de uma predefinição de condição e modificá-la de acordo com suas necessidades. Execute as seguintes etapas para criar uma cópia de uma predefinição de condição:

1. Selecione a guia **Predefinições de condição** no console do mapa DITA.
1. Clique no botão **Duplicar**.

   >[!NOTE]
   >
   > O nome padrão da predefinição é `<selected condition preset name>_Duplicate`

   Você pode alterar o nome de acordo com sua exigência.

1. \(Opcional\) Faça as alterações necessárias para todos os atributos na predefinição de condição.
1. Clique em **Salvar**.

### Excluir predefinição de condição

É possível excluir uma ou mais predefinições de condição da guia **Predefinição de Condição** do console de mapa DITA. Execute as seguintes etapas para excluir predefinições de condição:

1. Selecione a guia **Predefinições de condição** no console do mapa DITA.
1. Selecione a predefinição de condição\(s\) que deseja excluir.
1. Clique no botão **Remover**.
1. Clique em **Remover** para confirmar a ação.

**Tópico pai:**&#x200B;[&#x200B; Geração de saída](generate-output.md)
