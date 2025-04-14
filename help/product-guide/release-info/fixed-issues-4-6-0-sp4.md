---
title: Notas de versão | Correção de problemas na versão 4.6.0 do Service Pack 4 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 4.6.0 Service Pack 4 do Adobe Experience Manager Guides
role: Leader
source-git-commit: f9a03ae620a362989a36ebaefb264ea28220a4b3
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 1%

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
