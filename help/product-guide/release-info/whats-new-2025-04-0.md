---
title: Notas de versão | Novidades da versão 2025.04.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2025.04.0 do Adobe Experience Manager Guides
role: Leader
exl-id: 5d28119b-641f-402b-833c-6f7554e7c273
source-git-commit: f4ed3c8b70c47beb1f97c6703ade4d4f49fa814e
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Novidades da versão 2025.04.0 (abril de 2025)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2025.04.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2025.04.0](fixed-issues-2025-04-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.04.0](../release-info/upgrade-instructions-2025-04-0.md).

## Atributo &quot;Formato&quot; adicionado para links de referência

O Adobe Experience Manager Guides agora adiciona um atributo **format** para links de referência no Editor. Este atributo é exibido na **exibição do Source** e indica claramente o tipo de arquivo, como:

- Para arquivos com extensão **.pdf**, o formato será definido como **pdf**
- Para arquivos com uma extensão **.html**, o formato será definido como **html**
- Para arquivos com arquivos **.dita** ou **.ditamap**, o formato será definido como **dita**

Além disso, arquivos com uma extensão **.xml** também terão seu formato definido como **dita**. Para arquivos sem qualquer extensão, o formato será deixado em branco. Além disso, para qualquer link de referência com um escopo definido como **externo**, o formato será definido como **html** independentemente da extensão de arquivo nos links de referência.


## Comunicação precisa para arquivos grandes no Editor

O Experience Manager Guides agora notifica que um arquivo é classificado como arquivo grande e determinadas funcionalidades, como desfazer, refazer, o painel de estrutura de tópicos e o marcador sujo, podem não funcionar conforme esperado. Uma mensagem de alerta é exibida na parte superior da interface para arquivos grandes, como mostrado no trecho abaixo, indicando o número de elementos com base no parâmetro **largeFileTagCount** no arquivo **uiconfig.json**.

Além disso, a contagem de tags é mostrada na barra inferior, com uma dica de ferramenta sendo exibida ao passar o mouse sobre ela. Selecionar a guia **Saiba mais** fornece informações detalhadas sobre como manipular arquivos grandes. Este alerta está disponível somente para arquivos DITA e está visível em todas as exibições: Autor, Source e Layout.

Para obter mais detalhes, consulte [Manuseio de arquivos grandes no Editor](../user-guide/web-editor-other-features.md#handling-large-files-in-the-editor).

![](assets/add-toast-tag-count.png){width="800" align="left"}

## A Linha de base exportada agora inclui o estado do Documento

O recurso Exportar Linha de Base agora inclui o **estado do documento** junto com detalhes importantes, como título, nome de arquivo, tipo de arquivo e número de versão no instantâneo da linha de base. Esse aprimoramento melhora o gerenciamento da linha de base, fornecendo uma visão geral mais abrangente da linha de base.

Para obter mais detalhes, exiba [Criar e gerenciar linhas de base do Console de mapa](../user-guide/web-editor-baseline.md#manage-baselines).

## Experiência de pesquisa aprimorada para o painel Conteúdo reutilizável

O Experience Manager Guides apresenta uma experiência de pesquisa aprimorada no Painel de conteúdo reutilizável. Com essa atualização, a pesquisa de qualquer palavra-chave agora verifica todos os arquivos adicionados como conteúdo reutilizável, e não apenas os abertos, garantindo que você encontre a posição exata da palavra-chave em todas as ocorrências, independentemente de os contêineres estarem abertos ou recolhidos. Além disso, ao limpar a barra de pesquisa, o estado original de todos os contêineres é mantido, fornecendo uma funcionalidade de pesquisa mais eficiente e fácil de usar.

Para obter mais detalhes, consulte [Conteúdo reutilizável](../user-guide/web-editor-features.md#reusable-content).


## Atualização da versão do Java para contêineres de microsserviço

Para ambientes de nuvem habilitados para microsserviços, faremos a transição para o Java 21, garantindo que os processos existentes de DITA-OT e geração nativa do PDF permaneçam inalterados. O fluxo de trabalho existente do DITA-OT 3 continuará a funcionar perfeitamente com o Java 21.  Além disso, o DITA-OT 4 estará totalmente operacional, permitindo que os usuários gerem PDFs usando o DITA-OT e o PDF nativo, bem como produzam saídas para sites AEM nativos e outros formatos.
