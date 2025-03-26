---
title: Relatório de reutilização de conteúdo
description: Saiba como exibir o relatório de reutilização de conteúdo no AEM Guides. Gere o relatório para encontrar a porcentagem de reutilização de conteúdo.
exl-id: ccae4303-75b1-4077-829a-7ef6a14fd8ad
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Relatório de reutilização de conteúdo {#id205BB900OQD}

Outro relatório útil que pode ser gerado é o Relatório de reutilização de conteúdo. Esse relatório calcula a porcentagem média de uso de conteúdo, que é muito útil para os gerentes de projeto e proprietários de negócios visualizarem a quantidade de conteúdo que está sendo reutilizada.

>[!TIP]
>
> Para garantir o funcionamento adequado do Relatório de reutilização de conteúdo, é necessário habilitar o fluxo de trabalho de pós-processamento. Entre em contato com o administrador do sistema para ativar fluxos de trabalho de pós-processamento.

Execute as seguintes etapas para exibir o Relatório de reutilização de conteúdo:

1. Selecione o logotipo do Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecione **Guias** na lista de ferramentas.

1. Selecione o bloco **Relatório de reutilização de conteúdo**.

1. Selecione **Procurar** para escolher um caminho no qual os tópicos residem ou insira o caminho manualmente.

   O relatório é gerado ao examinar o conteúdo nas pastas pai e filho.

1. Selecione **Gerar relatório** para obter o Relatório de Reutilização de Conteúdo.

   ![](images/content-reuse-uuid.png){align="left"}

   A página do relatório está dividida em duas partes:

   - **Resumo do Relatório:**

     Lista a Reutilização média de conteúdo, que é calculada como Instâncias de reutilização de conteúdo/Contagem total de tópicos. Este relatório considera todas as referências diretas de conteúdo de primeiro nível e referências de tópico para cálculo. As Instâncias de reutilização de conteúdo são calculadas como o total da soma dos valores no campo Número de vezes de reutilização. O tópico mais amplamente reutilizado também está listado no Resumo do relatório. Selecionar o link do tópico no Tópico Mais Reutilizado abre a pré-visualização do tópico.

   - **Detalhes:**

     A seção Detalhes contém as seguintes colunas:

      - **Título**: o título do tópico. Selecionar o link do título do tópico abre a visualização do tópico.

      - **UUID**: o identificador exclusivo universalmente \(UUID\) do arquivo.

      - **Tamanho**: tamanho dos arquivos em bytes.

      - **Status**: o estado atual do documento - Rascunho, Em Revisão ou Revisado.

      - **Número de Vezes Reutilizado**: Número de vezes que o tópico correspondente foi reutilizado. Isso é calculado como a soma total das entradas nas colunas Referenciado por menos 1.

      - **Referenciado por**: os tópicos nos quais o tópico correspondente foi referenciado. Aqui, somente as referências diretas \(primeiro nível\) são consideradas. Vários tópicos são separados por vírgulas. A UUID do arquivo referenciado também é mencionada entre parênteses. Selecionar no link de título do tópico abre a visualização do tópico.


>[!NOTE]
>
> Você também pode exportar o Relatório de reutilização de conteúdo no formato CSV. Para fazer isso, selecione o link Exportar para CSV no canto superior esquerdo da tela e escolha um local para salvar o arquivo CSV. Em seguida, você pode abrir esse arquivo CSV em qualquer editor CSV.

**Tópico pai:**[ Introdução aos relatórios](reports-intro.md)
