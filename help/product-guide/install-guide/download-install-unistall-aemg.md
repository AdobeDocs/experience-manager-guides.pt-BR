---
title: Desinstalar guias do AEM
description: Saiba como desinstalar guias do AEM
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Desinstalar guias do AEM {#id21BHG0C0SXA}

Você pode desinstalar guias AEM usando o Gerenciador de pacotes CRX. Durante a desinstalação, o conteúdo do repositório é revertido para o instantâneo criado imediatamente antes da instalação do pacote.

Execute as seguintes etapas para desinstalar guias AEM:

1. Faça logon na instância do AEM e navegue até o Gerenciador de pacotes do CRX. O URL padrão para acessar o gerenciador de pacotes é:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Procure pelo pacote com.adobe.fmdita.
1. Clique no pacote para expandi-lo.
1. Clique em **Mais** para abrir a lista suspensa.
1. Clique em **Desinstalar** e aguarde a conclusão da desinstalação.
1. Se não precisar mais desse pacote, clique em **Excluir** após desinstalar o pacote.

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
