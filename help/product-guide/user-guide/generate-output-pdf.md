---
title: Tipos de predefinição do PDF
description: Saiba mais sobre os tipos de predefinição do PDF que você pode criar usando o Adobe Experience Manager Guides.
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
source-git-commit: 558cc1a724a483353eb5d912354e1ab37dab348a
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---

# Visão geral da predefinição de saída do PDF {#id205BE600HAH}

Com o Experience Manager Guides, é possível criar predefinições do PDF para gerar PDFs de tópicos individuais ou um arquivo de mapa inteiro. Você pode publicar seu conteúdo em um formato PDF usando um dos três métodos abaixo:

**DITA-OT**

Use esse método para gerar uma saída PDF para um mapa no console Mapa ou no painel Mapa. É possível definir as propriedades de publicação antes de gerar o PDF, criando uma predefinição de saída para o mapa que está aberto no console do Mapa ou no painel do Mapa.

Para obter mais informações sobre como criar uma predefinição de saída do PDF usando o método DITA-OT, exiba [Criar predefinição de saída do DITA-OT PDF](./generate-output-pdf-dita-ot.md)

**FrameMaker Publishing Server (FMPS)**

>[!NOTE]
>
> A opção de publicação FMPS só está disponível no painel Mapa.

Use esse método para gerar uma saída do PDF não apenas a partir do conteúdo DITA, mas também de documentos do FrameMaker (.book e .fm) disponíveis no repositório do AEM. O PDF pode ser criado configurando uma predefinição de saída e publicado usando o FrameMaker Publishing Server (FMPS). Você pode projetar e configurar a aparência da saída para o PDF e outros formatos e armazenar a mesma em um arquivo de configuração (.sts). Esse arquivo de configuração é então usado pelo FMPS para gerar saída para um mapa DITA ou arquivo .book. Para criar ou editar uma predefinição de saída, exiba [Noções básicas sobre as predefinições de saída](../user-guide/generate-output-understand-presets.md).

Para obter mais informações sobre como configurar o FMPS, exiba [Gerar saída de documentos do FrameMaker](../user-guide/fm-output-generatation.md).

**PDF nativo**

Use este método para gerar uma saída de PDF repleta de recursos com base nos padrões W3C CSS3 e CSS de mídia paginada. Com a publicação no PDF nativo, você pode usar modelos para definir o layout e o estilo do conteúdo e aplicar várias configurações para ajustar o PDF. Além disso, você pode modificar e criar seus próprios modelos com o editor de modelos.

Para obter mais informações sobre a criação da predefinição nativa do PDF, exiba [Criar predefinição de saída nativa do PDF](../web-editor/native-pdf-web-editor.md).





**Tópico pai:**&#x200B;[&#x200B; Noções básicas sobre as predefinições de saída](generate-output-understand-presets.md)
