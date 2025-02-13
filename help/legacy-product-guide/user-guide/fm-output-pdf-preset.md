---
title: PDF
description: Gerar e configurar saída de PDF para documentos do FrameMaker no AEM Guides.
feature: Publishing FrameMaker Documents
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 3%

---

# PDF {#id205BB0T20RH}

As seguintes opções estão disponíveis para a saída de PDF:

>[!NOTE]
>
> Para abrir predefinições de saída para o PDF, clique em um arquivo de FrameMaker \(`.fm` ou `.book`\), clique em Predefinições de Saída e, em seguida, clique na opção Saída de PDF.

| opções de PDF | Descrição |
|-----------|-----------|
| Tipo de saída | O tipo de saída que você deseja gerar. Para gerar saída de PDF, escolha a opção PDF. |
| Nome de configuração | Dê um nome descritivo para as configurações de saída de PDF que você está criando. Por exemplo, você pode especificar *saída de clientes internos* ou *saída de usuários finais*. |
| **Configurações do trabalho** |
| Opções | Escolha a predefinição de PDF que deseja usar para gerar a saída de PDF. |
| Gerar PDF marcado | Selecione esta opção para gerar PDF com tags que conterão informações sobre o conteúdo e a estrutura do documento. Essas informações são usadas pelos leitores de tela. |
| Gerar PDF para cada arquivo no livro | Se você estiver gerando saída para um arquivo de livro, selecione esta opção para gerar um PDF separado para cada arquivo no livro. |
| Gerar PDF para revisão apenas | Selecione esta opção para gerar o PDF com o recurso de comentários ativado. |
| Criar destino nomeado para todos os elementos e parágrafos | Selecione essa opção para criar destinos nomeados com base em elementos e parágrafos. |
| **Configurações de Exibição** |
| Abrir documento na página | Especifique o número de página que deve ser exibido ao abrir o PDF. |
| Nível de zoom inicial | Escolha o nível de zoom do documento. |
| Marca de registro | Para imprimir um documento com marcas de corte e de registro, escolha uma opção na lista suspensa Marcas de registro. |
| Largura e altura da página | Especifique a largura e a altura da página. |
| Intervalo de páginas | Escolha se deseja publicar todas as páginas no livro ou um intervalo de páginas. Se você escolher Faixa, deverá especificar a faixa de páginas De e Até. |
| Converter CYMK em RGB | Selecione esta opção para converter cores CYMK em RGB no PDF gerado. |
| Gerar marcadores do PDF | Crie PDF acessível que contenha marcadores. |
| Caminho de destino | O caminho no repositório AEM onde a saída de PDF está armazenada. |
| Executar fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída. |

**Tópico pai:**[ Gerar saída de documentos do FrameMaker](fm-output-generatation.md)
