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

Você pode usar o **Gerenciar** no Editor da Web para traduzir o conteúdo. Essa guia está disponível por padrão.

Para ocultar a variável **Gerenciar** no Editor da Web, execute as seguintes etapas:

1. Efetue logon no **Adobe Experience Manager** como administrador.
1. Clique no link **Adobe Experience Manager** vincule na parte superior e escolha **Ferramentas**.
1. Selecionar **Guias** na lista de ferramentas e clique no botão **Perfis de pasta**.
1. Clique no link **Perfil global** bloco.
1. Clique em **Configuração do editor XML**.
1. Clique em **Editar** ícone na parte superior.
1. Baixe o `ui\_config.json` arquivo.Remova o seguinte trecho de código do arquivo baixado:

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

Observe que **Gerenciar** O filtro não está mais disponível.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
