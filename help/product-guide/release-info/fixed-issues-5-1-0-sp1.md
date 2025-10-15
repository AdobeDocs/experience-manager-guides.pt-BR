---
title: Notas de versão | Correção de problemas na versão Adobe Experience Manager Guides 5.1.0 Service Pack 1
description: Saiba mais sobre as correções de erros na versão 5.1.0 Service Pack 1 do Adobe Experience Manager Guides
role: Leader
source-git-commit: 575488e1b378c17419add75876a8e7f7423d5116
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 1%

---

# Correção de problemas na versão 5.1.0 do Service Pack 1 (outubro de 2025)


Este artigo aborda os bugs corrigidos em várias áreas da versão 5.1.0 Service Pack 1 do Adobe Experience Manager Guides.

Saiba mais sobre as [instruções de atualização para o 5.1.0 Service Pack 1 versão](upgrade-instructions-5-1-0-sp1.md).


## Platform

- Ao migrar de não UUID para UUID e atualizar para a versão mais recente (5.0+), se você mover imagens referenciadas entre pastas e reverter os arquivos DITA (onde essas imagens foram referenciadas) para versões anteriores, isso resultará em referências de imagem corrompidas. (GUIDES-34315)

## Publicação

- Ao publicar um mapa DITA usando linha de base no AEM Sites (com mapeamento de componente herdado), os elementos do mapa com o atributo `processing-role = resource-only` também são publicados. (GUIDES-34298)
