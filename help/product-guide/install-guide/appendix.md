---
title: Apêndice
description: Saiba como preparar arquivos do InDesign para conversão
exl-id: 02da0e61-7a73-4c4c-9bd7-2664d90fa728
feature: InDesign File Conversion
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2851'
ht-degree: 0%

---

# Apêndice {#id195AD0L60Y4}

## Preparar arquivos de InDesign para conversão {#id195DBF0045Z}

O InDesign fornece aos autores um conjunto avançado de recursos para criar documentos atraentes e complexos. Geralmente, isso significa que as várias partes de um documento são colocadas na página visualmente, mas sem nenhuma tentativa de fornecer nenhum fluxo entre esses quadros de texto. Quando a &#39;*ordem de leitura*&#39; dos quadros de texto não estiver definida, o arquivo IDML conterá histórias que podem não seguir nenhuma ordem significativa. O resultado final será um ou mais tópicos DITA com parágrafos, tabelas e gráficos em uma ordem aleatória.

Embora seja possível editar o conteúdo DITA em uma ordem sensata em um editor DITA, é muito mais fácil corrigir o arquivo InDesign antes de criar o arquivo IDML. Isso pode ser feito sem alterar a aparência do documento de origem. Também tem a vantagem de tornar o documento de origem acessível, definindo corretamente a ordem de leitura.

***Encadeando quadros de texto***

O InDesign usa o termo *&#39;threading&#39;* para o processo de vinculação de um quadro a outro. Para obter mais detalhes sobre quadros de texto de encadeamento, consulte o tópico *[Texto de encadeamento](https://helpx.adobe.com/in/indesign/using/threading-text.html)* na documentação do InDesign.

***Quadros sobrepostos***

Alguns documentos do InDesign usam quadros sobrepostos não encadeados por motivos de layout. Pode ser muito difícil mesclar esse conteúdo na thread principal. A melhor opção pode ser editar o resultado no ambiente DITA.

***histórias de InDesigns***

Cada fluxo encadeado de conteúdo em um documento de InDesign é chamado de &#39;*história*&#39;. Para obter melhores resultados, é recomendável manter o número de histórias limitado. No entanto, há algumas partes do documento que podem não ser necessárias na saída DITA. Por exemplo, rodapés de página raramente são necessários, mas podem aparecer no meio de um tópico se não forem tratados com cuidado.

A maneira mais fácil de excluir texto não necessário no documento é fornecer a ele uma *Marca de parágrafo* especial, usada somente para o conteúdo indesejado. Por exemplo, em vez de reutilizar um *\[Parágrafo básico\]* para o rodapé, crie uma tag *Rodapé* dedicada. Em seguida, no arquivo MapStyle, basta definir os parágrafos *Footer* para serem soltos desta forma:

```XML
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Mapeamento para tipos de documentos DITA***

É essencial que o documento de origem tenha pelo menos um Estilo de parágrafo ou Elemento que possa marcar o início de um tópico. É comum documentos usarem *Cabeçalho1* como o nome dos títulos de nível superior no documento. Em seguida, você pode criar um mapeamento desse estilo para um tipo de documento DITA específico. Se o seu documento estiver bem organizado e o uso do *Cabeçalho1* for constante em todo o documento, você obterá bons resultados.

***Vários documentos DITA***

Se alguns dos parágrafos *Cabeçalho1* precisarem ser convertidos em diferentes tipos de documento DITA, duplique o estilo de parágrafo no InDesign. Dê a esses estilos um nome fácil de reconhecer, como *Heading1\_genTask* ou *Heading1\_troubleshooting*, conforme apropriado. Em seguida, configure o arquivo mapStyle como mostrado abaixo:

```XML
<doctypes>
   <doctypeParaRule style="Heading1" local="0" mapToDoctype="concept">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_genTask" local="0" mapToDoctype=" generalTask">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_troubleshooting" local="0"mapToDoctype=" troubleshooting">
      <attributeRules createID="true"/>
   </doctypeParaRule>
</doctypes>
```

***Documentos de InDesign estruturados***

O InDesign tem uma relação ampla com XML. Embora um documento possa incluir um DTD XML e a matéria principal possa ser válida em relação a esse DTD, também é possível criar documentos híbridos nos quais parte do conteúdo é XML, mas nenhum DTD está incluído. Esses são os casos indesejáveis para uma conversão bem-sucedida em DITA. Se um documento contiver partes XML, tente salvar a saída em XML e ver se os resultados são aceitáveis. Caso contrário, o conteúdo DITA também incluirá conteúdo inválido ou poderá falhar completamente.

***Formatação da tabela***

A conversão das regras de formatação da tabela do InDesign para a formatação de tabela equivalente em DITA é um processo complexo. Isso se deve aos recursos de formatação avançada disponíveis nos arquivos de origem em comparação às opções básicas fornecidas pelo modelo de tabela Oasis \(CALS\) usado no DITA. O alinhamento de texto vertical e horizontal é fornecido e fornece resultados semelhantes, embora o Texto justificado seja sempre justificado de acordo com a direção do texto, enquanto o InDesign permite Justificado à esquerda e Justificado à direita.

O manuseio de separadores de coluna e linha pelo InDesign é novamente muito mais capaz do que as opções básicas do modelo de tabela do Oasis. O InDesign fornece quatro bordas de célula: Tipo de borda \(sólida ou padrão\), Peso da borda, Cor da borda, Tonalidade da borda, Cor de espaço da borda e Tonalidade de espaço da borda. Todos eles devem ser mapeados para as bordas à direita e abaixo de cada célula \(elemento de entrada\) onde as únicas opções são 0 ou 1 - ocultar a borda ou mostrar a borda.

A decisão fronteiriça em InDesign pode ser aplicada nos seguintes níveis:

- Estilos de Tabela
- Estilos de Célula
- Substituições locais em cada célula

O processo de conversão do InDesign para o DITA aplica a decisão de fronteira da seguinte forma:

- Os Estilos de Tabela são mapeados para o atributo `colspec/@colsep` de regras verticais. As regras horizontais estão mapeadas para o atributo `row/@rowsep`. Em ambos os casos, se a borda não estiver definida, o atributo não será criado.
- Os Estilos de Célula são mapeados para os atributos `entry/@colsep` e `entry/@rowsep`. Esses valores substituirão qualquer regra de borda derivada do Estilo de tabela.
- As substituições locais aplicam a formatação diretamente à célula e substituem Estilos de Tabela e Estilos de Célula.

***Padrões alternados***

Os Estilos de Tabela de InDesign permitem que as regras de coluna e célula sigam um padrão alternado. Embora esse recurso seja compatível com a conversão, os resultados só serão óbvios quando um grupo de padrão for mapeado para mostrar a regra \(1\) e o outro grupo de padrão for mapeado para ocultar a regra \(0\).

## Preparar o arquivo de mapeamento para migração do InDesign para o DITA {#id194AF0003HT}

A conversão DITA correta requer um arquivo de mapeamento que corresponda ao conteúdo do documento de origem. Para documentos de InDesign não estruturados, isso significa que todos os Estilos de parágrafo e de caractere disponíveis precisam ser mapeados. Para documentos de InDesign estruturados XML, todos os elementos em seu DTD associado devem ser mapeados.

Os arquivos de mapeamento para documentos de InDesign não estruturados e estruturados são diferentes. Isso se deve aos requisitos de processamento mais complexos para converter conteúdo original não estruturado em DITA.

Uma amostra do arquivo de mapeamento é fornecida abaixo:

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE styleMap SYSTEM "mapStyle.dtd">
<styleMap xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="mapStyle.xsd" >
   <doctypes>
      <mapDoctypeParaRule root="itpx:stories" mapToDoctype="map">
         <attributeRules createID="true">
            <addNew name="outputclass" value="map"/>
         </attributeRules>
      </mapDoctypeParaRule>
      <doctypeParaRule style="Heading 1" local="0" mapToDoctype="concept">
         <attributeRules createID="true"/>
      </doctypeParaRule>
      <doctypeParaRule style="Heading A" local="0" mapToDoctype="topic">
         <attributeRules createID="true"/>
      </doctypeParaRule>
   </doctypes>
   <wrappingRules>
      <wrap elements="li+" context="number" wrapper="ol">
         <attributeRules createID="true"/>
      </wrap>
      <wrap elements="li+" context="bullet" wrapper="ul">
         <attributeRules createID="true"/>
      </wrap>
   </wrappingRules>
   <paragraphStyleRules>
      <paraRule style="Heading 2" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Heading 3" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|n|-|-]" context="number" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="0" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Title" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
   </paragraphStyleRules>
   <characterStyleRules>
      <charRule style="Bold" local="0" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="Code" local="0" mapTo="codeph">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Bold|-|-|-|-|-|-|-]" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Italic|-|-|-|-|-|-|-]" mapTo="i">
         <attributeRules createID="false"/>
      </charRule>
   </characterStyleRules>
</styleMap>
```

O arquivo de mapeamento é um arquivo XML com uma estrutura simples que lista todos os estilos de parágrafo de origem e códigos de estilo de caractere. O conteúdo do arquivo é explicado abaixo:

**Mapeamento de estilo**

No elemento `styleMap`, você pode especificar dois atributos opcionais - `@map_date` e `@map_version` para gravar a versão do arquivo de mapeamento.

**Tipo de Documento**

O elemento `doctypes` lista o mapa DITA e os mapeamentos de tópico com suporte.

**Mapear regras de parágrafo do tipo de documento**

O elemento `mapDoctypeParaRule` é obrigatório. Os atributos deste elemento não devem ser editados porque o elemento raiz do XML de origem é sempre mapeado para o elemento raiz `map` do mapa DITA.

**Regra de parágrafo de tipo de documento**

O elemento `doctypeParaRule` é obrigatório. Isso fornece ao processo de conversão uma maneira de identificar o início de um novo tópico. Normalmente, o atributo `@style` é usado sozinho com o atributo `@local` definido como 0. Entretanto, se sempre houver substituições de formatação local no estilo escolhido, será necessário adicionar uma regra para cada estilo mais suas substituições locais. É simples reconhecer isso no arquivo de mapeamento gerado, onde seria possível encontrar isso ou algo semelhante:

```XML
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

No exemplo acima, há dois elementos `paraRule` para `@style` = &quot;Heading1&quot;. Basta criar um elemento `doctypeParaRule` equivalente com o atributo `@mapToDoctype` definido conforme necessário.

Os atributos usados em `doctypeParaRule` são explicados abaixo:

- `@style`: O nome de um estilo no documento de InDesign de origem.
- `@local`: Consulte [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapToDoctype`: o nome de um tipo de tópico DITA de uma lista enumerada de todos os `doctypes` válidos.

**Regras de quebra automática de elemento**

As regras de quebra de elementos definem as maneiras de quebrar ou mover elementos no documento recebido para um elemento predefinido de acordo com um conjunto de valores de atributo.

***`wrap`elemento***

Esse é um elemento opcional. O elemento `wrap` lista os elementos que serão ajustados ou movidos. A quebra normalmente é usada quando uma série de elementos deve receber um elemento pai comum. Por exemplo, vários elementos `li` sendo envolvidos em um elemento `ol`. Além disso, `wrap` pode ser usado para mover elementos, como títulos para figuras e tabelas.

Os atributos usados em `wrap` são explicados abaixo:

- `@element`: um sinal de mais depois de um nome de elemento mostra que todos os elementos adjacentes com o mesmo nome serão encapsulados no elemento nomeado no atributo `@wrapper`.
- `@wrapper`: O nome do elemento de encapsulamento.
- `@context`: Fornece uma maneira de refinar ainda mais como um determinado elemento é encapsulado. O exemplo a seguir mostra uma maneira de mapear uma série de elementos `li` em uma lista ordenada `ol` ou em uma lista não ordenada `ul` de acordo com o valor `@context` \(o contexto é definido no elemento `paraRule`\):

  ```XML
  <wrap elements="li+" context="number" wrapper="ol">
     <attributeRules createID="true"/>
  </wrap>
  <wrap elements="li+" context="bullet" wrapper="ul">
     <attributeRules createID="true"/>
  </wrap>
  ```


O exemplo a seguir mostra como criar um elemento `fig` a partir de um elemento `title` e um elemento `image`:

- `@elements`: os elementos listados e separados por vírgula serão encapsulados no elemento nomeado no atributo `@wrapper`. Devido à prática comum de incluir títulos de figura abaixo da imagem, o título será o elemento `title` imediatamente após `image`.

  A seguinte regra de quebra de linha:

  ```XML
  <wrap elements="title, image" context="FigTitle" wrapper="fig">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Converte o seguinte XML intermediário:

  ```XML
  <image href="Links/myImage.png" scale="59">
     <title>IDML2DITA workflow</title>
  ```

  Na seguinte estrutura de figura DITA válida:

  ```XML
  <fig id="id397504">
     <title>IDML2DITA workflow</title>
     <image href="Links/myImage.png" scale="59">
  </fig>
  ```

- `@wrapper`: O nome do elemento de encapsulamento.
- `@context`: Fornece uma maneira de refinar ainda mais como um determinado elemento é encapsulado \(o contexto é definido no elemento `paraRule`\).

O exemplo a seguir mostra como mover um `title` para um `table`:

- `@elements`: O elemento `title`, que está localizado imediatamente antes ou depois de um `table`, será encapsulado no elemento nomeado no atributo `@wrapper`. Um predicado XPath-style pode identificar a posição do elemento title como `[before]` ou `[after]`.

  Exemplo: a seguinte regra de quebra:

  ```XML
  <wrap elements="title[before]" context="TableTitle" wrapper="table">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Converte o seguinte XML intermediário:

  ```XML
  <title>IDML2DITA workflow</title>
  <table id="id289742" outputclass="BasicTable">
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

  Nesta estrutura de figura DITA válida:

  ```XML
  <table id="id289742" outputclass="BasicTable">
     <title>IDML2DITA workflow</title>
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

- `@wrapper`: O nome do elemento de encapsulamento.

- `@context`: Fornece uma maneira de refinar ainda mais como um determinado elemento é encapsulado \(o contexto é definido no elemento `paraRule`\).


**Regras de estilo de parágrafo**

Os elementos `<paragraphStyleRule>` estão descritos abaixo:

***`paraRule`elemento***

O elemento `paraRule` é obrigatório. Especifica as regras de mapeamento para todos os Estilos de parágrafo. Em um documento de InDesign, todo o texto está contido em uma subestrutura de Estilos de parágrafo, até mesmo parágrafos sem nenhum estilo são nomeados como `[No paragraph style]`. Os colchetes indicam um nome de estilo de InDesign interno.

>[!NOTE]
>
> Os colchetes indicam um nome de estilo de InDesign incorporado.

Os atributos usados em `paraRule` são explicados abaixo:

- `@style`: O nome de um estilo no documento de InDesign de origem.
- `@local`: Consulte [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: o nome de um elemento de destino DITA.

- `@context`: Este atributo é usado para vincular a uma regra específica de **wrap** quando mais de uma opção de wrapper estiver disponível. Exemplo: o elemento `li` pode estar encapsulado em um elemento `ol` ou `ul`. Para identificar os diferentes tipos de lista, você pode usar um nome de estilo específico ou o atributo `@local` que pode mostrar o seguinte:
   - `local="p[-|-|-|-|-|b|-|-]"` Onde &#39;`b`&#39; no campo 6 indica um item de lista com marcadores. Neste caso, defina `@context` como &#39;`bullet`&#39;.
   - `local="p[-|-|-|-|-|n|-|-]"` Onde &#39;`n`&#39; no campo 6 indica um item de lista numerado. Neste caso, defina `@context` como &#39;`number`&#39;.

- `@commentOut`: este atributo habilita o encapsulamento do elemento de destino em comentários XML para que as informações não sejam perdidas, mas possam ser manipuladas manualmente pelo usuário. Isso é útil se o conteúdo original não puder ser forçado a se adequar às regras de estrutura DITA.

- `@refactor`: Este atributo opcional tem uma opção de dois valores:

- `unwrap`: o elemento correspondente é removido enquanto mantém seu conteúdo.

- `drop`: o elemento correspondente e todo o seu conteúdo são removidos.


**Regras de estilo de caractere**

Os elementos `charRule` estão descritos abaixo:

>[!NOTE]
>
> Não haverá mapeamento para o estilo de caractere interno `[No character style]` quando `local="0"`, pois eles são removidos durante o pré-processamento.

***`charRule`elemento***

Esse é um elemento opcional.

Essas são as regras de mapeamento para todos os Estilos de Caractere. Em um documento de InDesign, todo o texto está contido em elementos secundários de Estilos de caractere.

Os atributos usados em `charRule` são explicados abaixo:

- `@style`: O nome de um estilo no documento de InDesign de origem.
- `@local`: Consulte [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: o nome de um elemento de destino DITA.
- `@refactor`: Este atributo opcional tem uma opção de dois valores:
   - `unwrap`: o elemento correspondente é removido enquanto mantém seu conteúdo.

   - `drop`: o elemento correspondente e todo o seu conteúdo são removidos.


**Regras de atributo**

Esse elemento pode ser filho dos seguintes contextos de elemento:

- `mapDoctypeParaRule`
- `mapDoctypeElemRule`
- `doctypeParaRule`
- `doctypeElemRule`
- `paraRule`
- `charRule`
- `elementRule`

A finalidade das regras de atributo é gerenciar os atributos dos elementos correspondentes.

Dependendo do contexto, os seguintes atributos estão disponíveis para o elemento `attributeRules`:

- `@createID`: gera um identificador exclusivo para os elementos correspondentes. Valores permitidos `true` ou `false`. Disponível em todos os contextos.
- `@copyAll`: copia todos os atributos do conteúdo XML de origem somente para arquivos de origem estruturados. Os valores permitidos são `true` ou `false`. Disponível para os contextos `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` e `elementRule`.


Os atributos usados em `attributeRules` são explicados abaixo:

>[!NOTE]
>
> Esse elemento pode conter vários elementos secundários.

- `addNew`: Adiciona um novo atributo ao elemento correspondente. Disponível para todos os contextos. Ela tem dois atributos:
   - `@name`: deve ser um nome XML válido, de preferência, válido para o contexto DITA.
   - `@value`: pode ser texto literal ou uma expressão XPath simples.
- `copyAtt`: copia um único atributo para o destino enquanto, opcionalmente, o renomeia no processo. O valor não é alterado. Disponível para os contextos `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` e `elementRule`. Quando este elemento está presente, presume-se que o valor `@copyAllAtts` seja `false`. Ela tem dois atributos:
   - `@name`: deve ser o nome de um atributo presente no elemento XML de origem.
   - `@mapTo`: deve ser um nome XML válido, de preferência, válido para o contexto DITA.

**Códigos de formatação locais**

Em qualquer documento do InDesign, estilos de parágrafo e de caractere podem conter centenas de substituições de formatação diferentes. A maioria dessas propriedades não fornece nenhuma função útil no processo de conversão. No entanto, identificamos um conjunto principal de recursos de formatação que afetam a semântica do documento e precisam influenciar o processo de conversão.

Os atributos `@local` são apresentados como um formato delimitado especial, onde oito campos são fornecidos junto com um prefixo para mostrar o tipo de substituição de formatação. Os campos de códigos de formatação estão listados abaixo:

- Prefixo **p** para substituição local de estilo para ou **c** para substituição local de estilo de caractere.
- **Estilo da fonte**, que é o nome da família e as propriedades, como &#39;***Itálico condensado em Negrito***&#39;.
- **Tamanho da fonte** em pontos.
- **Posição do caractere** para sobrescrito ou subscrito.
- **Em** para sublinhado.
- **Tachado** para tachado.
- **Código de lista** para identificar o tipo de lista como com marcadores ou Numerado - nem sempre usado pelo InDesign.
- **Código do marcador** lista todos os tipos de marcadores definidos no documento.
- **Código numérico** lista todos os estilos de numeração definidos no documento.

O uso cuidadoso desse recurso permite que a formatação local perdida de outra forma ajude a melhorar a qualidade de uma transferência do conteúdo estilizado para o DITA. Este exemplo pode ser resolvido como um texto em itálico de 16 pt em uma lista com marcadores: `p[Italic|16|-|-|-|b|-|-]`.

**Mapeamento da estrutura**

O arquivo de mapeamento de estrutura é semelhante ao arquivo de Mapeamento de estilo, com uma estrutura simples que lista todos os elementos de origem e tipos de atributos relevantes. Dois atributos, `@map_date` e `@map_version`, são fornecidos para gravar a versão do arquivo de mapeamento a ser usado.

**Tipo de Documento**

O elemento `doctypes` lista o mapa DITA e os mapeamentos de tópico com suporte.

**Mapear regras de elemento de tipo de documento**

O elemento `mapDoctypeElemRule` é obrigatório. Os atributos deste elemento não devem ser editados porque o elemento raiz do XML de origem é sempre mapeado para o elemento raiz `map` do mapa DITA.

**Regras de quebra automática de elemento**

**`elementRules`elemento** Lista todos os elementos.

**`elementRule`elemento** O elemento `elementRule` é obrigatório. Estas são as regras de mapeamento para todos os elementos de origem. Embora um documento de InDesign contenha elementos de estilo não estruturados, eles são ignorados para conteúdo estruturado, a menos que o processamento do &#39;***modo híbrido***&#39; esteja habilitado.

Os atributos usados em `elementRule` são explicados abaixo:

- `@elementName`: O nome de um elemento no documento de InDesign de origem.

- `@local`: Consulte [\#id194CG0V005Z](#id194CG0V005Z). \(Útil somente para documentos híbridos\).

- `@mapTo`: o nome de um elemento de destino DITA.

- `@refactor`: Este atributo opcional tem uma opção de dois valores:

   - `unwrap`: o elemento correspondente é removido enquanto mantém seu conteúdo.

   - `drop`: o elemento correspondente e todo o seu conteúdo são removidos.

- `@context`: este atributo é usado para vincular a uma regra de wrap específica quando mais de uma opção de wrap está disponível. Exemplo: o elemento `li` pode estar encapsulado em um elemento `ol` ou `ul`.

- `@commentOut`: este atributo habilita o encapsulamento do elemento de destino em comentários XML para que as informações não sejam perdidas, mas possam ser manipuladas manualmente pelo usuário. Isso é útil se o conteúdo original não puder ser forçado a se adequar às regras de estrutura DITA.


## Solução de problemas do AEM Guides

Depois de instalar e configurar o AEM Guides, você pode solucionar os problemas.

## Validar referências

Você pode executar os scripts fornecidos para validar as referências. Esses scripts podem ajudar a identificar as referências corrompidas e, em seguida, corrigir ou corrigir essas referências.

- `/bin/fmdita/validatebtree?operation=validate` - relata as referências de conteúdo corrompido, mas não as corrige.
- `/bin/fmdita/validatebtree?operation=patch`- lista as referências de conteúdo corrompidas e os patches ou as corrige.

**Validar script**

Execute as seguintes etapas para verificar as referências usando o script de validação disponível no pacote do produto:

1. Execute o script de validação \[`/bin/fmdita/validatebtree?operation=validate`\] para verificar se há novas referências corrompidas.
1. Caso o script de validação reporte algum erro, você poderá corrigi-lo usando o script de correção.
1. Registre os detalhes fornecidos a seguir e, se necessário, compartilhe-os com a equipe de sucesso do cliente:
1. 
   - Logs impressos pelo script de validação
- Pacote de &quot;`/content/fmdita/references`&quot;
- Quaisquer outros detalhes necessários, dependendo do cenário relatado

**Script de correção**

Execute as seguintes etapas para corrigir referências quebradas, usando o script de patch disponível no pacote do produto:

1. Execute o script de patch `[/bin/fmdita/validatebtree?operation=patch]` para corrigir as referências corrompidas. A execução do script leva alguns minutos e imprime os registros conforme avança. Quando a execução for concluída, ele imprimirá &quot;`Done`&quot; no final.

   **Observação:* é recomendável copiar e salvar os logs para fins de referência.

1. Quando o script de patch for executado com sucesso, você poderá fazer as seguintes verificações:
1. 
   - Verificar se um novo nó &quot;`references_backup_<timestamp>"`&quot; foi criado em `/content/fmdita`
- Verifique se as referências foram corrigidas

**Agente**

Você também pode criar um agente de log separado para essa execução de script, de acordo com os detalhes fornecidos abaixo:

- Adicionar um agente de log na classe &quot;`adobe.fmdita.common.BTreeReferenceValidator`&quot;
- Defina como `DEBUG`

O arquivo de log criado registrará todas as informações relacionadas à execução do script e será útil caso o tempo limite da sessão do navegador seja excedido durante o acionamento do script no navegador.
