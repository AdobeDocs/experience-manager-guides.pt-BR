---
title: Configurar o recurso de tradução no editor da Web
description: Saiba como configurar o recurso de tradução no Editor da Web
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/7-SFQ0FXQ6bGo3pjAOK-18sEsU4-zriruioG2nMx2o0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9baid: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 154
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

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
