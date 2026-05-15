---
title: Fluxo de trabalho de pós-geração
description: Uma visão geral do fluxo de trabalho de pós-geração com um exemplo
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
feature: Workflow Configuration
role: User, Admin
TQID: https://experienceleague.adobe.com/GmpUvIwR5aDOIQ4RNUXoeOeQB3MrueRuxpvYBwYev4I
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b455a250-64c4-4598-b015-7b6b6dc528b1id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 0%

---

# Publicação no AEM Guides - Fluxo de trabalho de pós-geração

O AEM Guides oferece a flexibilidade de especificar um fluxo de trabalho de geração de pós-saída. Você pode executar algumas tarefas de pós-processamento na saída gerada usando o AEM Guides.
Por exemplo, você pode querer definir determinadas propriedades na saída do PDF ou enviar um email para um conjunto de usuários depois que a saída for gerada.


## Quais são as etapas envolvidas para utilizar workflows de pós-geração

### Criar um processo de fluxo de trabalho

Crie um processo de workflow baseado em Java ou ECMA que execute a operação na saída gerada. Por exemplo, copiar alguns metadados da origem para o conteúdo gerado ou manipular os metadados da saída gerada.
- Pegaremos um exemplo de criação desse processo usando o script ECMA (você pode consultar o pacote anexado)
- Para o processo de fluxo de trabalho baseado em Java, consulte a seção &quot;*Personalizar fluxo de trabalho de geração pós-saída*&quot; do [Guia de instalação e configuração](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### Criar um modelo de fluxo de trabalho

Com o processo de fluxo de trabalho personalizado criado na etapa anterior, crie um modelo de fluxo de trabalho e adicione essa etapa do processo a ele.
- Você também precisa adicionar uma etapa de processo obrigatória &quot;*Finalizar pós-geração*&quot; como a última etapa do fluxo de trabalho.

Consulte o modelo de fluxo de trabalho de amostra mostrado abaixo:

![Modelo de fluxo de trabalho de pós-geração](../assets/workflows/pgwf-workflow-model.png)


### Usar este fluxo de trabalho de pós-geração em um mapa

O fluxo de trabalho de pós geração é uma propriedade que pode ser configurada em qualquer predefinição de saída no mecanismo de publicação do AEM Guides. Exemplo:

![Fluxo de trabalho de pós-geração na Predefinição de saída](../assets/workflows/pgwf-preset-settings.png)


Presumindo que o modelo selecionado já foi criado.


### Testes

Agora é possível executar a publicação usando essa predefinição e validar a saída da etapa do processo


## Amostra

Para sua referência, você pode usar o pacote abaixo e instalá-lo por meio do gerenciador de pacotes para testar o fluxo de trabalho de pós-geração de amostra (*conforme referido nas capturas de tela acima*)

[Um exemplo de modelo de fluxo de trabalho de pós-geração baseado em ECMA](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
