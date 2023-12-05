---
title: Personalizar dicionário padrão do AEM
description: Saiba como personalizar o dicionário padrão do AEM
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# Personalizar dicionário padrão do AEM {#id209SD8000WU}

O Editor da Web pode ser configurado para usar o verificador ortográfico AEM ou o verificador ortográfico do navegador. Se optar por trabalhar com o verificador ortográfico AEM, você terá a flexibilidade de definir sua lista de palavras personalizadas. Essas palavras personalizadas são então adicionadas ao dicionário AEM e essas palavras não são sinalizadas \(como incorreto\) no Editor da Web.

Execute as seguintes etapas para criar sua lista de palavras personalizadas, que são adicionadas ao dicionário AEM:

1. Crie o arquivo user\_dictionary.txt com uma lista de palavras que você deseja definir no dicionário personalizado.

   >[!NOTE]
   >
   > Cada palavra personalizada deve ser definida em uma nova linha.

1. Salve o arquivo no seguinte local no repositório Git do Cloud Manager:

   /apps/fmdita/config

1. Salve o arquivo.

   Confirme as alterações e execute o pipeline \(CI/CD\) do Cloud Manager para implantar alterações de configuração.


Os autores precisariam reiniciar a sessão do Editor da Web para atualizar a lista de palavras personalizadas no dicionário AEM.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
