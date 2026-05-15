---
title: Notas de versão | Correção de problemas na versão Adobe Experience Manager Guides 5.1.0 Service Pack 1
description: Saiba mais sobre as correções de erros na versão 5.1.0 Service Pack 1 do Adobe Experience Manager Guides
role: Leader
exl-id: 4b51085b-1f71-41e2-b0a9-88a12990fc97
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 144
ht-degree: 1%

---

# Correção de problemas na versão 5.1.0 do Service Pack 1 (outubro de 2025)


Este artigo aborda os bugs corrigidos em várias áreas da versão 5.1.0 Service Pack 1 do Adobe Experience Manager Guides.

Saiba mais sobre as [instruções de atualização para o 5.1.0 Service Pack 1 versão](upgrade-instructions-5-1-0-sp1.md).


## Platform

- Ao migrar de não UUID para UUID e atualizar para a versão mais recente (5.0+), se você mover imagens referenciadas entre pastas e reverter os arquivos DITA (onde essas imagens foram referenciadas) para versões anteriores, isso resultará em referências de imagem corrompidas. (GUIDES-34315)

## Publicação

- Ao publicar um mapa DITA usando linha de base no AEM Sites (com mapeamento de componente herdado), os elementos do mapa com o atributo `processing-role = resource-only` também são publicados. (GUIDES-34298)
