---
title: Novo mecanismo de publicação para o PDF nativo | Geração de saída do PDF
description: Saiba como trabalhar com o novo mecanismo de publicação para publicação nativa do PDF
feature: Publishing, Native PDF Output
role: User
TQID: https://experienceleague.adobe.com/GV3iYtBdFVrQwFjdvfqnfDIWPMugO3hFjS4FZqspG2M
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: afb45297-4313-4f67-818e-bc0b03abe086
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f6b497f1-f8e0-42ce-8e95-56c28d94026e
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 010a11e20d518064549ce7d66648586f49f572ec
workflow-type: tm+mt
source-wordcount: 913
ht-degree: 0%

---

# Trabalhar com o mecanismo nativo do PDF v2

O novo mecanismo de publicação *Mecanismo nativo do PDF v2*, é baseado em uma estrutura de geração do PDF atualizada e inclui alterações no manuseio de fontes, processamento de CSS e comportamento de renderização.

Como resultado, a saída de PDF gerada com o novo mecanismo de publicação pode ser diferente da saída gerada com o mecanismo PDF existente (*Mecanismo PDF nativo v1*). As diferenças podem ser visíveis em áreas como layout de texto, espaçamento, estilo, renderização de imagem e formatação de nota de rodapé.

Por exemplo, o mecanismo Native PDF v2 oferece suporte a `OpenType` fontes, enquanto o mecanismo Native PDF v1 depende principalmente de `TrueType` fontes. Aprimoramentos de renderização semelhantes podem afetar a aparência geral dos PDFs gerados.

Para obter detalhes sobre como habilitar o mecanismo nativo do PDF v2 em seu ambiente, consulte [Configurar o novo mecanismo de publicação para o PDF nativo](./conf-new-pdf-engine.md).

## Atualizações de CSS recomendadas para o novo mecanismo de publicação

Se você quiser preservar a aparência da saída do PDF gerada pelo mecanismo PDF nativo v1 ao usar o mecanismo PDF nativo v2, talvez seja necessário atualizar seu CSS personalizado. As alterações de CSS recomendadas descritas abaixo podem ajudar a manter a consistência da saída após ativar a nova configuração.

| Descrição | Atualização de CSS recomendada |
|-------------|------------------------------------------------|
| Imagens dimensionadas podem parecer diferentes devido a alterações no comportamento de renderização da imagem. | Para restaurar o comportamento de renderização da imagem, adicione:<br><br><pre><code>&quot;css
renderização de imagem: pixelada;
&quot;</code></pre> |
| O alinhamento da guia do índice pode parecer um pouco diferente devido a alterações no comportamento de renderização da guia. | Para restaurar o alinhamento da guia do índice, ajuste o estilo dos elementos da guia do índice na folha de estilos personalizada. As alterações de CSS necessárias podem variar dependendo do layout e da formatação do índice. |
| O espaçamento e a quebra automática de linha do texto podem diferir devido a alterações na renderização de fonte e no processamento do layout do glifo. | Se sua folha de estilos usar a família de fontes `sans-serif` ou as fontes que exibem diferenças de espaçamento, adicione:<br><br><pre><code>&quot;css
body { -ro-glyph-layout-mode: quality; }
&quot;</code></pre> |
| As referências de nota de rodapé podem não aparecer mais como marcadores sobrescritos devido a alterações no estilo padrão da nota de rodapé. | Para restaurar marcadores de nota de rodapé de estilo sobrescrito, adicione:<br><br><pre><code>&quot;css
.fn::marcador de nota de rodapé &lbrace;
  content: counter(nota de rodapé) &quot; &quot;;
  vertical-align: super;
  font-size: 65%;
&rbrace;
&quot;</code></pre> |
| O texto sublinhado pode aparecer com mais espaço entre ele e o sublinhado devido a alterações no posicionamento do sublinhado. | Para restaurar o posicionamento de sublinhado, use a propriedade `text-underline-offset` e ajuste o valor de deslocamento conforme necessário. Por exemplo:<br><br><pre><code>&quot;css
text-decoration: underline;
text-underline-offset: -0.1em;
&quot;</code></pre> |
| O espaçamento entre os marcadores de lista e o texto do item de lista pode ser diferente devido a alterações no comportamento de renderização da lista. | Para restaurar o espaçamento, aumente o preenchimento esquerdo para os itens da lista. Por exemplo:<br><br><pre><code>&quot;css
.etapa &lbrace;
  margem superior: 0,3rem;
  margem inferior: 0,5rem;
  preenchimento à esquerda: calc(1.5rem + 1ch);
&rbrace;
&quot;</code></pre> |
| O espaçamento antes dos cabeçalhos pode ser diferente devido a alterações no comportamento de recolhimento de margem. | Para restaurar o espaçamento, revise as margens dos elementos adjacentes e reduza ou remova as margens superiores e inferiores sobrepostas, quando necessário. Por exemplo:<br><br><pre><code>&quot;css
h1.chapter { margin-top: 0; }
.chaptoc-body { margin-bottom: 0; }
&quot;</code></pre> |
| Os marcadores de seleção gerados com CSS podem aparecer com tamanhos ou estilos diferentes, pois são renderizados usando fontes de fallback diferentes. | Para renderizar marcadores de forma consistente, use uma família de fontes que contenha ambos os glifos. Por exemplo:<br><br><pre><code>&quot;css
::marcador &lbrace;
  família de fontes: - ro- símbolos !important;
&rbrace;
&quot;</code></pre> |
| Os marcadores de lista circular gerados por CSS podem aparecer parcialmente cortados ou truncados devido a alterações no comportamento de posicionamento do marcador. | Para restaurar a aparência dos marcadores de lista circular, evite usar o posicionamento absoluto para o marcador. Se o posicionamento absoluto for necessário, especifique explicitamente um valor `top` apropriado para posicionar corretamente o marcador. |
| A ordem de leitura dos itens de lista na saída PDF/UA pode ser diferente quando os itens de lista usam estilos de posicionamento como `position: relative`. | Para fazer com que a ordem de leitura siga a estrutura do documento de origem mais de perto, aplique a seguinte propriedade CSS aos itens da lista:<br><br><pre><code>&quot;css
li &lbrace;
  -reordenação de tinta: evite;
&rbrace;
&quot;</code></pre> |


## Soluções alternativas para problemas conhecidos

As soluções alternativas a seguir podem ajudar a resolver problemas conhecidos na saída gerada do PDF ao usar o mecanismo PDF v2 nativo.

- `text-decoration` propriedades css aplicadas ao conteúdo da tabela não são renderizadas na saída do PDF.

  **Solução alternativa**: aplique as propriedades de decoração de texto aos elementos `span` dentro do conteúdo da tabela, em vez de aplicá-los diretamente aos elementos da tabela.

- As propriedades CSS `-ro-colorbar-top-left` e `-ro-colorbar-top-right` não afetam a barra de cores na saída do PDF.

  **Solução alternativa**: remova os valores correspondentes da folha de estilos do usuário em `mergedHTML.json` ou adicione `!important` aos valores de propriedade no documento CSS para que eles não sejam substituídos pela folha de estilos do usuário.

- Barras de cores podem aparecer mescladas quando a largura da página é restrita, pois as barras de cores não são dimensionadas para baixo com o tamanho da página na saída do PDF.

  **Solução alternativa**: exibir as barras cinza e colorida em diferentes lados da página ou ajustar as configurações da barra de cores para que elas não se sobreponham em larguras de página menores.

## Correção de problemas com o novo mecanismo de publicação

Os seguintes problemas na saída do PDF gerada com o _Mecanismo Nativo do PDF v1_ foram corrigidos no _Mecanismo Nativo do PDF v2_:

- Ao gerar uma saída Native PDF para determinado conteúdo, somente a primeira página é renderizada no PDF, apesar do HTML intermediário que contém o conteúdo completo em várias páginas. (GUIDES-28270)
- A ordem de leitura do conteúdo na saída nativa do PDF com as configurações de acessibilidade ativadas está incorreta. Os números de página dos rodapés são lidos antes do conteúdo principal em vez de no final. (GUIDES-27790)
- A barra de cores na saída do PDF nativo não se alonga pela largura total da página e se sobrepõe quando o tamanho da página é personalizado, fazendo com que algumas caixas de cores fiquem ocultas. (GUIDES-15505)
- O seletor `CSS:is()pseudo-class` não é respeitado na saída do PDF nativo, resultando em diferenças de estilo em comparação à renderização do navegador. (GUIDES-11328)