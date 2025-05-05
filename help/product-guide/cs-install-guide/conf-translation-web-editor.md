---
title: Configurar o recurso de tradução no editor da Web
description: Saiba como configurar o recurso de tradução no Editor da Web
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Configurar o recurso de tradução no editor da Web {#id21BONI0J0YR}

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

**Tópico pai:**&#x200B;[ Personalizar editor da Web](conf-web-editor.md)
