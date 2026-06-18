---
title: Remover a opção "Excluir" do menu de contexto do arquivo no editor da Web para usuários específicos
description: Saiba como personalizar o editor da Web removendo a opção "Excluir" do menu de contexto do arquivo para usuários/grupos específicos
exl-id: 31b4dd53-3938-42e1-bbc6-64806d668696
TQID: https://experienceleague.adobe.com/dzbMsXUoEibR5QxKB-Z-h4qGnQaX2NmIYLTtxVJHE-A
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 0%

---

# Remover a opção &quot;Excluir&quot; do menu de contexto do arquivo no editor da Web

Neste artigo, aprenderemos como ocultar a opção &quot;Excluir&quot; no menu de contexto do arquivo no Editor do AEM Guides para usuários ou grupos específicos. Para outras personalizações em opções de menu de contexto de arquivo, verifique a Estrutura de extensão de guias. Mais detalhes podem ser encontrados [aqui](https://github.com/adobe/guides-extension/tree/main).

Como você pode ver abaixo do trecho, o menu de contexto do arquivo tem a opção &quot;Excluir&quot; disponível para este usuário específico.

![Menu de contexto de arquivo com Exclusão](../../../assets/authoring/file-contextmenu-Delete.png)

Agora, vejamos como ocultar a opção &quot;Excluir&quot; para este usuário.

## Etapas da implementação:

- Navegue até Ferramentas > Segurança > Permissões na página inicial do AEM.
- Escolha o grupo ou usuário na caixa de pesquisa.
- Clique em &quot;Adicionar ACE&quot; no canto superior direito.
- Escolha o caminho da pasta.
- Inclua os privilégios &quot;jcr:removeChildNodes&quot; e &quot;jcr:removeNode&quot;.
- Escolha &quot;Tipo de permissão&quot; como &quot;negar&quot; e clique em &quot;Adicionar&quot; conforme mostrado abaixo.

![ACE de Negação de Permissão de Usuário](../../../assets/authoring/permission-ACE-Delete.png)

![Lista de controle de acesso em permissões](../../../assets/authoring/delete-acl.png)

### Testes

- Faça logon no AEM como o usuário para o qual a ACE foi adicionada.
- Abra o editor da Web.
- Vá para a visualização de repositório e escolha a pasta para a qual as ACEs foram adicionadas.
- Abra o menu de contexto do arquivo.
- A opção &#39;Excluir&#39; não aparecerá no menu de contexto.

O menu de contexto do arquivo agora terá esta aparência:

![Menu de contexto de arquivo sem Excluir](../../../assets/authoring/file-contextmenu-Delete-removed.png)

```
Please note that these steps would also remove 'move' and 'rename' options from the Editor as they are also tied to delete process at the backend.
```
