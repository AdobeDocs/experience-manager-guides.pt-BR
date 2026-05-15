---
title: Notas de versão | Correção de problemas na versão 4.6.0 do Service Pack 4 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 4.6.0 Service Pack 4 do Adobe Experience Manager Guides
role: Leader
exl-id: ad69ea47-7880-43d1-8567-cd608fedb462
TQID: https://experienceleague.adobe.com/4ILARUO5umX41xE3Lcie-FsP396sgSqfbrWlMqdjsQ4
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 234
ht-degree: 4%

---

# Correção de problemas na versão 4.6.0 do Service Pack 4 (abril de 2025)


Este artigo aborda os bugs corrigidos em várias áreas da versão 4.6.0 Service Pack 4 do Adobe Experience Manager Guides.

Saiba mais sobre as [instruções de atualização do 4.6.0 Service Pack 4 versão](upgrade-instructions-4-6-0-sp4.md).

## Criação

- Arrastar e soltar uma imagem em um tópico na exibição **Autor** faz com que a referência da imagem seja interrompida, resultando em perda de dados. (25769)
- Arrastar e soltar um `topicref` em um Mapa na exibição **Autor** falha ao executar a operação pretendida e remove o `topicref` ao lado do `topicref` arrastado. (19460)
- Falha ao fechar conexões da sessão JCR ao atualizar ou criar tópicos resulta em vazamentos de memória e tempo de inatividade do serviço. (26282)

## Publicação

- A publicação do PDF nativo continua indefinidamente se o conteúdo DITA tiver um link da Web sem ter o escopo `external`. (26434)
- Ao criar uma nova linha de base com um grande número de rótulos, isso causa falha no carregador de rótulos e impede que os rótulos sejam buscados. (16232)
- A publicação de PDFs nativos e sites do AEM é interrompida e colocada em fila quando há erros no conteúdo. (26516)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para esta versão:

- A publicação do PDF nativo no Windows encontra falhas quando o conteúdo DITA contém um link externo que não inclui o atributo `scope`.
