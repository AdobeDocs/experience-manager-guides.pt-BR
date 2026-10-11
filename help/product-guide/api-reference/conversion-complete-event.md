---
title: Manipulador de eventos do processo de conversão
description: Saiba mais sobre o manipulador de eventos do processo de conversão
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/VhlUaVSMTZpfyh5MiJI0WHFpc46s41xjLbuLMUnKH58'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: bb416568-e09c-46e3-b3e9-fa7154401215
    internal-label: Conversion process event handler
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 3%
---
# Manipulador de eventos do processo de conversão {#id175UB30E05Z}

O AEM Guides expõe o evento com/adobe/fmdita/conversion/complete usado para executar qualquer operação de pós-processamento após a conclusão de um processo de conversão de documentos. Esse evento é disparado sempre que um documento não DITA é migrado para o formato de arquivo DITA. Por exemplo, se você executar uma conversão do Word para o DITA ou um processo de conversão do InDesign para o DITA, esse evento será chamado após o término do processo de conversão.

É necessário criar um manipulador de eventos do AEM para ler as propriedades disponíveis nesse evento e executar processamento adicional.

Os detalhes do evento são explicados abaixo:

**Nome do evento**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `status` | String | O status de retorno da operação executada. As opções possíveis são: - SUCESSO: o processo de conversão foi concluído com êxito. <br> - CONCLUÍDO COM ERROS: o processo de conversão foi concluído, mas com alguns erros. <br>- FALHA: o processo de conversão falhou devido a algum erro fatal. |
| `filePath` | String | Caminho absoluto do arquivo de origem \(a ser convertido\) no repositório do AEM. |
| `outputPath` | String | Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos. |
| `logPath` | String | Caminho absoluto do nó onde o log de conversão será salvo. |
