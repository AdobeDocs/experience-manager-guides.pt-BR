---
title: Relatório de reutilização de conteúdo
description: Saiba como exibir o relatório de reutilização de conteúdo no AEM Guides. Gere o relatório para encontrar a porcentagem de reutilização de conteúdo.
feature: Report Generation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Relatório de reutilização de conteúdo {#id205BB900OQD}

Outro relatório útil que pode ser gerado é o Relatório de reutilização de conteúdo. Esse relatório calcula a porcentagem média de uso de conteúdo, que é muito útil para os gerentes de projeto e proprietários de negócios verem a quantidade de conteúdo que está sendo reutilizada.

>[!TIP]
>
> Para garantir o funcionamento adequado do Relatório de reutilização de conteúdo, é necessário habilitar o fluxo de trabalho de pós-processamento. Entre em contato com o administrador do sistema para ativar fluxos de trabalho de pós-processamento.

Execute as seguintes etapas para exibir o Relatório de reutilização de conteúdo:

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecione **Guias** na lista de ferramentas.

1. Clique no bloco **Relatório de reutilização de conteúdo**.

1. Clique em **Procurar** para escolher um caminho no qual os tópicos residem ou insira o caminho manualmente.

   O relatório é gerado ao examinar o conteúdo nas pastas pai e filho.

1. Clique em **Gerar relatório** para obter o Relatório de Reutilização de Conteúdo.

   ![](images/content-reuse-uuid.png){width="800" align="left"}

   A página do relatório está dividida em duas partes:

   - **Resumo do Relatório:**

     Lista a Reutilização média de conteúdo, que é calculada como Instâncias de reutilização de conteúdo/Contagem total de tópicos. Este relatório considera todas as referências diretas de conteúdo de primeiro nível e referências de tópico para cálculo. As Instâncias de reutilização de conteúdo são calculadas como o total da soma dos valores no campo Número de vezes de reutilização. O tópico mais amplamente reutilizado também está listado no Resumo do relatório. Clicar no link do tópico no Tópico Mais Reutilizado abre a visualização do tópico.

   - **Detalhes:**

     A seção Detalhes contém as seguintes colunas:

      - **Título**: o título do tópico. Clicar no link do título do tópico abre a visualização do tópico.

      - **UUID**: o identificador exclusivo universalmente \(UUID\) do arquivo.

      - **Tamanho**: tamanho dos arquivos em bytes.

      - **Status**: o estado atual do documento - Rascunho, Em Revisão ou Revisado.

      - **Número de Vezes Reutilizado**: Número de vezes que o tópico correspondente foi reutilizado. Isso é calculado como a soma total das entradas nas colunas Referenciado por menos 1.

      - **Referenciado por**: os tópicos nos quais o tópico correspondente foi referenciado. Aqui, somente as referências diretas \(primeiro nível\) são consideradas. Vários tópicos são separados por vírgulas. A UUID do arquivo referenciado também é mencionada entre parênteses. Clicar no link de título do tópico abre a visualização do tópico.


>[!NOTE]
>
> Você também pode exportar o Relatório de reutilização de conteúdo no formato CSV. Para fazer isso, clique no link Exportar para CSV no canto superior esquerdo da tela e escolha um local para salvar o arquivo CSV. Em seguida, você pode abrir esse arquivo CSV em qualquer editor CSV.

**Tópico pai:**[ Relatórios](reports-intro.md)
