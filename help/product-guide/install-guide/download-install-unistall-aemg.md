---
title: Desinstalar o AEM Guides
description: Saiba como desinstalar o AEM Guides
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Desinstalar o AEM Guides {#id21BHG0C0SXA}

Você pode desinstalar o AEM Guides usando o Gerenciador de pacotes do CRX. Durante a desinstalação, o conteúdo do repositório é revertido para o instantâneo criado imediatamente antes da instalação do pacote.

Execute as seguintes etapas para desinstalar o AEM Guides:

1. Faça logon na instância do AEM e navegue até o Gerenciador de pacotes da CRX. O URL padrão para acessar o gerenciador de pacotes é:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Procure pelo pacote com.adobe.fmdita.
1. Clique no pacote para expandi-lo.
1. Clique em **Mais** para abrir a lista suspensa.
1. Clique em **Desinstalar** e aguarde a conclusão da desinstalação.
1. Se você não precisar mais deste pacote, clique em **Excluir** após desinstalar o pacote.

## Após a desinstalação

Para limpar os arquivos residuais após a desinstalação, execute as seguintes etapas:

1. Limpar o cache de scripts usando:

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. Você pode invalidar o cache usando:

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. Clique em **Invalidar cache**.
1. Limpe o cache do navegador.

**Tópico pai:**[ Baixar e instalar](download-install.md)
