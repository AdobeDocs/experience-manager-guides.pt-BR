---
title: Configurar o trabalho de limpeza da árvore B para serviços em nuvem
description: Configurar o trabalho de limpeza da árvore B para serviços em nuvem
feature: Output Generation
role: Admin
level: Experienced
exl-id: de464e92-f17b-4c99-98f2-fdba8d214129
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 3%

---

# Configurar limpeza da árvore B

Configure o trabalho de limpeza da árvore B e gerencie a configuração `Guides BTree deletion` para manter o sistema otimizado e o armazenamento limpo.

## Configurar trabalho de limpeza da árvore B

Execute as seguintes etapas para configurar o trabalho de limpeza da árvore B:

1. Use as instruções fornecidas em [Substituições de configuração](../cs-install-guide/download-install-additional-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Valor padrão:** &quot;0 0 0 * * * ?&quot; |


## Configurar a opção de ativação da exclusão da árvore B dos guias

Execute as seguintes etapas para ativar a configuração:

1. Use as instruções fornecidas em [Substituições de configuração](../cs-install-guide/download-install-additional-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Valor padrão:** &quot;True&quot; |
