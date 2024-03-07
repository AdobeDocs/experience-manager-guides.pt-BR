---
title: Notas de versão | Correção de problemas na versão 4.3.1.5 dos Guias do Adobe Experience Manager
description: Saiba mais sobre as correções de erros na versão 4.3.1.5 dos Guias do Adobe Experience Manager
role: Leader
source-git-commit: 485f88e2e8724d1dc28deac13d677734fcc15c25
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---


# Correção de problemas na versão 4.3.1.5


Este artigo aborda os bugs corrigidos em várias áreas da versão 4.3.1.5 dos Guias do Adobe Experience Manager.



Saiba mais sobre [instruções de atualização da versão 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Criação  

- Adição de espaços entre elementos em linha no `<codeblock>` causa uma quebra de linha na saída gerada. (15247)
- Problemas de experiência ocorrem ao adicionar elementos da caixa de diálogo &quot;Inserir elemento&quot;. (15108)

## Publicação

- Os logs de erro exibem informações incorretas sobre a publicação de conteúdo com escopos externos. (15242)
- Links internos para arquivos DITA que começam com `HTTP` são tratados como links externos e causam erros de escopo. (15155)
- A regeneração do site AEM falha para mapas DITA. (14369)

## Gerenciamento

- **fmditaTopicrefs** A propriedade mostra caminhos relativos em vez de caminhos absolutos. (15341)

