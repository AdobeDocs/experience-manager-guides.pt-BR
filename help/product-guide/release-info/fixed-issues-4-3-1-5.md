---
title: Notas de versão | Correção de problemas na versão 4.3.1.5 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 4.3.1.5 do Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---

# Correção de problemas na versão 4.3.1.5


Este artigo aborda os bugs corrigidos em várias áreas da versão 4.3.1.5 do Adobe Experience Manager Guides.



Saiba mais sobre as [instruções de atualização para a versão 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Criação  

- Adicionar espaços entre elementos embutidos dentro de `<codeblock>` causa uma quebra de linha na saída gerada. (15247)
- Problemas de experiência ocorrem ao adicionar elementos da caixa de diálogo &quot;Inserir elemento&quot;. (15108)

## Publicação

- Os logs de erro exibem informações incorretas sobre a publicação de conteúdo com escopos externos. (15242)
- Links internos para arquivos DITA que começam com `HTTP` são tratados como links externos e causam erros de escopo. (15155)
- A regeneração do site AEM falha para mapas DITA. (14369)

## Gerenciamento

- A propriedade **fmditaTopicrefs** mostra caminhos relativos em vez de caminhos absolutos. (15341)
