---
title: Configurar o recurso de tradução no editor da Web
description: Saiba como configurar o recurso de tradução no Editor da Web
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# Configurar o recurso de tradução no Editor da Web do Cloud Service

O editor da Web fornece um recurso avançado de tradução para traduzir o conteúdo em vários idiomas.

Você pode usar a guia **Gerenciar** no Editor da Web para traduzir o conteúdo. Essa guia está disponível por padrão.

Para ocultar a guia **Gerenciar** no Editor da Web, execute as seguintes etapas:

1. Faça logon no **Adobe Experience Manager** como administrador.
1. Clique no link **Adobe Experience Manager** na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Clique em **Configuração do Editor de XML**.
1. Clique no ícone **Editar** na parte superior.
1. Baixar o arquivo `ui\_config.json`.Remova o seguinte trecho de código do arquivo baixado:

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

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](customize-overview.md)
