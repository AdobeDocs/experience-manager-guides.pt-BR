---
title: Migração de conteúdo não UUID para UUID
description: Saiba como migrar conteúdo não UUID para UUID
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: 56f1bd81e74ad9b479b2dcbcf04e1ee82e9a9041
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---

# Migração de conteúdo não UUID para UUID {#id226TI0U20XA}


Você pode migrar seu conteúdo não UUID para UUID com base na versão atual do Experience Manager Guides que você está usando.

>[!IMPORTANT]
>
> Antes de migrar o conteúdo para o servidor UUID, verifique se você tem um servidor não UUID com versão compatível do AEM Guides instalada.

## Matriz de compatibilidade

Use a matriz a seguir para determinar o caminho de migração correto com base na sua versão atual não UUID. Isso garante uma transição tranquila após a migração.

| Versão não UUID necessária para migração | Versão da UUID após a migração | Caminho de atualização compatível após a migração |
|---|---|---|
| 4.3.1 não UUID | 4.3.2 UUID | Depois de migrar para a versão 4.3.2 UUID, você deve instalar diretamente a 4.6.0 (UUID). Quando estiver na versão 4.6.0, atualize para a versão 5.1.0 e instale a 5.1.0 Service Pack 3. |
| 4.6.0 Service Pack 4 não UUID | 4.6.1 UUID | Depois de migrar para a versão 4.6.1 UUID, você deve atualizar diretamente para a 5.1.0 (UUID). Quando a atualização estiver concluída, instale a versão 5.1.0 Service Pack 3. |

## Estimativa de tempo de migração

O utilitário de migração processa ativos a uma taxa média de ~50 ms por ativo. A tabela a seguir fornece estimativas de tempo de migração para um sistema configurado com 64 vCPUs, 128 GB de RAM e armazenamento de dados com suporte de SSD. Os requisitos de memória podem aumentar para repositórios ou ativos maiores com muitas representações ou binários de alta resolução.

>[!NOTE]
>
> O tempo real de migração pode variar dependendo do desempenho do hardware, do throughput do armazenamento, das atividades simultâneas do AEM e da carga geral do sistema.


| **Contagem de ativos** | **Aprox. Hora** |
|-----------------|-------------------------|
| 10 K | ~8 a 9 minutos |
| 50 K | ~42 minutos |
| 100K | ~1,4 horas |
| 250 K | ~3,5 horas |
| 500 K | ~7 horas |
| 750 K | ~10,5 horas |
| 1M | ~14 horas |
| 2M | ~28 horas (~1,2 dias) |
| 3M | ~42 horas (~1,75 dias) |
| 5M | ~69 horas (~2,9 dias) |
| 10M | ~139 horas (~5,8 dias) |


Para obter etapas detalhadas sobre como migrar seu conteúdo, consulte os seguintes artigos:

- [**4.3.1 não UUID para migração de conteúdo UUID 4.3.2**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 não UUID para migração de conteúdo UUID 4.6.1**](./migrate-non-uuid-uuid-4-6.md)



