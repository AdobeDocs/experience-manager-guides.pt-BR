---
title: Notas de versão | Correção de problemas no Adobe Experience Manager Guides, versão 2026.11.0 Service Pack 1
description: Saiba mais sobre as correções de erros na versão 2026.11.0 do Service Pack 1 do Adobe Experience Manager Guides as a Cloud Service.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 8821e671951d83439688aa33f88ac1f91f0919eb
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%
---
# Correção de problemas na versão 2026.11.0 do Service Pack 1

Este artigo aborda os bugs corrigidos na versão 2026.11.0 do Service Pack 1 do Adobe Experience Manager Guides as a Cloud Service.

## Publicação

Os seguintes problemas ocorrem ao publicar no AEM Sites (com mapeamento de componente composto):

- Gerar novamente os tópicos selecionados ou um submapa com a publicação `microservice-based` leva tempo, contanto que o mapa completo seja gerado. (GUIDES-59322)
- Gerar novamente um submapa que contém tópicos fragmentados faz com que o índice exiba títulos e links incorretos. Cada entrada de tópico fragmentado mostra o título do último tópico fragmentado. (GUIDES-58650)

Os seguintes problemas ocorrem ao publicar no AEM Sites usando uma linha de base dinâmica, seja Linha de base (herdada) ou Nova linha de base:

- A linha de base é recriada mais de uma vez durante a mesma operação de publicação, o que aumenta o tempo de publicação e, em alguns casos, causa a interrupção da recriação. Com a Nova linha de base, a publicação incremental também usa uma linha de base obsoleta em vez da atual, de modo que a saída pode não refletir o conteúdo mais recente. (GUIDES-60189)
- Alguns problemas de desempenho são observados ao usar o painel de Mapa. (GUIDES-60189, GUIDES-55646)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para o Service Pack 1 2026.11.0:

- Ao usar o Experience Manager Guides as a Cloud Service 2026.11.0 ou posterior, a publicação falha com um erro de aplicativo se o AEM reiniciar determinados serviços internos durante o processo de publicação, como quando uma instância de servidor é iniciada. (GUIDES-60804)<br>**Solução alternativa:** Para resolver o problema, tente publicar novamente.
- Ao gerar saída para várias predefinições do AEM Sites (usando mapeamento de componente composto) ou predefinições do PDF Nativo por meio de **Coleção de mapas** ou API, a geração de saída falha com uma exceção `Rebuild the Baseline`. <br>**Solução alternativa:** publique as predefinições sequencialmente em vez de simultaneamente para evitar o problema.