---
title: Notas de versão | Notas de versão do Service Pack 1 2026.11.0 | AEM GUIDES
description: Saiba mais sobre as correções de erros, problemas conhecidos e compatibilidade do Java SDK para a versão 2026.11.0 Service Pack 1 do Adobe Experience Manager Guides as a Cloud Service.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e21e39b2acf48c4115101ab806e97b45844fa191
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%
---
# Notas de versão do Service Pack 1 2026.11.0 (novembro de 2026)

Este artigo fornece informações sobre os problemas corrigidos, a compatibilidade com o Java SDK e os problemas conhecidos na versão 2026.11.0 do Service Pack 1 do Adobe Experience Manager Guides as a Cloud Service.

## Compatibilidade com Java SDK

Use os recursos a seguir ao desenvolver plug-ins Java personalizados ou integrações com o Experience Manager Guides. Verifique se a versão do SDK corresponde à versão instalada do Experience Manager Guides.

| Versão | Versão do Java SDK | Maven Central | Referência da API Java |
|---|---|---|----|
| Service Pack 1 2026.11.0 | 2026.11.0 | [API do AEM Guides SDK 2026.11.0](https://central.sonatype.com/artifact/com.adobe.aem/aem-dox-sdk-api/2026.11.0) | [Javadoc 2026.11.0](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) |

Para obter mais detalhes, consulte [Configurar e usar o JAR da API do repositório central Maven](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).


## Problemas corrigidos

Os seguintes problemas ocorrem ao publicar no AEM Sites (com mapeamento de componente composto):

- Gerar novamente os tópicos selecionados ou um submapa com a publicação `microservice-based` leva tempo, contanto que o mapa completo seja gerado. (GUIDES-59322)
- Gerar novamente um submapa que contém tópicos fragmentados faz com que o índice exiba títulos e links incorretos. Cada entrada de tópico fragmentado mostra o título do último tópico fragmentado. (GUIDES-58650)

Os seguintes problemas ocorrem ao publicar no AEM Sites usando uma linha de base dinâmica, seja Linha de base (herdada) ou Nova linha de base:

- A linha de base é recriada mais de uma vez durante a mesma operação de publicação, o que aumenta o tempo de publicação e, em alguns casos, causa a interrupção da recriação. Com a Nova linha de base, a publicação incremental também usa uma linha de base obsoleta em vez da atual, de modo que a saída pode não refletir o conteúdo mais recente. (GUIDES-60189)
- Alguns problemas de desempenho são observados ao usar o painel de Mapa. (GUIDES-60189, GUIDES-55646)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para o Service Pack 1 2026.11.0:

- Ao usar o Experience Manager Guides as a Cloud Service 2026.11.0 ou posterior, a publicação falha com um erro de aplicativo se o AEM reiniciar determinados serviços internos durante o processo de publicação, como quando uma instância de servidor é iniciada. (GUIDES-60804)<br>**Solução alternativa:** Para resolver o problema, tente publicar novamente.
- Ao gerar saída para várias predefinições AEM Sites (usando mapeamento de componente composto) ou predefinições PDF nativas usando a mesma linha de base por meio da **Coleção de mapas** ou API, a geração de saída falha com uma exceção `Rebuild the Baseline`. (GUIDES-60877) <br>**Solução alternativa:** publique as predefinições sequencialmente em vez de simultaneamente para evitar o problema.

