---
title: Migração de conteúdo não UUID para UUID
description: Saiba como migrar conteúdo não UUID para UUID
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '205'
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
| 4.3.1 não UUID | 4.3.2 UUID | Depois de migrar para a versão 4.3.2 UUID, você pode instalar diretamente a 4.6.0 (UUID). Quando estiver na versão 4.6.0, atualize para a versão 5.1.0 e instale a 5.1.0 Service Pack 1. |
| 4.6.0 Service Pack 4 não UUID | 4.6.1 UUID | Depois de migrar para a versão 4.6.1 UUID, você pode atualizar diretamente para a 5.1.0 (UUID). Quando a atualização estiver concluída, instale a versão 5.1.0 Service Pack 1. |

Para obter etapas detalhadas sobre como migrar seu conteúdo, consulte os seguintes artigos:

- [**4.3.1 não UUID para migração de conteúdo UUID 4.3.2**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 não UUID para migração de conteúdo UUID 4.6.1**](./migrate-non-uuid-uuid-4-6.md)



