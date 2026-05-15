---
title: Notas de versão | Correção de problemas na versão 4.3.1.5 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 4.3.1.5 do Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
TQID: https://experienceleague.adobe.com/ujQFyhAp5bIB1OJnmqvbHCaiDip7T2qsjlVAWevykK8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 6%

---

# Correção de problemas na versão 4.3.1.5


Este artigo aborda os bugs corrigidos em várias áreas da versão 4.3.1.5 do Adobe Experience Manager Guides.



Saiba mais sobre as [instruções de atualização para a 4.3.1.5 versão](../release-info/upgrade-instructions-4-3-1-5.md).


## Criação

- Adicionar espaços entre elementos embutidos dentro de `<codeblock>` causa uma quebra de linha na saída gerada. (15247)
- Problemas de experiência ocorrem ao adicionar elementos da caixa de diálogo &quot;Inserir elemento&quot;. (15108)

## Publicação

- Os logs de erro exibem informações incorretas sobre a publicação de conteúdo com escopos externos. (15242)
- Links internos para arquivos DITA que começam com `HTTP` são tratados como links externos e causam erros de escopo. (15155)
- A regeneração do site do AEM falha para mapas DITA. (14369)

## Gerenciamento

- A propriedade **fmditaTopicrefs** mostra caminhos relativos em vez de caminhos absolutos. (15341)
