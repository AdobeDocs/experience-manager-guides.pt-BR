---
title: Transmita os metadados para a saída usando DITA-OT
description: Saiba como transmitir os metadados para a saída usando a publicação DITA-OT nos Guias do AEM.
exl-id: 70ca32dc-56c3-45ee-b6b9-0efb8cc79ea1
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Transmita os metadados para a saída usando DITA-OT {#id21BJ00QD0XA}

Os metadados são informações adicionais sobre a saída. Nos Guias do AEM você pode transmitir os metadados existentes ou criar tags de metadados personalizadas. Você pode transmitir metadados para saídas de AEM, PDF, HTML5, EPUB e Formato personalizado usando a publicação DITA-OT.

Execute as seguintes etapas para transmitir os metadados para a saída usando a publicação DITA-OT:

1. No **Interface do usuário do Assets**, navegue até o arquivo de mapa DITA e clique nele para o qual deseja passar os metadados para o DITA-OT.
1. Selecione e edite uma predefinição de saída para a qual deseja passar os campos de metadados. Por exemplo, selecione predefinição de saída de PDF.
1. Selecionar **DITA-OT** em Gerar &lt;output> Usando a opção na predefinição de saída selecionada.

   ![](images/custom-meta-data-output-preset.png){width="800" align="left"}

1. Na lista suspensa Propriedades, selecione os metadados que deseja transmitir para a publicação DITA-OT.

   A lista suspensa Propriedades lista as propriedades personalizadas e padrão. Por exemplo, na captura de tela acima, o autor é a propriedade personalizada enquanto `dc:description`, `dc:language`, `dc:title`, e `docstate` são as propriedades padrão.

   >[!NOTE]
   >
   > Essas propriedades são selecionadas do arquivo metadataList, disponível no seguinte local:`/libs/fmdita/config/metadataList`. Por padrão, há quatro propriedades listadas neste arquivo- `dc:description`, `dc:language`, `dc:title`, e `docstate`.

   Esse arquivo pode ser sobreposto em: `/apps/fmdita/config/metadataList`.

   Para transmitir uma propriedade personalizada para a qual você já definiu os valores, consulte [Usar metadados de AEM na saída de PDF DITA-OT](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. No **Propriedades** selecione as propriedades personalizadas e padrão necessárias. Por exemplo, selecione `author`, `dc:title`, e `dc:description`. Estes são os padrões `metadata/properties` que é criado após a criação de um arquivo. As propriedades selecionadas são listadas abaixo da dropbox.

   ![](images/selected-metadata-properties.png){width="300" align="left"}

1. Clique em **Concluído** na parte superior esquerda para salvar as alterações.
1. Gere a saída.

As propriedades de metadados selecionadas serão passadas para a saída gerada usando o DITA-OT.

**Tópico pai:**[ Geração de saída](generate-output.md)