---
title: Editar tópicos no Editor da Web
description: Saiba como editar tópicos no editor da Web. Saiba mais sobre vários recursos de edição para modificar arquivos de tópico em Guias AEM.
exl-id: 8da37a81-e8c3-434f-b3f4-4723d87c2ade
feature: Authoring, Web Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# Editar tópicos no Editor da Web {#id2056B040VUI}

O Editor da Web vem com uma variedade de recursos de edição que permitem criar ou modificar facilmente seus arquivos de tópico. De modo geral, você executaria as seguintes etapas para editar um tópico no Editor da Web.

>[!IMPORTANT]
>
> Se você encontrar um erro de aplicativo ao trabalhar no Editor da Web, atualize a página para continuar trabalhando.

1. Para fazer alterações no tópico, clique dentro do limite de texto do elemento necessário e comece a fazer edições.

1. Para inserir um elemento específico, clique em no final do elemento após o qual deseja inserir o novo elemento e clique no ícone do elemento necessário na barra de ferramentas. Você também pode usar o atalho de teclado `Alt+Enter` para invocar o **Inserir elemento** pop-up.

   Será exibida uma lista de elementos que podem ser usados no tópico. O AEM Guides faz uma inserção inteligente dos elementos de acordo com sua localização válida no tópico.

   >[!NOTE]
   >
   > Você também pode escolher qual ícone deve ser exibido na barra de ferramentas, configurando o `ui_config.json` arquivo localizado em - `/etc/designs/fmdita/clientlibs/xmleditor/`. Para obter mais informações sobre como personalizar recursos, entre em contato com o administrador do sistema.

1. Quando terminar de editar o documento, clique em **Salvar**.

   >[!NOTE]
   >
   > Se não quiser confirmar as alterações no repositório AEM, clique em **Fechar** e clique em **Fechar sem salvar** no diálogo Alterações não salvas.

   **Atualizar o navegador ao editar os arquivos**
Os Guias do Experience Manager fornecem suporte para atualizar o navegador enquanto você edita seu conteúdo no Editor da Web. Este recurso ajuda você a continuar editando o conteúdo caso encontre um erro no aplicativo durante o trabalho. Se você clicar em Atualizar do navegador enquanto um ou mais arquivos com alterações não salvas estiverem abertos para edição, você será avisado de que as alterações não salvas podem ser perdidas. Você tem a opção de cancelar a operação de atualização e salvar os arquivos para preservar as alterações.

   Mesmo ao atualizar o navegador, as exibições do painel esquerdo e direito são mantidas no Editor da Web. O Experience Manager Guides restaura o último estado salvo dos arquivos abertos no Editor da Web quando você atualiza o navegador. Por exemplo, os arquivos abertos no painel Repositório são abertos novamente. O painel de mapa é mantido junto com o mapa aberto anteriormente.

   O tópico ativo ou mapa DITA é reaberto na área de edição de conteúdo.

   O painel direito também é reaberto e exibe a mesma visualização de antes da atualização.

   **Indicador de cópia de trabalho**
Guias do AEM fornecem o indicador da cópia de trabalho que mostra se a \(cópia de trabalho\) atual do arquivo está sincronizada ou não com a versão salva. Se você tiver alterado sua cópia atual e não tiver salvado o arquivo, uma marca \* será exibida junto com o título na guia do arquivo do tópico. Esse indicador atua como um lembrete para salvar suas alterações e desaparece ao salvar o arquivo.

   ![](images/working-copy-text-update-indicator.png){width="550" align="left"}

   Os Guias do AEM também indicam se a última cópia \(em funcionamento\) salva do arquivo está ou não sincronizada com a versão salva. Se você tiver algumas alterações não salvas entre a cópia de trabalho e a última versão salva, uma marca \* será exibida juntamente com as informações da versão mostradas no canto superior direito da guia Arquivo do tópico. Esse indicador atua como um lembrete para salvar e criar uma versão da sua cópia \(em funcionamento\) atual do arquivo.

   ![](images/version-update-indicator.png){width="550" align="left"}


**Tópico pai:**[ Trabalhar com o editor da Web](web-editor.md)
