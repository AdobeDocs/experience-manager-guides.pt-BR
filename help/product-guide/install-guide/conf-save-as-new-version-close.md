---
title: Configurar o prompt para salvar como uma nova versão ao fechar
description: Saiba como Configurar o prompt para salvar como uma nova versão ao fechar
exl-id: 1b8c3eaa-a654-4563-9541-18a59b7d306c
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configurar o prompt para salvar como uma nova versão ao fechar {#id222HBI00XXA}

Quando o usuário tenta fechar um arquivo aberto no Editor da Web usando o **Fechar** na guia do arquivo ou na guia **Fechar** no menu Opções, uma caixa de diálogo será exibida se o arquivo tiver dados não salvos ou uma versão não salva. O usuário será solicitado a salvar o arquivo como uma nova versão se a versão não for salva.

A variável **Salvar como uma nova versão** a caixa de seleção não está ativada por padrão e você precisa ativá-la no configMgr. Execute as seguintes etapas para habilitar a opção por padrão no Editor da Web:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacote.

1. Selecione o **Solicitar nova versão ao fechar** opção.

1. Clique em **Salvar**.


Quando essa opção é selecionada, a variável **Salvar como uma nova versão** é marcada por padrão na caixa de diálogo.

Para obter mais detalhes, consulte *Cenários de fechamento e salvamento de arquivos* no guia as a Cloud Service Usar guias do Adobe Experience Manager.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
