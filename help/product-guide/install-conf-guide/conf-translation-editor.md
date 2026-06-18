---
title: Configurar o recurso de tradução no editor
description: Saiba como configurar o recurso de tradução no editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 22d7e1c7-2059-43fb-b7aa-3ae4a6072678
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---

# Configurar o recurso de tradução no editor do Cloud Service

O Editor fornece um recurso avançado de tradução para traduzir o conteúdo em vários idiomas.

Você pode usar a guia **Gerenciar** no Editor para traduzir o conteúdo. Essa guia está disponível por padrão.

Para ocultar a guia **Gerenciar** no Editor, execute as seguintes etapas:

1. Faça logon no **Adobe Experience Manager** como administrador.
1. Clique no link **Adobe Experience Manager** na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Clique em **Configuração do Editor de XML**.
1. Clique no ícone **Editar** na parte superior.
1. Baixe o arquivo `ui\_config.json`.Remova o seguinte trecho de código do arquivo baixado:

   ```json
   {
       "component":"tab",
       "id":"workflow",
       "title":"Manage",
       "on-click":"APP_MODE_CHANGE",
       "items":
       [
           {
               "component":"label",
               "label":"Manage"
           }
       ]
   },
   ```

1. Faça upload do arquivo ui\_config.json atualizado.

Observe que o filtro **Gerenciar** não está mais disponível.

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor](customize-overview.md)
