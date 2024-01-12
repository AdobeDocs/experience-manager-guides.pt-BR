---
title: Definir o Editor de mapa avançado como padrão
description: Saiba como definir o Editor de mapa avançado como padrão
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Definir o Editor de mapa avançado como padrão {#id181AI0003PN}

O AEM Guides vem com um Editor de Mapas Básico e um Editor de Mapas Avançado. O Editor de mapa básico fornece todos os recursos necessários para criar seu arquivo de mapa. O Editor de mapa avançado possui muito mais recursos e está integrado ao Editor da Web. O Editor de mapa avançado permite que os autores criem e editem arquivos de mapa DITA com uma interface fácil de usar.

Por padrão, sempre que um novo arquivo de mapa é criado, ele é aberto no Editor de mapa básico. Você pode alterar esse comportamento ativando a configuração para abrir o Editor de mapa avançado por padrão.

Execute as seguintes etapas para tornar o Editor de mapa avançado como o editor padrão para os arquivos de mapa:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacote.

1. Selecione o **Ocultar Editor de mapa básico** opção.

   Com essa opção selecionada, os usuários não verão o link Editor de mapa básico em nenhum lugar na interface do usuário. Por padrão, os arquivos de mapa serão abertos no Editor de mapa avançado.
