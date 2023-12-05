---
title: Fluxo de trabalho de pós-geração
description: Uma visão geral do fluxo de trabalho de pós-geração com um exemplo
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Publicação de guias do AEM - Fluxo de trabalho de pós-geração

O Guias do AEM oferece a flexibilidade de especificar um fluxo de trabalho de geração de pós-saída. Você pode executar algumas tarefas de pós-processamento na saída que é gerada usando Guias AEM.
Por exemplo, você pode querer definir determinadas propriedades na saída do PDF ou enviar um email para um conjunto de usuários depois que a saída for gerada.


## Quais são as etapas envolvidas para utilizar workflows de pós-geração

### Criar um processo de fluxo de trabalho

Crie um processo de workflow baseado em Java ou ECMA que execute a operação na saída gerada. Por exemplo, copiar alguns metadados da origem para o conteúdo gerado ou manipular os metadados da saída gerada.

- Pegaremos um exemplo de criação desse processo usando o script ECMA (você pode consultar o pacote anexado)
- Para o processo de workflow baseado em Java, consulte a seção &quot;*Personalizar fluxo de trabalho de geração de pós-saída*&quot; de [Guia de instalação e configuração](/help/product-guide/install-guide/customize-workflows.md#id17A6GI004Y4)


### Criar um modelo de fluxo de trabalho

Com o processo de fluxo de trabalho personalizado criado na etapa anterior, crie um modelo de fluxo de trabalho e adicione essa etapa do processo a ele.

- Você também precisa adicionar uma etapa de processo obrigatória&quot;*Finalizar pós-geração*&quot; como a última etapa do fluxo de trabalho.

Consulte o modelo de fluxo de trabalho de amostra mostrado abaixo:

![Modelo de fluxo de trabalho de pós-geração](../assets/workflows/pgwf-workflow-model.png)


### Usar este fluxo de trabalho de pós-geração em um mapa

O fluxo de trabalho de pós geração é uma propriedade que pode ser configurada em qualquer predefinição de saída no mecanismo de publicação dos Guias AEM. Exemplo:

![Fluxo de trabalho de pós geração na predefinição de saída](../assets/workflows/pgwf-preset-settings.png)


Presumindo que o modelo selecionado já foi criado.


### Testes

Agora é possível executar a publicação usando essa predefinição e validar a saída da etapa do processo


## Amostra

Para sua referência, você pode usar o pacote abaixo e instalá-lo por meio do gerenciador de pacotes para testar o fluxo de trabalho de pós-geração de amostra (*conforme referido nas capturas de tela acima*)

[Um exemplo de modelo de fluxo de trabalho de pós-geração baseado em ECMA](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
