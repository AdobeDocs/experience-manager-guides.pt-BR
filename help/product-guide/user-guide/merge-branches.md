---
title: Mesclar ramificações de um mapa DITA | EXPERIENCE MANAGER GUIDES
description: Saiba como mesclar alterações de uma ramificação de um mapa DITA na ramificação principal e resolver conflitos de mesclagem no Experience Manager Guides.
TQID: https://experienceleague.adobe.com/pg9zeEg8m3NeDbN-j945SqPbaMX0GgBmuquAsQcrjOM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: ec4263d9-bf7c-44c7-b3f1-3e664861c8f2
    internal-label: Generative AI
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: 278cc3c433085c34d3e7cd3cdbedf482c8200567
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 0%
---
# Mesclar uma ramificação à principal

No Experience Manager Guides, você pode mesclar alterações de uma ramificação de um mapa DITA na ramificação `main`. A mesclagem permite incorporar atualizações concluídas na documentação do `main` sem copiar manualmente as alterações no `main`.

Por exemplo, considere um mapa DITA chamado `install-the-lift.ditamap` com uma ramificação chamada `Release 2`. Os autores podem atualizar as instruções de instalação nesta ramificação enquanto a documentação existente permanece inalterada no `main`.

Quando as atualizações estiverem prontas, os autores poderão mesclar as alterações de `Release 2` em `main`.

## Entender a mesclagem de ramificações

A mesclagem traz alterações de uma ramificação selecionada de um mapa DITA para a ramificação `main`.

- **Ramificação do Source:** a ramificação que contém as alterações que você deseja mesclar.
- **Ramificação de destino:** a ramificação padrão (`main`) na qual as alterações são mescladas.

Se a mesma parte de um tópico/mapa tiver sido modificada em ambas as ramificações, podem ocorrer conflitos de mesclagem que exigem resolução.

## Mesclar uma ramificação

Você pode mesclar alterações de uma ramificação selecionada de um mapa DITA em `main`.

Para mesclar uma ramificação, execute as seguintes etapas:

1. Abra o mapa DITA necessário no console Mapa.
2. Navegue até a guia **Ramificações**.
3. Localize a ramificação que contém as alterações que você deseja mesclar.
4. Abra o menu **Opções** da ramificação e selecione **Mesclar para principal**.

   ![](./images/merge-into-main.png)

   Uma solicitação de mesclagem é criada para a ramificação selecionada. Ele permite que você revise as alterações e resolva quaisquer conflitos antes de mesclá-los no `main`.

   ![](./images/merge-request-created.png)

5. Selecione a solicitação de mesclagem.

   A solicitação de mesclagem é aberta na exibição **Merge branch**. Revise as alterações e resolva os conflitos, se necessário.
6. Conclua a mesclagem.

   Revise as alterações e resolva os conflitos, se necessário. Para obter mais informações, consulte [Resolver conflitos de mesclagem](#resolve-merge-conflicts).

   Depois que todos os conflitos forem resolvidos, selecione **Mesclar tudo** para mesclar as alterações em `main`.

   As alterações são mescladas na ramificação `main`.

## Resolver conflitos de mesclagem

Um conflito de mesclagem ocorre quando o mesmo conteúdo foi modificado em `main` e na ramificação que está sendo mesclada. Você deve resolver todos os conflitos antes de mesclar as alterações em `main`.

Quando você abre uma solicitação de mesclagem, as seguintes seções são exibidas na exibição **Ramificação de mesclagem**:

![](./images/merge-branch-view.png)

- **Conflitos:** Lista os arquivos que exigem resolução de conflitos.
- **Limpar atualizações:** Lista os arquivos que podem ser mesclados sem resolver conflitos.

Para arquivos com conflitos, é exibida uma exibição **Mesclar ramificação**.

![](./images/merge-conflicts.png)

A exibição **Mesclar ramificação** contém os seguintes painéis:

- **Painel esquerdo (principal):** Exibe o conteúdo da ramificação padrão (`main`).
- **Painel do meio (Mesclado):** Exibe o conteúdo mesclado, onde você pode aceitar as alterações de qualquer ramificação ou editar o conteúdo diretamente.
- **Painel direito (ramificação selecionada):** Exibe o conteúdo da ramificação que está sendo mesclada em `main`.

As diferenças são destacadas nos painéis esquerdo e direito com base no conteúdo do painel **Mesclado**:

- **Vermelho (-):** Indica o conteúdo presente no painel **Mesclado** que difere do conteúdo no painel esquerdo ou direito correspondente.
- **Verde (+):** indica o conteúdo presente no painel esquerdo ou direito que não está incluído no painel **Mesclado**.

Inicialmente, o painel **Mesclado** contém o mesmo conteúdo que `main`, portanto, as diferenças são realçadas no painel direito. Depois que você aceitar as alterações da ramificação selecionada, o painel esquerdo mostrará diferenças em comparação com o painel **Mesclado** atualizado.

Execute as seguintes etapas para resolver conflitos de mesclagem:

1. Na seção **Conflitos**, selecione o arquivo que contém conflitos.

   >[!NOTE]
   >
   > Os arquivos listados em **Limpar atualizações** contêm alterações feitas apenas na ramificação selecionada e, portanto, não exigem resolução de conflitos.

2. Revise as diferenças destacadas na exibição **Ramificação de mesclagem** e resolva os conflitos usando os controles de mesclagem.

   A caixa de seleção ao lado de um conflito no painel direito determina como o conteúdo da ramificação selecionada é adicionado ao painel **Mesclado**:

   - **Selecionado (padrão):** substitui o conteúdo correspondente no painel **Mesclado** pelo conteúdo de ramificação selecionado.
   - **Limpo:** Adiciona o conteúdo da ramificação selecionada ao lado do conteúdo existente no painel **Mesclado** sem substituí-lo.

   Você pode resolver conflitos usando as seguintes opções:

   - Se quiser usar as alterações da ramificação selecionada, mantenha a caixa de seleção referente ao conflito selecionada e selecione o controle de seta para a esquerda correspondente (`<<<`). O conteúdo da ramificação selecionada substitui o conteúdo conflitante no painel **Mesclado**.

     ![](./images/replace-content-accept.png)

   - Se quiser manter o conteúdo de ambas as ramificações, desmarque a caixa de seleção referente ao conflito e selecione o controle de seta para a esquerda (`<<<`). Isso adiciona o conteúdo da ramificação selecionada ao painel **Mesclado** sem substituir o conteúdo já presente nesse painel.

     ![](./images/keep-both-versions.png)

   - Se você aceitou alterações da ramificação selecionada e deseja restaurar o conteúdo correspondente de `main`, selecione o controle de seta para a direita (`>>>`) no painel esquerdo. Isso substitui o conteúdo selecionado no painel **Mesclado** pela versão de `main`.

   >[!TIP]
   >
   > Passe o mouse sobre um controle de seta para ver como a aceitação da alteração selecionada afetará o painel **Mesclado**.

3. Depois de revisar o conteúdo mesclado, você também pode usar uma das seguintes opções para aceitar todo o conteúdo de qualquer ramificação:

   - **Aceitar principal:** substitui o conteúdo do painel **Mesclado** para o arquivo selecionado pela versão de `main`.
   - **Aceitar [nome da ramificação]:** substitui o conteúdo no painel **Mesclado** para o arquivo selecionado pela versão da ramificação selecionada.

   >[!NOTE]
   >
   > Selecionar qualquer uma das opções substituirá todo o conteúdo do **Painel mesclado** para o arquivo selecionado, incluindo todas as alterações feitas manualmente durante a resolução de conflitos.

   Como alternativa, você pode revisar ou editar o conteúdo diretamente no painel **Mesclado** e selecionar **Marcar como resolvido** para manter o conteúdo mesclado.

4. Revise o conteúdo final no painel **Mesclado** e selecione **Marcar como resolvido** para marcar o arquivo como resolvido.

5. Repita as etapas para todos os arquivos listados em **Conflitos**.

   Depois que todos os conflitos forem resolvidos, a opção **Mesclar tudo** ficará disponível.

6. Selecione **Mesclar tudo** para mesclar os arquivos resolvidos e as atualizações limpas em `main`.

   >[!NOTE]
   > 
   > A opção **Mesclar tudo** permanece desabilitada até que todos os conflitos sejam resolvidos.

   As alterações resolvidas foram mescladas em `main`. Uma mesclagem concluída não pode ser desfeita. No entanto, é possível criar uma nova solicitação de mesclagem para mesclar as alterações subsequentes no principal.



## Gerenciar uma solicitação de mesclagem

É possível gerenciar solicitações de mesclagem existentes usando o menu de contexto.

Para gerenciar uma solicitação de mesclagem, abra o menu de contexto e selecione uma das seguintes opções:

- **Visualização:** mostra as alterações na solicitação de mesclagem sem mesclá-las.
- **Exibir log:** Exiba o log associado à solicitação de mesclagem.
- **Excluir:** exclua a solicitação de mesclagem. A ramificação e suas alterações não são afetadas.
- **Exibir relatório:** Exibir o relatório de mesclagem após a ramificação ter sido mesclada em `main`.