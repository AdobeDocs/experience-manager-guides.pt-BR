---
title: Configurar prompt para fazer check-in de um arquivo ao fechar
description: Saiba como configurar o prompt para fazer check-in de um arquivo ao fechar
exl-id: d184c97f-8405-4bcd-963d-635f17584897
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---

# Configurar prompt para fazer check-in de um arquivo ao fechar {#id222HC040PE8}

Quando o usuário tenta fechar um arquivo aberto no Editor da Web usando o **Fechar** na guia do arquivo ou na guia **Fechar** no menu Opções, uma caixa de diálogo será exibida se o arquivo tiver dados não salvos ou uma versão não salva. O usuário será solicitado a desbloquear o arquivo se ele estiver bloqueado.

A variável **Desbloquear o arquivo** a caixa de seleção não está ativada por padrão e você precisa ativá-la no configMgr. Execute as seguintes etapas para habilitar a opção por padrão no Editor da Web:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacote.

1. Selecione o **Solicitar check-in ao fechar** opção.

1. Clique em **Salvar**.


Quando essa configuração estiver ativada, a variável **Desbloquear o arquivo** é marcada por padrão na caixa de diálogo.

Para obter mais detalhes, consulte *Cenários de fechamento e salvamento de arquivos* no guia as a Cloud Service Usar guias do Adobe Experience Manager.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
