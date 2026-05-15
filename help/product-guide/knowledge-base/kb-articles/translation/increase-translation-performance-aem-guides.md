---
title: Aumente o desempenho da tradução para seus arquivos DITA nos guias do AEM
description: Práticas recomendadas, dicas e truques para aumentar o desempenho do projeto de tradução DITA no AEM Guides
feature: Translation
role: User, Admin
author: Pulkit Nagpal (punagpal)
exl-id: d7e4f3ae-2143-4767-b7ab-c89f5e5eef59
TQID: https://experienceleague.adobe.com/n6-b3-ZsOIueVYWgcm1NkDLKRAOwQhWxctbgj7Q6P1U
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 0%

---

# Práticas recomendadas a serem seguidas para tradução no AEM Guides

O desempenho do seu projeto de tradução pode diminuir à medida que a atividade de tradução no sistema aumenta ao longo do tempo.

Cada projeto de tradução gera vários grupos de usuários para acesso, resultando em um aumento no número de grupos de usuários no sistema. À medida que o número de grupos de usuários se expande, ele pode retardar gradualmente as operações de CRUD relacionadas às permissões do usuário, afetando potencialmente o desempenho geral do AEM. Além disso, se os projetos de tradução permanecerem ativos após a conclusão, isso poderá afetar negativamente o desempenho da sincronização de tradução entre o AEM e o fornecedor da tradução.

**Seguir as práticas recomendadas abaixo ajudará a manter um ambiente eficiente.**

## Se você estiver em uma build com mais de 4.6 (no local) ou 2404 (nuvem):

- Marcar todos os projetos como &quot;Inativos&quot; depois que a tradução for concluída e aprovada.O projeto permanece disponível para revisão e é simplesmente marcado como inativo.
   - Seguir essas etapas ajudará a manter o desempenho geral da tradução com boa integridade.
     ![Projeto de tradução inativo &#x200B;](../assets/translation/translation-project-image1.png)

- Para a pasta de projetos mais antigos, que está marcada como inativa, aprovada e revisada deve ser excluída
   - Seguir essas etapas ajudará a manter o desempenho geral da tradução com boa integridade, limpando os arquivos de tradução temporários e os grupos de usuários associados a esta pasta do projeto.
     ![Excluir projeto e pasta de tradução &#x200B;](../assets/translation/translation-project-image2.png)


## Se você estiver no, build 4.6 ou 2404 ou posterior:

Você pode continuar seguindo as mesmas etapas mencionadas acima. A partir da versão 4.6/2404, o AEM Guides apresenta uma configuração de editor para que os administradores desativem a exclusão automática de projetos de tradução.

Consulte: [Excluir ou desabilitar automaticamente um projeto de tradução concluído](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/author-content/create-preview-topics/author-content-aem-guides/work-with-web-editor/translate-documents-web-editor#automatically-delete-or-disable-a-completed-translation-project)

![Configurações automatizadas para excluir e desabilitar o projeto de tradução no AEM Guides &#x200B;](../assets/translation/translation-project-image3.png)
