---
title: PDF
description: Gere e configure a saída do PDF para documentos do FrameMaker no AEM Guides.
exl-id: df3d3cd8-2aa1-4d82-8756-c3f5555cb904
feature: Publishing FrameMaker Documents
role: User
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 3%

---

# PDF {#id205BB0T20RH}

As seguintes opções estão disponíveis para a Saída do PDF:

>[!NOTE]
>
> Para abrir predefinições de saída para o PDF, selecione um arquivo FrameMaker \(`.fm` ou `.book`\), selecione as Predefinições de Saída e escolha a opção Saída do PDF.

| Opções do PDF | Descrição |
|-----------|-----------|
| Tipo de saída | O tipo de saída que você deseja gerar. Para gerar a saída do PDF, escolha a opção PDF. |
| Nome de configuração | Dê um nome descritivo para as configurações de saída do PDF que você está criando. Por exemplo, você pode especificar *saída de clientes internos* ou *saída de usuários finais*. |
| **Configurações do trabalho** |  |
| Opções | Escolha a predefinição do PDF que deseja usar para gerar a saída do PDF. |
| Gerar PDF com tags | Selecione essa opção para gerar PDFs marcados que conterão informações sobre o conteúdo e a estrutura do documento. Essas informações são usadas pelos leitores de tela. |
| Gerar PDF para cada arquivo no livro | Se você estiver gerando saída para um arquivo de livro, selecione essa opção para gerar uma PDF separada para cada arquivo no livro. |
| Gerar PDF somente para revisão | Selecione esta opção para gerar o PDF com o recurso de comentários ativado. |
| Criar destino nomeado para todos os elementos e parágrafos | Selecione essa opção para criar destinos nomeados com base em elementos e parágrafos. |
| **Configurações de Exibição** |  |
| Abrir documento na página | Especifique o número de página que deve ser exibido ao abrir o PDF. |
| Nível de zoom inicial | Escolha o nível de zoom do documento. |
| Marca de registro | Para imprimir um documento com marcas de corte e de registro, escolha uma opção na lista suspensa Marcas de registro. |
| Largura e altura da página | Especifique a largura e a altura da página. |
| Intervalo de páginas | Escolha se deseja publicar todas as páginas no livro ou um intervalo de páginas. Se você escolher Faixa, deverá especificar a faixa de páginas De e Até. |
| Converter CYMK em RGB | Selecione essa opção para converter cores CYMK em RGB no PDF gerado. |
| Gerar marcadores do PDF | Crie PDF acessíveis que contenham marcadores. |
| Caminho de destino | O caminho no repositório do AEM onde a saída do PDF está armazenada. |
| Executar fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída. |

**Tópico pai:**&#x200B;[&#x200B; Gerar saída de documentos do FrameMaker](fm-output-generatation.md)
