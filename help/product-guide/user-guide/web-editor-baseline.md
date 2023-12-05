---
title: Criar e gerenciar linhas de base no Editor da Web
description: Criar e gerenciar linhas de base do editor da Web no AEM Guides. Saiba como criar linhas de base com base em rótulos e aplicar filtros às linhas de base.
exl-id: 14f87bdd-3042-46f9-853e-e9ded81b10ed
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1468'
ht-degree: 0%

---

# Criar e gerenciar linhas de base no Editor da Web {#id223MB0ZF043}

>[!TIP]
>
> É recomendável usar esse recurso de Linha de base do Editor da Web se você tiver atualizado para a versão as a Cloud Service de março do AEM Guides ou posterior.

O Guia AEM fornece o recurso de Linha de base integrado ao Editor da Web, que permite que os usuários criem linhas de base e as usem para publicar ou traduzir tópicos de diferentes versões.

## Criar uma Linha de Base

Você pode criar uma linha de base no Editor da Web executando as seguintes etapas:

1. No painel Repositório, abra o arquivo de mapa DITA na Exibição de mapa.
1. Clique em **Gerenciar** guia. A variável **Linha de base** exibe as linhas de base do mapa DITA.

   ![Painel Linha de base](images/baseline-manage.png){width="800" align="left"}

1. No **Linha de base** clique no ícone + no canto superior direito. Você pode criar uma linha de base com uma versão específica dos tópicos e conteúdo referenciado disponível em uma data e hora específicas, ou com um rótulo definido para uma versão dos tópicos.
1. Insira um nome para a linha de base em **Nome da Linha de Base**.
1. Entrada **Opção de Linha de Base**, você pode escolher **Usar versão do arquivo** ou **Usar rótulos** opção:

   **Usar versão do arquivo**: Você pode criar uma linha de base estática com uma versão específica dos tópicos e conteúdo referenciado disponível em uma data e hora específicas, ou com um rótulo definido para uma versão de tópicos:

   - Entrada **Definir a versão mais recente com base em,** selecione uma das seguintes opções:


      1. **Data** &lt;time stamp=&quot;&quot;>: Seleciona a versão do tópico como na data e hora especificadas.
      1. **Rótulo**: selecione essa opção para escolher os tópicos de acordo com o rótulo aplicado a eles. Se os tópicos tiverem rótulos especificados para eles, eles serão listados na lista suspensa. Você pode escolher um rótulo na lista. Também é possível adicionar um rótulo na caixa de texto.

         Para as referências diretas em linhas de base estáticas, os rótulos são extraídos da versão salva mais recente do mapa. Por exemplo, se você tiver criado rótulos `Label Release 1.0` e `Label Release 1.1` para as versões 1.0 e 1.1 do Tópico A e, em seguida, adicione o Tópico A ao mapa salvo como versão 1.0. Nesse caso, é possível visualizar os rótulos `Label Release 1.0` e `Label Release 1.1` no menu suspenso para rótulos de linha de base estáticos.


         Ao selecionar **Label,** você pode escolher as referências diretas e indiretas.
         - Para referências diretas no mapa DITA, você tem a opção de usar a versão mais recente de tópicos que não têm o rótulo especificado aplicado a eles.

           >[!NOTE]
           >
           > Se você inserir um rótulo que não existe e selecionar a opção **Não criar uma linha de base** em seguida, a criação da linha de base falha e fornece uma mensagem de erro próxima ao nome da linha de base no painel Linha de base.

         - Para referências indiretas no mapa DITA, você tem uma opção adicional para usar a versão mais recente de tópicos que não têm o rótulo especificado aplicado. Você também pode optar por **Escolher Automaticamente** para o conteúdo referenciado, e o sistema escolhe automaticamente a versão do conteúdo referenciado correspondente à versão do conteúdo no qual ele é referenciado.

         Depois de selecionar um rótulo ou uma versão como na data, todos os tópicos e arquivos de mídia referenciados no mapa são selecionados adequadamente. Essa seleção de tópicos não é exibida na interface do usuário, mas é salva no back-end.

   **Usar rótulos**: selecione essa opção para que a criação da linha de base escolha os tópicos de acordo com o rótulo aplicado a eles.

   As linhas de base baseadas em rótulos são atualizadas dinamicamente. Se você gerar uma linha de base, baixar uma linha de base ou criar um projeto de tradução usando uma linha de base, os arquivos serão selecionados dinamicamente com base nos rótulos atualizados. Por exemplo, se você tiver usado a versão 1.2 de um tópico com Rótulo Versão 1.0 para a linha de base e a versão mais recente atualizada 1.5 com Rótulo Versão 1.0, a linha de base será atualizada dinamicamente e a versão 1.5 será usada.

   ![Criar uma linha de base](images/dynamic-baseline.png){width="550" align="left"}

   - **Selecionar rótulos**: Se os tópicos tiverem rótulos especificados para eles, os rótulos serão listados na **Selecionar rótulos** lista suspensa. Você pode escolher o rótulo\(s\) na lista. Os rótulos selecionados primeiro recebem prioridade mais alta sobre os posteriores.

     Para linhas de base dinâmicas, os rótulos são extraídos da versão salva mais recente e da cópia de trabalho atual do mapa. Por exemplo, se você tiver criado rótulos   `Label Release A.1.0 ` e `Label Release A.1.1` para as versões 1.0 e 1.1 do Tópico A e rótulos `Label Release B.1.0` e `Label Release B.1.1` para as versões 1.0 e 1.1 do Tópico B. Em seguida, você pode adicionar o Tópico A ao Mapa A na versão 1.0 e o Tópico B ao Mapa A no 1.0* (cópia de trabalho). Nesse caso, você pode exibir  `Label Release A.1.0 `, `Label Release A.1.1`, `Label Release B.1.0`, e `Label Release B.1.1` na lista suspensa de rótulos de linha de base dinâmicos.

1. **Referências indiretas**: para referências indiretas no mapa DITA, você recebe as seguintes opções:

   - **Escolher automaticamente**: você pode optar por **Escolher Automaticamente** para o conteúdo referenciado, e o sistema escolhe automaticamente a versão do conteúdo referenciado correspondente à versão do conteúdo no qual ele é referenciado.

   - **Usar rótulo selecionado**: é possível criar uma linha de base com o rótulo selecionado definido para uma versão de tópicos.
   - **Usar a versão mais recente ou a cópia de trabalho**: Use a versão mais recente dos tópicos que não têm o rótulo especificado aplicado ou, se nenhuma versão tiver sido criada, use a cópia de trabalho dos tópicos para criar a linha de base.
1. Clique em **Aplicar**.

A linha de base é criada. A criação da linha de base ocorre de forma assíncrona, para que você possa continuar trabalhando em outros arquivos no Editor da Web. Depois que a linha de base é criada, uma mensagem pop-up é exibida confirmando que a linha de base foi criada, e você também recebe uma notificação da Caixa de entrada para a mesma linha.

## Gerenciar linhas de base

Você pode gerenciar suas linhas de base existentes usando os vários recursos no painel Linha de Base.

- Você pode pesquisar uma linha de base existente usando a caixa de texto no painel Linha de base. Use o **Aplicar filtro** ícone para mostrar todas as linhas de base ou listar as linhas de base com o status de criação como Bem-sucedido, Em Andamento ou Falha.
- Use o **Atualizar** ícone no painel Linha de Base para verificar novamente todas as linhas de base e exibir uma nova lista de linhas de base para o mapa DITA aberto na Exibição de Mapa.
- Você pode exibir ou editar o conteúdo de uma linha de base estática existente clicando duas vezes na linha de base na lista do painel Linha de base. A janela de edição da linha de base no centro exibe o arquivo de mapa DITA, o conteúdo do mapa ou os tópicos e o conteúdo referenciado.


  ![opções de uma linha de base](images/baseline-options.png){width="800" align="left"}



  Você também pode executar as seguintes operações na linha de base a partir do menu Opções:

- **Editar**, **Duplicar,** **Renomear** ou **Excluir** uma linha de base existente.

  >[!NOTE]
  >
  >A operação de edição para linhas de base estáticas só é recomendada para um pequeno número de alterações de referência. A operação de edição não é recomendada para alterar a versão do mapa DITA principal, pois deve recalcular todas as referências. Isso pode causar uma falha de atualização de linha de base para mapas DITA grandes. Para os mapas DITA maiores, é possível criar uma nova linha de base ou editar as propriedades da linha de base.
  >
  >Editar operação no caso de linha de base dinâmica permite editar as propriedades da linha de base, pois as referências para linhas de base dinâmicas são geradas no tempo de execução usando os rótulos.

- Adicionar, remover ou fazer alterações em rótulos existentes do **Gerenciar rótulos** opção para linhas de base estáticas. Se o administrador tiver configurado rótulos predefinidos, esses rótulos serão exibidos na lista suspensa Adicionar rótulo. Para obter mais informações sobre como adicionar rótulos, consulte [Usar rótulos](web-editor-use-label.md#).

  >[!NOTE]
  >
  > O processo para adicionar ou remover rótulos ocorre de forma assíncrona, para que você possa continuar trabalhando em outros arquivos no Editor da Web. Depois que o rótulo é adicionado ou removido, uma mensagem pop-up é exibida confirmando que o rótulo foi adicionado ou removido, e você também recebe uma notificação da Caixa de entrada para o mesmo.

- **Editar propriedades** de uma linha de base estática existente que você definiu ao criar a linha de base.
- Exporte o instantâneo de uma linha de base em um arquivo do Microsoft Excel com o **Exportar Linha de Base** opção.

**Filtros da linha de base**

Uso do ícone Filtros no **Filtros da linha de base** painel é possível aplicar filtros na linha de base aberta na janela de edição da linha de base:

![filtros da linha de base](images/baseline-filter.png){width="300" align="left"}

- Filtre os arquivos com base nos nomes ou no local dos arquivos.
- Filtre os arquivos com base nos valores de diferentes colunas, como Tipo de arquivo, Tipo de referência e assim por diante.
- Escolha as colunas a serem exibidas na janela de edição da linha de base.

>[!NOTE]
>
> Você pode clicar em um cabeçalho de coluna e classificar os arquivos com base nas colunas na janela de edição da linha de base.

**Salvar ou Redefinir uma Linha de Base**

Depois de editar a linha de base, você pode clicar no link **Salvar** botão na parte superior para salvar as alterações na linha de base. Você pode clicar no link **Redefinir** se não quiser salvar a alteração e redefinir a linha de base. Ao clicar no botão **Redefinir** botão, um aviso será exibido informando que as alterações não salvas serão perdidas.

**Tópico pai:**[ Trabalhar com o editor da Web](web-editor.md)
