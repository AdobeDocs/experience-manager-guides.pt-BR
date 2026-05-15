---
title: Iniciar o Editor da Web
description: Saiba como iniciar o editor da Web na página de navegação do AEM, na interface do usuário do AEM Assets e no console de mapas DITA no AEM Guides.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 374042e4-0f1c-44cf-926c-c9fefa4b1de0
TQID: https://experienceleague.adobe.com/O-rew8ysArVVeDpj3T7oEi-hEg-phDWzb85gD2l-9gQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 592
ht-degree: 0%

---

# Iniciar o Editor da Web {#id2056B0140HS}

Você pode iniciar o Editor da Web nos seguintes locais:

- [Página de navegação do AEM](#id2056BG00RZJ)
- [Interface do usuário do AEM Assets](#id2056BG0307U)
- [Console de mapa DITA](#id2056BG090BF)

As seções a seguir abordam os detalhes de como você pode acessar e iniciar o Editor da Web a partir de vários locais.

## Página de navegação do AEM {#id2056BG00RZJ}

Ao fazer logon no AEM, você verá a página Navegação:

![](images/web-editor-from-navigation-page.png){width="800"}

Ao clicar no link **Guias**, você será direcionado diretamente para o Editor da Web.

![](images/web-editor-launch-page.png){width="800"}

Como você iniciou o Editor da Web sem selecionar nenhum arquivo, uma tela em branco do Editor da Web é exibida. Abra um arquivo para edição no repositório do AEM ou em sua coleção Favoritos.

- Clique no ícone **Guias** (![](images/aem-guides-icon.png) ) para voltar para a página Navegação do AEM.

- O botão **Fechar** leva você a um destino com base em sua configuração:



  <details>

  <summary> Cloud Services </summary>

  Se você estiver usando o Cloud Services, clique no botão **Fechar** para voltar para a página Navegação do AEM.
  </details>

  <details>

  <summary> Software local</summary>

  Se você estiver usando o AEM Guides On-premise Software (4.2.1 e posterior), clique no botão **Fechar** à direita para voltar ao caminho do arquivo atual na interface do usuário do Assets.

  </details>

## Interface do usuário do AEM Assets {#id2056BG0307U}

Outro local onde você pode iniciar o Editor da Web é na interface do usuário do AEM Assets. Você pode selecionar um ou mais tópicos e abri-los diretamente no Editor da Web. Para abrir um tópico no Editor da Web, siga estas etapas:

1. Na interface do usuário do Assets, navegue até o tópico que deseja editar.

   >[!NOTE]
   >
   > Você também pode ver a UUID do tópico.

   .

   ![](images/assets_ui_with_uuid_cs.png){width="800"}

   >[!IMPORTANT]
   >
   > Certifique-se de que você tenha as permissões de leitura e gravação na pasta que contém o tópico que deseja editar.

1. Para obter um bloqueio exclusivo sobre o tópico, selecione o tópico e clique em **Fazer Check-out**.

   >[!IMPORTANT]
   >
   > Se o administrador tiver configurado a opção **Desabilitar Edição Sem Check-out**, você deverá fazer check-out do arquivo antes de editar. Se não fizer check-out do arquivo, você não poderá ver a opção de edição.

1. Feche o modo de seleção de ativos e clique no tópico que deseja editar.

   A visualização do tópico é exibida.

   Você pode abrir o Editor da Web na exibição em Lista, na exibição Cartão e no modo de Visualização.

   >[!IMPORTANT]
   >
   > Se quiser abrir vários tópicos para edição, selecione os tópicos desejados na interface do usuário do Assets e clique em Editar. Certifique-se de que o navegador não tenha o bloqueador de pop-ups ativado, caso contrário, somente o primeiro tópico na lista selecionada será aberto para edição.

   ![](images/edit-from-preview_cs.png){width="800"}

   Se não quiser visualizar um tópico e quiser abri-lo diretamente no Editor da Web, clique no ícone Editar no menu de ação rápida da exibição de cartão:

   ![](images/edit-topic-from-quick-action_cs.png){width="800"}

1. Clique em **Editar** para abrir o tópico no Editor da Web.

   ![](images/edit-mode.png){width="800"}


## Console de mapa DITA {#id2056BG090BF}

Para abrir o Editor da Web no console de mapa DITA, siga estas etapas:

1. Na interface do usuário do Assets, navegue até o arquivo de mapa DITA que contém o tópico que deseja editar e clique nele.

   O console do mapa DITA é exibido.

1. Clique em **Tópicos**.

   Uma lista de tópicos no arquivo de mapa é exibida. A UUID dos tópicos é exibida abaixo do título do tópico.

1. Selecione o arquivo de tópico que deseja editar.

1. Clique em **Editar tópico**.

   ![](images/edit-topics-map-console_cs.png){width="800"}

1. O tópico é aberto no Editor da Web.

   >[!IMPORTANT]
   >
   > Se o administrador tiver configurado a opção **Desabilitar Edição Sem Check-out**, você deverá fazer check-out do arquivo antes de editar. Se você não fizer check-out do arquivo, o documento será aberto no editor no modo somente leitura.


**Tópico pai:**&#x200B;[&#x200B; Trabalhar com o Editor da Web](web-editor.md)
