---
title: Criar um projeto DITA
description: Crie um projeto DITA usando um modelo nos Guias do AEM. Saiba como usar um projeto DITA para iniciar as revisões.
exl-id: 0cd83fe3-1764-4f04-ae11-0b71b6ac576c
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# Criar um projeto DITA {#id1645HA00NM6}

O Guia AEM fornece um modelo de projeto DITA que pode ser usado para criar e gerenciar as tarefas de revisão.

Você pode criar um projeto DITA e usá-lo para iniciar suas revisões. Um projeto permite definir um prazo e controlar as tarefas e o tempo necessário para concluir a tarefa de revisão para a qual você criou o projeto.

Você pode adicionar membros da equipe a um projeto, aos quais poderão ser atribuídas várias funções - Autores, Revisores e Editores.

Depois de criar o projeto DITA, você pode iniciar a revisão no Editor da Web ou na interface do usuário do Assets. Para obter mais detalhes, consulte [Enviar tópicos para revisão](review-send-topics-for-review.md#).

Da mesma forma, sempre que um autor inicia qualquer fluxo de trabalho de revisão, os membros selecionados do projeto recebem uma notificação por email. Para configurar notificações por email, consulte *Personalizar modelos de email* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

Execute as seguintes etapas para criar um projeto DITA:

1. Abra o console Projetos.

   Você também pode acessar o console de Projetos usando o seguinte URL:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Clique em **Criar** \> **Projeto** para iniciar o assistente Criar projeto.

   ![](images/project-console-63.png){width="650" align="left"}

1. Na página Criar projeto, selecione a **Projeto DITA** e clique em **Próxima**.

1. Na página Propriedades do projeto, insira os seguintes detalhes:

   Informações na **Básico** guia:

   ![](images/create-project.png){width="650" align="left"}

   - Insira o do seu projeto **Título**, **Descrição**, e **Prazo**.

   - Você pode, opcionalmente, escolher uma miniatura para o projeto.

   - Por padrão, você se torna o proprietário do projeto. Para adicionar mais usuários a este projeto:

   1. Insira ou escolha um usuário no **Usuário** lista suspensa.

   1. Escolha um tipo de usuário - Autores, Revisores ou Editores.

      >[!NOTE]
      >
      >Você verá outros tipos de usuários nessa lista suspensa, mas para um projeto DITA, você só deve escolher entre os tipos de usuários Autores, Revisores ou Editores. Mesmo que você adicione um usuário de um tipo diferente, ele não poderá acessar nenhum recurso específico de DITA disponível nos Guias do AEM.

   1. Clique em **Adicionar**.

      >[!NOTE]
      >
      >Se estiver usando Guias AEM versão 3.5 ou anterior, você verá uma opção para selecionar um arquivo de mapa DITA para resolver referências principais para edição de tópicos, visualização e fluxos de trabalho de revisão. Nas versões 3.6 e posteriores, é possível definir o mapa raiz por meio do Editor da Web. Para obter mais informações, consulte [Preferências do usuário](web-editor-features.md#id2087G0P40SB) no Editor da Web. Outra maneira de definir o mapa raiz é configurando-o nos perfis globais ou de nível de pasta. Para obter mais detalhes, consulte *Configurar perfis globais ou de nível de pasta* no Guia de instalação e configuração.

   Informações na **Avançado** guia:

   - Insira um nome para o projeto. Esse nome é usado para criar o URL desse projeto.

1. Clique em **Criar**.

   A caixa de diálogo Projeto criado é exibida.

1. Clique em **Abertura** para abrir a página do projeto.


**Tópico pai:**[ Revisar tópicos ou mapas](review.md)
