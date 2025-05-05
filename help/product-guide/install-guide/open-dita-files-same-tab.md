---
title: Abrir tópico DITA ou mapear arquivos na mesma guia
description: Saiba como Abrir um tópico DITA ou mapear arquivos na mesma guia
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Abrir tópico DITA ou mapear arquivos na mesma guia {#id223HI0P202H}

Em alguns workflows, ao clicar em um link de um tópico ou arquivo de mapa, ele é aberto em uma nova guia. Isso pode levar a muitas guias abertas no navegador, o que pode afetar sua produtividade. Você pode alterar esse comportamento de abrir um tópico ou arquivo de mapa em uma nova guia e forçá-lo a abrir na própria guia atual. Para fazer isso, execute as seguintes alterações de configuração:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Selecione a opção **Abrir tópico/mapa DITA na mesma guia**.

1. Clique em **Salvar**.


Essa configuração afeta os seguintes locais de onde você pode acessar o tópico ou mapear arquivos:

- Criar tópico DITA \(no final do fluxo de trabalho, ao clicar no botão **Abrir tópico**\)

- Criar Mapa DITA \(no final do fluxo de trabalho, ao clicar no botão **Abrir Mapa**\)

- Guia Tópicos no console do mapa DITA

- Guia Linhas de Base no console de mapa DITA

- Guia Relatórios no console de mapa DITA


**Tópico pai:**&#x200B;[ Personalizar editor da Web](conf-web-editor.md)
