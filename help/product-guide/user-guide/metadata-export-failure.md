---
title: A exportação de metadados falha com a exceção "A cadeia de caracteres é muito longa" no Experience Manager Guides
description: Entenda por que a exportação de metadados pode falhar para o conteúdo de Guias na interface do usuário do Assets.
feature: Authoring, Publishing
role: User
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 1c61df4820e559417410d25c81800637481b040c
workflow-type: tm+mt
source-wordcount: 274
ht-degree: 0%

---

# Por que a exportação de metadados para uma pasta falha com a exceção &quot;A cadeia de caracteres é muito longa&quot;?

Ao [exportar metadados](https://experienceleague.adobe.com/pt-br/docs/experience-manager-65/content/assets/using/metadata#export-metadata) para uma pasta da interface do usuário do Assets, o trabalho de exportação pode falhar com a exceção `String is too long`. Isso normalmente acontece quando a pasta contém propriedades específicas do Experience Manager Guides que armazenam valores que não são de cadeia de caracteres, como `baselineObj`.

**Por que isso ocorre?**

Algumas propriedades armazenadas no nó de metadados de um ativo são usadas internamente pelo Experience Manager Guides e contêm dados, como objetos JSON, em vez de valores de sequência simples. Ao exportar metadados para uma pasta, se **Propriedades a serem exportadas** estiver definido como **Todas**, o trabalho de exportação tentará converter todas as propriedades em uma cadeia de caracteres e falhará nas propriedades que contêm esse tipo de dados.

**Como isso é evitado?**

Para evitar essa falha, as seguintes propriedades são excluídas da exportação de metadados por padrão na **Configuração do exportador de metadados do ativo**:

- `baseline`
- `namedoutputs`
- `conditionpresets`
- `nextgenbaselinestore`

**Ainda posso exportar essas propriedades?**

Sim. Se você precisar de uma ou mais dessas propriedades na exportação, poderá editar a **Configuração do exportador de metadados do ativo** e removê-los da lista de exclusão.

A remoção de uma propriedade da lista de exclusão não garante que a exportação será bem-sucedida. Dependendo do tamanho e do conteúdo dos dados subjacentes, o processo ainda poderá falhar com a mesma exceção. Se você encontrar isso depois de reativar uma propriedade, adicione-a de volta à lista de exclusão para restaurar o comportamento de exportação padrão e confiável.
