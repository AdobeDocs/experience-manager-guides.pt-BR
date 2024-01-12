---
title: Converter conteúdo não UUID sem versões em conteúdo UUID
description: Saiba como migrar conteúdo não UUID sem versões.
exl-id: 44b5660d-9961-4463-9686-53085249fb05
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 0%

---

# Migrar conteúdo sem versão

>[!IMPORTANT]
>
> Você pode escolher essa abordagem de migração se quiser ignorar ou não as versões de ativos.


1. Baixe e carregue ativos da instância que não é UUID para a instância UUID diretamente da interface do usuário do AEM Assets usando ferramentas de Adobe, como o aplicativo para desktop AEM.

1. Habilite o fluxo de trabalho do ativo de atualização do DAM e execute-o em todos os ativos depois de importar o conteúdo para criação de GUID.
