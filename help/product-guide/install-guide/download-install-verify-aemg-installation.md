---
title: Verificar a instalação do AEM Guides
description: Saiba como verificar a instalação do AEM Guides
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Verificar a instalação do AEM Guides {#id213BD030FBE}

Depois de instalar o AEM Guides, você precisa verificar se a instalação foi bem-sucedida ou não. Execute as seguintes etapas para verificar o processo de instalação:

1. Faça logon na instância do AEM e navegue até a página AEM Web Console Bundles. O URL padrão para acessar a página de pacotes é:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   Uma lista de pacotes é exibida.

1. Filtre a lista de pacotes inserindo fmdita na caixa de texto de filtragem e pressione **Enter**.

   A lista de pacotes é filtrada para mostrar os pacotes instalados pelo AEM Guides. Se a instalação for bem-sucedida, todos os conjuntos instalados terão um **Status** de **Ativo**.

   Se algum dos pacotes não tiver o status **Ativo**, verifique os logs de AEM para solucionar o problema de instalação.


>[!IMPORTANT]
>
> Há várias recomendações de otimização de desempenho que você pode considerar para melhorar o desempenho do seu sistema. Consulte [Recommendations para otimização de desempenho](download-install-recommend-perf-optimiz.md#) para obter detalhes.

**Tópico pai:**&#x200B;[ Baixar e instalar](download-install.md)
