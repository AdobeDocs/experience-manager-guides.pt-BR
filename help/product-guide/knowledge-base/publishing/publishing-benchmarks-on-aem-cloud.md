---
title: Guias de publicação de benchmarks no AEMaaCS
description: Entenda os limites do sistema em Publicação na AEM Cloud.
feature: Publishing
role: User, Admin
source-git-commit: 6e2577f04f1092ec9d8445ddbb97aa34be1e53a4
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 20%

---

# Benchmarks de publicação do AEM Guides no AEMaaCS

Este benchmark avalia o desempenho das novas APIs de publicação em diferentes predefinições de saída e no aumento do tamanho dos mapas no AEM Guides as a Cloud Service. O objetivo é entender o comportamento de escalabilidade e identificar gargalos de desempenho.

O serviço de publicação usa uma [arquitetura baseada em microsserviços](https://experienceleague.adobe.com/pt-br/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/publish-microservice-architecture-and-performance) com dimensionamento automático, permitindo a manipulação de cargas de trabalho maiores por meio de pods adicionais.

## Ambiente de execução

- **AEM versão**:2026.4.25322.20260407T085152Z
- **Versão do complemento Guides**: 2026.5.0
- **Contagem de pods inicial**: 2 pods
- **Comportamento de dimensionamento automático**: dimensionado para até 4 pods em 4 nós conforme a carga aumenta
- **vCPUs**: 10
- **RAM por pod**: 8 GB
- **Usuários simultâneos**: 1 usuário

>[!NOTE]
>
> Esse exercício enfocou como a publicação se comporta à medida que o tamanho do mapa aumenta, destacando o impacto de mapas maiores na taxa de transferência, na latência e na conclusão geral da publicação sob carga.


## Números de geração de saída

**Site Nativo do AEM**

| MapSize | Tempo de execução (em segundos) | Microsserviço |
| ------- | ------------------ | ------------ |
| 10 | 62.378 | Sim |
| 100 | 64.27 | Sim |
| 1000 | 93.091 | Sim |
| 5000 | 496.319 | Sim |
| 10000 | 922.602 | Sim |

**PDF nativo**

| MapSize | Tempo de execução (em segundos) | Microsserviço |
| ------- | ------------------ | ------------ |
| 10 | 62.302 | Sim |
| 100 | 62.431 | Sim |
| 1000 | 108.666 | Sim |
| 5000 | 201.379 | Sim |
| 10000 | 1170.689 | Sim |

**PDF**

| MapSize | Tempo de execução (em segundos) | Microsserviço |
| ------- | ------------------ | ------------ |
| 10 | 30.926 | Sim |
| 100 | 30.987 | Sim |
| 1000 | 77.007 | Sim |
| 5000 | 247.505 | Sim |
| 10000 | 686.61 | Sim |

**HTML5**

| MapSize | Tempo de execução (em segundos) | Microsserviço |
| ------- | ------------------ | ------------ |
| 10 | 30.844 | Sim |
| 100 | 30.834 | Sim |
| 1000 | 77.384 | Sim |
| 5000 | 170.237 | Sim |
| 10000 | 419.166 | Sim |


## Observações principais

- O tempo de geração do site do AEM depende do modelo que está sendo usado. O tempo de execução pode aumentar se um template complexo for usado.
- O tempo de execução da publicação personalizada se baseia em um exemplo de saída personalizada. O tempo de publicação personalizado depende exclusivamente da lógica de transformação do próprio cliente.