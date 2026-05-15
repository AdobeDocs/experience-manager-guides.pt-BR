---
title: Criar um projeto DITA
description: Crie um projeto DITA usando um modelo no AEM Guides. Saiba como usar um projeto DITA para iniciar as revisões.
feature: Reviewing
role: User
hide: true
exl-id: 1b29c50a-04d0-4052-b893-44fb8bcc3c97
TQID: https://experienceleague.adobe.com/7MU9ThZrrkJ1owYxDxKztHnadVb27Jk5Hhvst2NiQl8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 472
ht-degree: 0%

---

# Criar um projeto DITA {#id1645HA00NM6}

O AEM Guides fornece um modelo de projeto DITA que você pode usar para criar e gerenciar suas tarefas de revisão.

Você pode criar um projeto DITA e usá-lo para iniciar suas revisões. Um projeto permite definir um prazo e controlar as tarefas e o tempo necessário para concluir a tarefa de revisão para a qual você criou o projeto.

Você pode adicionar membros da equipe a um projeto, aos quais poderão ser atribuídas várias funções - Autores, Revisores e Editores.

Depois de criar o projeto DITA, você pode iniciar a revisão no Editor da Web ou na interface do Assets. Para obter mais detalhes, consulte [Enviar tópicos para revisão](review-send-topics-for-review.md#).

Da mesma forma, sempre que um autor inicia qualquer fluxo de trabalho de revisão, os membros selecionados do projeto recebem uma notificação por email. Para configurar notificações por email, consulte *Personalizar modelos de email* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

Execute as seguintes etapas para criar um projeto DITA:

1. Abra o console Projetos.

   Você também pode acessar o console de Projetos usando o seguinte URL:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Clique em **Criar** \> **Projeto** para iniciar o assistente Criar Projeto.

   ![](images/project-console-63.png){width="650"}

1. Na página Criar projeto, selecione o modelo **Projeto DITA** e clique em **Avançar**.

1. Na página Propriedades do projeto, insira os seguintes detalhes:

   Informações na guia **Básico**:

   ![](images/create-project.png){width="650"}

   - Insira o **Título**, **Descrição** e **Data de Conclusão** do seu projeto.

   - Você pode, opcionalmente, escolher uma miniatura para o projeto.

   - Por padrão, você se torna o proprietário do projeto. Para adicionar mais usuários a este projeto:

   1. Insira ou escolha um usuário na lista suspensa **Usuário**.

   1. Escolha um tipo de usuário - Autores, Revisores ou Editores.

      >[!NOTE]
      >
      >Você verá outros tipos de usuários nessa lista suspensa, mas para um projeto DITA, você só deve escolher entre os tipos de usuários Autores, Revisores ou Editores. Mesmo que você adicione um usuário de um tipo diferente, ele não poderá acessar nenhum recurso específico de DITA disponível no AEM Guides.

   1. Clique em **Adicionar**.

      >[!NOTE]
      >
      >Se estiver usando o AEM Guides versão 3.5 ou anterior, você verá uma opção para selecionar um arquivo de mapa DITA para resolver referências principais para edição de tópicos, visualização e fluxos de trabalho de revisão. Nas versões 3.6 e posteriores, é possível definir o mapa raiz por meio do Editor da Web. Para obter mais informações, consulte as [Preferências do Usuário](web-editor-features.md#id2087G0P40SB) no Editor da Web. Outra maneira de definir o mapa raiz é configurando-o nos perfis globais ou de nível de pasta. Para obter mais detalhes, consulte *Configurar perfis globais ou de nível de pasta* no Guia de Instalação e Configuração.

   Informações na guia **Avançado**:

   - Insira um nome para o projeto. Esse nome é usado para criar o URL desse projeto.

1. Clique em **Criar**.

   A caixa de diálogo Projeto criado é exibida.

1. Clique em **Abrir** para abrir a página do projeto.


**Tópico pai:**[ Tópicos ou mapas de revisão](review.md)
