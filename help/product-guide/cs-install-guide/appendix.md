---
title: Apêndice
description: Saiba como preparar documentos do InDesign para migração
exl-id: 71b09039-b220-45f3-b334-c23f5b09dadc
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '2852'
ht-degree: 0%

---

# Apêndice {#id195AD0L60Y4}

## Solução de problemas de guias do AEM

Depois de instalar e configurar os Guias do AEM, você pode solucionar os problemas.

## Validar referências

Você pode executar os scripts fornecidos para validar as referências. Esses scripts podem ajudar a identificar as referências corrompidas e, em seguida, corrigir ou corrigir essas referências.

- `/bin/fmdita/validatebtree?operation=validate` - relata todas as referências de conteúdo corrompidas, mas não as corrige.

- `/bin/fmdita/validatebtree?operation=patch` - lista as referências de conteúdo corrompidas e os patches ou as correções.


**Validar script**

Execute as seguintes etapas para verificar as referências usando o script de validação disponível no pacote do produto:

1. Execute o script de validação \[`/bin/fmdita/validatebtree?operation=validate`\] para verificar se há novas referências quebradas.
1. Caso o script de validação reporte algum erro, você poderá corrigi-lo usando o script de correção.
1. Registre os detalhes fornecidos a seguir e, se necessário, compartilhe-os com a equipe de sucesso do cliente:
1. 
   - Logs impressos pelo script de validação
- Pacote de &quot;`/content/fmdita/references`&quot;
- Quaisquer outros detalhes necessários, dependendo do cenário relatado

**Script de correção**

Execute as seguintes etapas para corrigir referências quebradas, usando o script de patch disponível no pacote do produto:

1. Execute o script de patch `[/bin/fmdita/validatebtree?operation=patch]` para corrigir as referências quebradas. A execução do script leva alguns minutos e imprime os registros conforme avança. Quando a execução for concluída, ele imprimirá &quot;`Done`&quot; no final.

>[!NOTE]
>
> É recomendável copiar e salvar os logs para fins de referência.

1. Quando o script de patch for executado com sucesso, você poderá fazer as seguintes verificações:
1. 
   - Verificar um novo nó &quot;`references_backup_<timestamp>"` foi criado em `/content/fmdita`
- Verifique se as referências foram corrigidas

**Logger**

Você também pode criar um agente de log separado para essa execução de script, de acordo com os detalhes fornecidos abaixo:

- Adicionar um agente de log na classe &quot;`adobe.fmdita.common.BTreeReferenceValidator`&quot;
- Defina-o como `DEBUG`

O arquivo de log criado registrará todas as informações relacionadas à execução do script e será útil caso o tempo limite da sessão do navegador seja excedido durante o acionamento do script no navegador.

## Preparar arquivos de InDesign para conversão {#id195DBF0045Z}

O InDesign fornece aos autores um conjunto avançado de recursos para criar documentos atraentes e complexos. Geralmente, isso significa que as várias partes de um documento são colocadas na página visualmente, mas sem nenhuma tentativa de fornecer nenhum fluxo entre esses quadros de texto. Quando a variável &#39;*ordem de leitura*&#39; dos quadros de texto não estiver definido, o arquivo IDML conterá histórias que podem não seguir qualquer ordem significativa. O resultado final será um ou mais tópicos DITA com parágrafos, tabelas e gráficos em uma ordem aleatória.

Embora seja possível editar o conteúdo DITA em uma ordem sensata em um editor DITA, é muito mais fácil corrigir o arquivo InDesign antes de criar o arquivo IDML. Isso pode ser feito sem alterar a aparência do documento de origem. Também tem a vantagem de tornar o documento de origem acessível, definindo corretamente a ordem de leitura.

***Encadeamento de quadros de texto***

O InDesign usa o termo *&#39;encadeamento&#39;* para o processo de vinculação de um quadro a outro. Para obter mais detalhes sobre encadeamento de quadros de texto, consulte *[Texto da discussão](https://helpx.adobe.com/in/indesign/using/threading-text.html)* tópico na documentação do InDesign.

***Sobreposição de quadros***

Alguns documentos do InDesign usam quadros sobrepostos não encadeados por motivos de layout. Pode ser muito difícil mesclar esse conteúdo na thread principal. A melhor opção pode ser editar o resultado no ambiente DITA.

***Histórias de InDesign***

Cada fluxo de conteúdo encadeado em um documento do InDesign é chamado de &#39;*história*&#39;. Para obter melhores resultados, é recomendável manter o número de histórias limitado. No entanto, há algumas partes do documento que podem não ser necessárias na saída DITA. Por exemplo, rodapés de página raramente são necessários, mas podem aparecer no meio de um tópico se não forem tratados com cuidado.

A maneira mais fácil de excluir um texto que não é necessário no documento é fornecer um *Tag de parágrafo* que só é usado para o conteúdo indesejado. Por exemplo, em vez de reutilizar um *\[Parágrafo básico\]* para o rodapé, crie um *Rodapé* tag. Em seguida, no arquivo MapStyle, basta definir o *Rodapé* parágrafos a serem soltos desta forma:

```
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Mapeamento para tipos de documentos DITA***

É essencial que o documento de origem tenha pelo menos um Estilo de parágrafo ou Elemento que possa marcar o início de um tópico. É comum documentos usarem *Cabeçalho1* como o nome dos títulos de nível superior no documento. Em seguida, você pode criar um mapeamento desse estilo para um tipo de documento DITA específico. Se o documento estiver bem organizado e o uso de *Cabeçalho1* é constante em todo o, então você terá bons resultados.

***Vários tipos de documento DITA***

Se alguma das *Cabeçalho1* Os parágrafos precisam ser convertidos em diferentes tipos de documento DITA e, em seguida, duplicar o estilo de parágrafo no InDesign. Dê a esses estilos um nome fácil de reconhecer, como *Heading1\_genTask* ou *Heading1\_troubleshooting* conforme adequado. Em seguida, configure o arquivo mapStyle como mostrado abaixo:

```
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

***Formatação de tabela***

A conversão das regras de formatação da tabela do InDesign para a formatação de tabela equivalente em DITA é um processo complexo. Isso se deve aos recursos de formatação avançada disponíveis nos arquivos de origem em comparação às opções básicas fornecidas pelo modelo de tabela Oasis \(CALS\) usado no DITA. O alinhamento de texto vertical e horizontal é fornecido e fornece resultados semelhantes, embora o Texto justificado seja sempre justificado de acordo com a direção do texto, enquanto o InDesign permite Justificado à esquerda e Justificado à direita.

O manuseio de separadores de coluna e linha pelo InDesign é novamente muito mais capaz do que as opções básicas do modelo de tabela do Oasis. O InDesign fornece quatro bordas de célula: Tipo de borda \(sólida ou padrão\), Peso da borda, Cor da borda, Tonalidade da borda, Cor de espaço da borda e Tonalidade de espaço da borda. Todos eles devem ser mapeados para as bordas à direita e abaixo de cada célula \(elemento de entrada\) onde as únicas opções são 0 ou 1 - ocultar a borda ou mostrar a borda.

A decisão fronteiriça em InDesign pode ser aplicada nos seguintes níveis:

- Estilos de Tabela
- Estilos de Célula
- Substituições locais em cada célula

O processo de conversão do InDesign para o DITA aplica a decisão de fronteira da seguinte forma:

- Os estilos de tabela são mapeados para a variável `colspec/@colsep` atributo para regras verticais. As regras horizontais são mapeadas para o `row/@rowsep` atributo. Em ambos os casos, se a borda não estiver definida, o atributo não será criado.
- Os estilos de célula são mapeados para o `entry/@colsep` e `entry/@rowsep` atributos. Esses valores substituirão qualquer regra de borda derivada do Estilo de tabela.
- As substituições locais aplicam a formatação diretamente à célula e substituem Estilos de Tabela e Estilos de Célula.

***Padrões alternados***

Os Estilos de Tabela de InDesign permitem que as regras de coluna e célula sigam um padrão alternado. Embora esse recurso seja compatível com a conversão, os resultados só serão óbvios quando um grupo de padrão for mapeado para mostrar a regra \(1\) e o outro grupo de padrão for mapeado para ocultar a regra \(0\).

## Preparar o arquivo de mapeamento para migração do InDesign para o DITA {#id194AF0003HT}

A conversão DITA correta requer um arquivo de mapeamento que corresponda ao conteúdo do documento de origem. Para documentos de InDesign não estruturados, isso significa que todos os Estilos de parágrafo e de caractere disponíveis precisam ser mapeados. Para documentos de InDesign estruturados XML, todos os elementos em seu DTD associado devem ser mapeados.

Os arquivos de mapeamento para documentos de InDesign não estruturados e estruturados são diferentes. Isso se deve aos requisitos de processamento mais complexos para converter conteúdo original não estruturado em DITA.

Uma amostra do arquivo de mapeamento é fornecida abaixo:

```
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

No `styleMap` elemento, você pode especificar dois atributos opcionais - `@map_date` e `@map_version` para gravar a versão do arquivo de mapeamento.

**Tipo de documento**

A variável `doctypes` element lista o mapa DITA e os mapeamentos de tópico compatíveis.

**Mapear regras de parágrafo do tipo de documento**

A variável `mapDoctypeParaRule` elemento é obrigatório. Os atributos deste elemento não devem ser editados porque o elemento raiz do XML de origem é sempre mapeado para a raiz do mapa DITA `map` elemento.

**Regra de parágrafo de tipo de documento**

A variável `doctypeParaRule` elemento é obrigatório. Isso fornece ao processo de conversão uma maneira de identificar o início de um novo tópico. Normalmente, a variável `@style` atributo é usado sozinho com o `@local` atributo definido como 0. Entretanto, se sempre houver substituições de formatação local no estilo escolhido, será necessário adicionar uma regra para cada estilo mais suas substituições locais. É simples reconhecer isso no arquivo de mapeamento gerado, onde seria possível encontrar isso ou algo semelhante:

```
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

No exemplo acima, há dois `paraRule` elementos para `@style` = &quot;Heading1&quot;. Basta criar um equivalente `doctypeParaRule` elementos com o `@mapToDoctype` atributo definido conforme necessário.

Os atributos usados na variável `doctypeParaRule` são explicados a seguir:

- `@style`: O nome de um estilo no documento de InDesign de origem.
- `@local`: Consulte [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapToDoctype`: o nome de um tipo de tópico DITA de uma lista enumerada de todos os `doctypes`.

**Regras de quebra automática de elemento**

As regras de quebra de elementos definem as maneiras de quebrar ou mover elementos no documento recebido para um elemento predefinido de acordo com um conjunto de valores de atributo.

***`wrap`element***

Esse é um elemento opcional. A variável `wrap` element lista os elementos que serão quebrados ou movidos. A quebra normalmente é usada quando uma série de elementos deve receber um elemento pai comum. Por exemplo, vários `li` elementos sendo envolvidos em um `ol` elemento. Além disso, `wrap` pode ser usado para mover elementos, como títulos para figuras e tabelas.

Os atributos usados na variável `wrap` são explicados a seguir:

- `@element`: um sinal de mais depois de um nome de elemento mostra que todos os elementos adjacentes com o mesmo nome serão encapsulados no elemento chamado no `@wrapper`atributo.
- `@wrapper`: o nome do elemento de encapsulamento.
- `@context`: fornece uma maneira de refinar ainda mais como um determinado elemento é encapsulado. O exemplo a seguir mostra uma maneira de mapear uma série de `li` elementos em uma lista ordenada `ol` ou uma lista não ordenada `ul` de acordo com a `@context` value \(o contexto é definido na variável `paraRule` element\):

  ```
  <wrap elements="li+" context="number" wrapper="ol">
     <attributeRules createID="true"/>
  </wrap>
  <wrap elements="li+" context="bullet" wrapper="ul">
     <attributeRules createID="true"/>
  </wrap>
  ```


O exemplo a seguir mostra como criar um `fig` elemento de a `title` e uma `image` elemento:

- `@elements`: os elementos listados e separados por vírgula serão encapsulados no elemento chamado no `@wrapper` atributo. Devido à prática comum de incluir títulos de figura abaixo da imagem, o título será o `title` imediatamente após o `image`.

  A seguinte regra de quebra de linha:

  ```
  <wrap elements="title, image" context="FigTitle" wrapper="fig">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Converte o seguinte XML intermediário:

  ```
  <image href="Links/myImage.png" scale="59">
     <title>IDML2DITA workflow</title>
  ```

  Na seguinte estrutura de figura DITA válida:

  ```
  <fig id="id397504">
     <title>IDML2DITA workflow</title>
     <image href="Links/myImage.png" scale="59">
  </fig>
  ```

- `@wrapper`: o nome do elemento de encapsulamento.
- `@context`: fornece uma maneira de refinar ainda mais como um determinado elemento é encapsulado \(o contexto é definido na variável `paraRule` element\).

O exemplo a seguir mostra como mover um `title` em um `table`:

- `@elements`: A variável `title` elemento situado imediatamente antes ou imediatamente depois de um `table` será encapsulado no elemento chamado no `@wrapper` atributo. Um predicado de estilo XPath pode identificar a posição do elemento de título como `[before]` ou `[after]`.

  Exemplo: a seguinte regra de quebra:

  ```
  <wrap elements="title[before]" context="TableTitle" wrapper="table">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Converte o seguinte XML intermediário:

  ```
  <title>IDML2DITA workflow</title>
  <table id="id289742" outputclass="BasicTable">
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

  Nesta estrutura de figura DITA válida:

  ```
  <table id="id289742" outputclass="BasicTable">
     <title>IDML2DITA workflow</title>
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

- `@wrapper`: o nome do elemento de encapsulamento.

- `@context`: fornece uma maneira de refinar ainda mais como um determinado elemento é encapsulado \(o contexto é definido na variável `paraRule` element\).


**Regras de estilo de parágrafo**

A variável `paragraphStyleRule` Os elementos do são descritos abaixo:

** `paraRule` elemento**

A variável `paraRule` elemento é obrigatório. Especifica as regras de mapeamento para todos os Estilos de parágrafo. Em um documento de InDesign, todo o texto está contido na subestrutura de Estilos de parágrafo. Mesmo parágrafos sem nenhum estilo são nomeados `\[No paragraph style\]`. Os colchetes indicam um nome de estilo de InDesign incorporado.

>[!NOTE]
>
> Os colchetes indicam um nome de estilo de InDesign incorporado.

Os atributos usados na variável `paraRule` são explicados a seguir:

- `@style`: O nome de um estilo no documento de InDesign de origem.
- `@local`: Consulte [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: o nome de um elemento de destino DITA.

- `@context`: este atributo é usado para vincular a um **quebra automática** regra quando mais de uma opção de invólucro estiver disponível. Exemplo: a variável `li` o elemento pode ser encapsulado em um `ol`, ou um `ul` elemento. Para identificar os diferentes tipos de lista, você pode usar um nome de estilo específico ou o `@local` atributo que pode mostrar o seguinte:
   - `local="p[-|-|-|-|-|b|-|-]"` Onde o &#39;`b`&quot; no campo 6 indica um item de lista com marcadores. Nesse caso, defina `@context` para &#39;`bullet`&#39;.
   - `local="p[-|-|-|-|-|n|-|-]"` Onde o &#39;`n`&quot; no campo 6 indica um item de lista numerado. Nesse caso, defina `@context` para &#39;`number`&#39;.

- `@commentOut`: esse atributo permite o encapsulamento do elemento de destino em comentários XML para que as informações não sejam perdidas, mas possam ser manipuladas manualmente pelo usuário. Isso é útil se o conteúdo original não puder ser forçado a se adequar às regras de estrutura DITA.

- `@refactor`: este atributo opcional tem uma opção de dois valores:

- `unwrap`: o elemento correspondente é removido enquanto mantém seu conteúdo.

- `drop`: o elemento correspondente e todo o seu conteúdo são removidos.


**Regras de estilo de caractere**

A variável `charRule` Os elementos do são descritos abaixo:

>[!NOTE]
>
> Não haverá mapeamento para o estilo de caractere interno `[No character style]` quando `local="0"`, pois são removidos durante o pré-processamento.

***`charRule`element***

Esse é um elemento opcional.

Essas são as regras de mapeamento para todos os Estilos de Caractere. Em um documento de InDesign, todo o texto está contido em elementos secundários de Estilos de caractere.

Os atributos usados na variável `charRule` são explicados a seguir:

- `@style`: O nome de um estilo no documento de InDesign de origem.
- `@local`: Consulte [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: o nome de um elemento de destino DITA.
- `@refactor`: este atributo opcional tem uma opção de dois valores:
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

Dependendo do contexto, os seguintes atributos estarão disponíveis na `attributeRules` elemento:

- `@createID`: gera um identificador exclusivo para os elementos correspondentes. Valores permitidos `true` ou `false`. Disponível em todos os contextos.
- `@copyAll`: copia todos os atributos do conteúdo XML de origem somente para arquivos de origem estruturados. Os valores permitidos são `true` ou `false`. Disponível para contextos `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` e `elementRule`.


Os atributos usados na variável `attributeRules` são explicados a seguir:

>[!NOTE]
>
> Esse elemento pode conter vários elementos secundários.

- `addNew`: adiciona um novo atributo ao elemento correspondente. Disponível para todos os contextos. Ela tem dois atributos:
   - `@name`: deve ser um nome XML válido, de preferência, para o contexto DITA.
   - `@value`: pode ser um texto literal ou uma expressão XPath simples.
- `copyAtt`: copia um único atributo para o target, enquanto, opcionalmente, o renomeia no processo. O valor não é alterado. Disponível para contextos `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` e `elementRule`. Quando esse elemento estiver presente, a variável `@copyAllAtts` presume-se que o valor `false`. Ela tem dois atributos:
   - `@name`: deve ser o nome de um atributo presente no elemento XML de origem.
   - `@mapTo`: deve ser um nome XML válido, de preferência, para o contexto DITA.

**Códigos de formatação local**

Em qualquer documento do InDesign, estilos de parágrafo e de caractere podem conter centenas de substituições de formatação diferentes. A maioria dessas propriedades não fornece nenhuma função útil no processo de conversão. No entanto, identificamos um conjunto principal de recursos de formatação que afetam a semântica do documento e precisam influenciar o processo de conversão.

A variável `@local` os atributos são apresentados como um formato delimitado especial, onde oito campos são fornecidos junto com um prefixo para mostrar o tipo de substituição de formatação. Os campos de códigos de formatação estão listados abaixo:

- Prefixo **p** para substituição local do estilo para ou **c** para substituição local de estilo de caractere.
- **Estilo da fonte** que é o nome da família e as propriedades, como &#39;***Itálico condensado em Negrito***&#39;.
- **Tamanho da fonte** em pontos.
- **Posição do caractere** para sobrescrito ou subscrito.
- **Em** para sublinhado.
- **Tachado** para tachado.
- **Código da lista** para identificar o tipo de lista como com marcadores ou Numerada, nem sempre usado pelo InDesign.
- **Código de marcador** lista todos os tipos de marcadores definidos no documento.
- **Código numérico** lista todos os estilos de numeração definidos no documento.

O uso cuidadoso desse recurso permite que a formatação local perdida de outra forma ajude a melhorar a qualidade de uma transferência do conteúdo estilizado para o DITA. Este exemplo pode ser resolvido como um texto em itálico de 16 pt em uma lista com marcadores: `p[Italic|16|-|-|-|b|-|-]`.

**Mapeamento de estrutura**

O arquivo de mapeamento de estrutura é semelhante ao arquivo de Mapeamento de estilo, com uma estrutura simples que lista todos os elementos de origem e tipos de atributos relevantes. Dois atributos, `@map_date` e `@map_version` são fornecidos para registrar a versão do arquivo de mapeamento a ser usado.

**Tipo de documento**

A variável `doctypes` element lista o mapa DITA e os mapeamentos de tópico compatíveis.

**Mapear regras de elemento de tipo de documento**

A variável `mapDoctypeElemRule` elemento é obrigatório. Os atributos deste elemento não devem ser editados porque o elemento raiz do XML de origem é sempre mapeado para a raiz do mapa DITA `map` elemento.

**Regras de quebra automática de elemento**

Consulte [\#id194CG600NY4](#id194CG600NY4).

**`elementRules`element**

Isso lista todas as [\#id194CGC00SHS](#id194CGC00SHS)elementos.

**`elementRule`element**

A variável `elementRule` elemento é obrigatório. Estas são as regras de mapeamento para todos os elementos de origem. Embora um documento do InDesign contenha elementos de estilo não estruturados, eles são ignorados para conteúdo estruturado, a menos que a variável &#39;***modo híbrido*** O processamento &#39; está ativado.

Os atributos usados na variável `elementRule` são explicados a seguir:

- `@elementName`: O nome de um elemento no documento de InDesign de origem.

- `@local`: Consulte [\#id194CG0V005Z](#id194CG0V005Z). \(Útil somente para documentos híbridos\).

- `@mapTo`: o nome de um elemento de destino DITA.

- `@refactor`: este atributo opcional tem uma opção de dois valores:

   - `unwrap`: o elemento correspondente é removido enquanto mantém seu conteúdo.

   - `drop`: o elemento correspondente e todo o seu conteúdo são removidos.

- `@context`: este atributo é usado para se vincular a uma regra de wrap específica quando mais de uma opção de wrap está disponível. Exemplo: a variável `li` o elemento pode ser encapsulado em um `ol`, ou um `ul` elemento.

- `@commentOut`: esse atributo permite o encapsulamento do elemento de destino em comentários XML para que as informações não sejam perdidas, mas possam ser manipuladas manualmente pelo usuário. Isso é útil se o conteúdo original não puder ser forçado a se adequar às regras de estrutura DITA.
