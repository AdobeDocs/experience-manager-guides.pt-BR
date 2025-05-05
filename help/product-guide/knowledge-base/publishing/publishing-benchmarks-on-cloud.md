---
title: Guias de publicação de benchmarks no AEMaaCS
description: Entenda os limites do sistema em Publicação na Nuvem AEM.
exl-id: 2cb4dfa4-dafc-409a-8d29-dbb00fabeae5
feature: Publishing
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 8%

---

# Benchmarks de publicação do AEM Guides no AEMaaCS

Atualmente, o AEM Guides Cloud Service tem alguns limites de tamanhos de mapa de publicação para os quais a equipe do Guides está trabalhando ativamente.

A equipe do Guides apresentou um microsserviço de publicação escalável para oferecer suporte a mapas grandes e várias publicações simultâneas. Para saber mais sobre o novo microsserviço de publicação, consulte [arquitetura do microsserviço de publicação](publish-microservice-architecture-and-performance.md)

Para configurar o novo serviço de publicação para qualquer ambiente de nuvem AEM, consulte [configurar nova publicação baseada em microsserviço](configure-microservices.md)


## Ambiente de execução

    Versão do AEM: 2023.5.11983.20230511T173830Z
    Versão do Guia Complementar: 2023.6.0
    Modelo de Site do AEM: Modelo de OOTB do AEM Guides
    Versão do DITA-OT: 3.5.4
    Tipo de Fluxo de Trabalho do Publish: Fluxo de Trabalho do Publish Dividido
    Saída suportada pelo microsserviço: PDF nativo, PDF (Dita-OT)&lbrace;6

## Números de Geração de Saída

| Tipo de saída | Tamanho do Mapa (Referências de Tópico) | Tempo de execução (em segundos) | Microsserviço de publicação |
|---------------|------------------------------|----------------------------|-----------------------|
| Site AEM | 3500 | 5220 | Não |
| PDF nativo | 3500 | 780 | Sim |
| PDF (DITA-OT) | 11000 | 960 | Sim |
| HTML 5 | 3500 | 240 | Não |
| Personalizado | 300 | 300 | Não |

## Pontos principais a serem lembrados

- O site AEM cria muitos nós cq:Page e nivela ao renderizá-los individualmente durante o tempo de geração. Por isso, é aconselhável evitar a execução de várias publicações simultâneas no site AEM, pois isso pode sobrecarregar o sistema.
- O tempo de geração do site de AEM depende do modelo usado. O tempo de execução pode aumentar se um template complexo for usado.
- O tempo de execução de publicação personalizado serve para obter um exemplo de saída personalizada. O tempo de publicação personalizado depende exclusivamente da lógica de transformação do próprio cliente.
