---
title: Configurar nomes de arquivo automáticos com base no UUID
description: Saiba como Configurar nomes de arquivo automáticos com base na UUID
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/2oXpOlXt4gZ3GELX7SmwPJoWJYM71f0cZFy2--M6AYM
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 0%

---

# Configurar nomes de arquivo automáticos com base no UUID {#id205QG070D5Z}

Por padrão, quando um tópico ou arquivo de mapa é criado, os autores têm a opção de especificar também o nome do arquivo. Os autores podem atribuir os nomes de arquivo de acordo com seus requisitos. No entanto, isso pode gerar inconsistência e uma grande variedade de nomes de arquivos pode ser vista em um grande sistema de documentação. Como administrador, você pode impedir que seus autores atribuam nomes de arquivos aos arquivos que eles criam em seu sistema. Para cada novo tópico ou arquivo de mapa, você pode optar por atribuir nomes de arquivo baseados em UUID automaticamente.

Execute as seguintes etapas para atribuir automaticamente o nome de arquivo baseado em UUID para todos os novos arquivos criados no sistema:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote *com.adobe.fmdita.xmleditor.config.XmlEditorConfig*.

1. Selecione a opção **Usar nomes de arquivo do sistema baseados em UUID**.

1. Clique em **Salvar**.


>[!NOTE]
>
> Por padrão, essa opção está desativada. Quando essa opção estiver ativada, os autores não verão a opção para especificar o nome do arquivo ao criar um novo tópico ou arquivo de mapa. Um novo tópico ou arquivo de mapa pode ser criado na interface do usuário do Assets e no Editor da Web.

**Tópico pai:**[ Configurar nomes de arquivo](conf-file-names.md)
