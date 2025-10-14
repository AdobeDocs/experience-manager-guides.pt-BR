---
title: Criar tópicos
description: Saiba como criar tipos de tópicos DITA usando modelos personalizados no Adobe Experience Manager Guides.
exl-id: 84e9cfdf-e188-487f-9181-68708029c101
feature: Authoring
role: User
source-git-commit: c6709ffb8e415c88931e732456e2f2a5e6b63729
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Criar tópicos {#id2056AL00O5Z}

O Adobe Experience Manager Guides permite criar tópicos DITA do tipo — tópico, tarefa, conceito, referência, glossário, DITAVAL, Markdown e muito mais. Além de criar tópicos com base nos modelos prontos para uso, também é possível definir seus modelos personalizados. Esses modelos devem ser adicionados ao perfil da pasta para serem exibidos no Blueprint de seleção de modelo e no Editor.

>[!NOTE]
>
> A configuração Global e Perfil de pasta está disponível somente para usuários administrativos no nível da pasta. Para obter detalhes sobre como configurar perfis globais e de nível de pasta, consulte *Configurar modelos de criação* em Instalar e configurar o Adobe Experience Manager Guides para sua configuração.


Há duas maneiras de criar tópicos no Experience Manager Guides:

- [Criar tópicos no Editor](#create-topics-from-the-editor)
- [Criar tópicos na interface do usuário do Assets](#create-topics-from-the-assets-ui)

## Criar tópicos no Editor

Execute as seguintes etapas para criar um tópico a partir do Editor:

1. No painel Repositório, selecione o ícone **Novo arquivo** e selecione **Tópico** no menu suspenso.

   ![](images/create-topic-option.png){width="500" align="left"}

   Você também pode acessar esta opção a partir da [Página inicial do Experience Manager Guides](./intro-home-page.md) e do menu de opções de uma pasta na exibição Repositório.

2. A caixa de diálogo **Novo tópico** é exibida.

3. Na caixa de diálogo **Novo tópico**, forneça os seguintes detalhes:
   - Um Título para o tópico.
   - \(Opcional\)* O nome do arquivo do tópico. O nome do arquivo é sugerido automaticamente com base no tópico Título. Caso o administrador tenha ativado nomes de arquivo automáticos com base na configuração UUID, você não visualizará o campo Nome.
   - Um modelo no qual o tópico será baseado. Por exemplo, para uma configuração pronta para uso, você pode escolher entre os modelos Em branco, Conceito, DITAVAL, Referência, Tarefa, Tópico, Markdown, Glossário e Solução de problemas. Se a pasta tiver um Perfil de Pasta configurado, você visualizará somente os modelos de tópico configurados no perfil de Pasta.
   - Caminho no qual você deseja salvar o arquivo de tópico. Por padrão, o caminho da pasta selecionada no momento no repositório é mostrado no campo Caminho.

4. Selecione **Criar**.

   ![](images/create-topic-dialog-new.png){width="300" align="left"}

O tópico é criado no caminho especificado. Além disso, o tópico é aberto no Editor para edição.

![](images/new-topic-editor.png){align="left"}

## Criar tópicos na interface do usuário do Assets

Execute as seguintes etapas para criar um tópico na interface do usuário do Assets:

1. Na interface do usuário do Assets, navegue até o local em que deseja criar o tópico.

1. Para criar um novo tópico, selecione **Criar** \> **Tópico DITA**.

1. Na página Blueprint, selecione o tipo de documento DITA que você deseja criar e selecione **Próximo**.

   ![](images/create_dita_topic.png){align="left"}

   Por padrão, o Experience Manager Guides fornece os modelos de tópicos DITA mais usados. Você pode configurar mais modelos de tópico de acordo com seus requisitos organizacionais, exibir *Configurar modelos de criação* em Instalar e configurar o Adobe Experience Manager Guides para sua configuração.

   >[!NOTE]
   >
   > Na exibição de lista da interface do Assets, o tipo de tópico DITA é mostrado na coluna Tipo como Tópico, Tarefa, Conceito, Referência, Glossentry, Markdown ou DITAVAL. O mapa DITA é exibido como Map.

1. Na página Propriedades, especifique o documento **Título**.

1. \(Opcional\) Especifique o arquivo **Nome**.

   Se o administrador tiver configurado o nome de arquivo automático com base na configuração UUID, você não visualizará a opção para especificar o nome do arquivo. Um nome de arquivo baseado em UUID é automaticamente atribuído ao arquivo.

   Se a opção de nomenclatura de arquivo estiver disponível, então o nome também será sugerido automaticamente com base no **Título** do seu documento. Se você quiser especificar manualmente o nome do documento, certifique-se de que **Name** não contenha espaços, apóstrofo ou chaves e termine com .xml ou .dita. Por padrão, o Experience Manager Guides substitui todos os caracteres especiais por hifens. Consulte a seção Nomes de arquivos no Guia de práticas recomendadas para obter as práticas recomendadas sobre a nomeação de arquivos DITA.

1. Selecione **Criar**. A mensagem Topic Created (Tópico criado) é exibida.

   Você pode optar por abrir o tópico para edição no Editor ou salvar o arquivo de tópico no repositório do Adobe Experience Manager.

**Informações adicionais**

1. Todo tópico novo criado na interface do usuário do Assets **Criar** \> **Tópico DITA** ou no Editor recebe uma ID de tópico exclusiva. O valor dessa ID é o próprio nome do arquivo. Além disso, um novo documento é salvo como a cópia de trabalho mais recente do tópico no DAM. Até salvar uma revisão de um tópico recém-criado, você não exibirá nenhum número de versão no Histórico de versões. Se você abrir o tópico para edição, as informações da versão serão mostradas no canto superior direito da barra de ferramentas:

   ![](images/topic-version-none_cs.png){width="550" align="left"}

2. As informações de versão de um tópico recém-criado são mostradas como *nenhuma*. Ao salvar uma nova versão, um número de versão é atribuído como 1.0.

3. Se o administrador tiver configurado o Editor para bloquear arquivos antes de editar, você não poderá editar um arquivo até bloqueá-lo. Da mesma forma, se configurado, você será solicitado a desbloquear qualquer arquivo bloqueado antes de fechá-lo.

4. Depois de criar o tópico DITA, continue salvando as alterações na sua cópia de trabalho e crie uma nova versão após concluir as atualizações do tópico.

**Tópico pai:**&#x200B;[&#x200B; Criar e visualizar tópicos](create-preview-topics.md)
