---
title: Implantação de indexação personalizada para configuração no local
description: Saiba como personalizar o conteúdo de índice para configuração no local
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 8a9a82e79c757e403141e853aafbc64e1618c30a
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# Reindexação do recurso Localizar e substituir (exibição do Source)

A reindexação é necessária para habilitar o recurso **Localizar e substituir (modo de exibição Source)**, que permite verificar todo o conteúdo visível no modo de exibição Autor e também o conteúdo Source subjacente (estrutura XML, incluindo elementos, marcas e valores de atributo) da cadeia de caracteres pesquisada.

## Reindexação

Para configurações no local, a definição de índice é incluída no pacote. Para habilitar o recurso, você deve reindexar o conteúdo.

Inicie a reindexação definindo a propriedade `reindex=true (Boolean)` no nó: ` /oak:index/guidesAssetLucene` para reindexar o conteúdo capturado anteriormente.

O processo de reindexação continuará até que o sistema altere automaticamente essa propriedade de volta para false. Você pode monitorar o progresso da operação de reindexação nos logs do sistema.