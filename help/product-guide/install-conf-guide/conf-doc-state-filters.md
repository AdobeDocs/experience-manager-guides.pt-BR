---
title: Configurar filtros de estado do documento
description: Saiba como configurar filtros de estado do documento
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 6dee8479-770f-48d7-9939-5035388d16d8
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Configurar filtros de estado do documento para o Cloud Service

O Adobe Experience Manager Guides fornece o recurso para pesquisar um arquivo com base em seu estado de documento atual. Você pode usar a pesquisa de filtro para pesquisar arquivos na interface do repositório para procurar arquivos.

Execute as seguintes etapas para configurar os filtros de estado do documento:

1. Faça logon no Adobe Experience Manager como Administrador.
1. Selecione o link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e selecione **Perfis de Pasta**.
1. Abra o bloco **Perfil Global**. Você também pode selecionar um bloco de perfil de pasta específico se quiser que essas alterações sejam aplicadas somente a essa pasta, em vez de globalmente.
1. Navegue até **Configuração do Editor de XML**.
1. Selecione o ícone **Editar** na parte superior.
1. Selecione o ícone **Baixar** para baixar o arquivo `ui\_config.json` no sistema local.
No arquivo `ui\_config.json` baixado, consulte a seguinte seção:

   ```
   "repositoryFilters": [
       {
       "title": "Document state",
       "property": "jcr:content/metadata/docstate",
       "children": [
           {
           "title": "Draft",
           "value": "Draft"
           },
           {
           "title": "Edit",
           "value": "Edit"
           },
           {
           "title": "In-Review",
           "value": "In-Review"
           },
           {
           "title": "Approved",
           "value": "Approved"
           },
           {
           "title": "Reviewed",
           "value": "Reviewed"
           },
           {
           "title": "Done",
           "value": "Done"
           }
       ]
       }
   ]
   ```

   Este trecho representa os filtros de estado de documento padrão disponíveis no Experience Manager Guides.

1. Você pode personalizar os valores de filtro com base no fluxo de trabalho da sua organização. Por exemplo, para adicionar um estado de documento personalizado **Pendente**, insira a seguinte entrada em `children`:

   ```
   {
       "title": "Pending",
       "value": "Pending"
   }
   ```

1. Depois de atualizado, salve o arquivo e faça upload dele.

Os filtros configurados são exibidos no painel **Filtros** em Repositório, na Home page.

**Tópico pai:**[ Personalizar editor](customize-overview.md)
