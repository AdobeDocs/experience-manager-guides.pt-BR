---
title: Personalizar o mapeamento de elementos dita com componentes do AEM
description: Saiba como personalizar o mapeamento de elementos de lista com componentes do AEM
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '1268'
ht-degree: 1%

---


# Personalizar o mapeamento de elemento DITA com componentes do AEM {#id1679J600HEL}

Os elementos DITA no AEM Guides são mapeados para os componentes correspondentes do AEM. O AEM Guides usa esse mapeamento em fluxos de trabalho, como publicação e revisão, para converter o elemento DITA em um componente AEM correspondente. O mapeamento é definido no arquivo `elementmapping.xml`, que pode ser acessado usando o gerenciador de pacotes para instalação do Cloud Service e a partir da URL: `/libs/fmdita/config/elementmapping.xml` no modo CRXDE Lite para instalação no local.

>[!NOTE]
>
> Não faça nenhuma personalização nos arquivos de configuração padrão disponíveis no nó ``libs``. Você deve criar uma sobreposição do nó ``libs`` no nó ``apps`` e atualizar os arquivos necessários somente no nó ``apps``.

Você pode usar os mapeamentos predefinidos de elementos DITA ou mapear elementos DITA para seus componentes personalizados do AEM. Para usar os componentes personalizados do AEM, você precisa entender a estrutura do arquivo `elementmapping.xml`.

## estrutura elementmapping.xml

Uma visão geral de alto nível da estrutura `elementmapping.xml` é explicada abaixo:

1. Cada elemento DITA é pesquisado primeiro por um mapeamento de componente correspondente com base no nome do elemento. Por exemplo:

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   No exemplo acima, todos os elementos DITA `substeps` são renderizados usando o componente `dita/components/ditaolist`.

1. Se um elemento DITA não encontrar uma correspondência com base no nome, uma correspondência com base no `class` será feita. Por exemplo:

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   No exemplo acima, se não houver mapeamento definido para o elemento `task`, o elemento `task` será mapeado para o componente acima porque `task` é herdado do componente `topic`.

1. Quando um elemento tem um mapeamento de componente correspondente, o processamento adicional de seus elementos filho é determinado por `type`. Por exemplo:

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` assume os seguintes valores:

   - COMPOSITE: o mapeamento de elemento para componente *também continua para elementos filho*.

   - STANDALONE: os elementos filhos do elemento atual *não estão mais mapeados*.

   No exemplo acima, se o elemento `<title>` tiver qualquer elemento filho, ele não será mapeado para nenhum outro componente. O componente do elemento `<title>` é responsável por renderizar todos os elementos filho dentro do elemento `<title>`.

1. Se houver vários componentes mapeados para um único elemento DITA, a melhor correspondência para o elemento será selecionada. Para selecionar o componente de melhor correspondência, a especialização estrutural e de domínio de elementos DITA é considerada.

   Se houver elementos DITA com especialização de domínio e um componente for mapeado para especialização de domínio, esse componente receberá alta prioridade.

   Da mesma forma, se houver elementos DITA com especialização estrutural e um componente for mapeado para especialização estrutural, esse componente receberá alta prioridade.

1. Você pode usar `<attributemap>` no mapeamento de elementos para mapear valores de atributos às propriedades de nós correspondentes.
1. `textprop` pode ser usado para serializar o conteúdo de texto de um elemento DITA para uma propriedade de nó. Além disso, ele pode ser usado várias vezes em uma tag element para serializar o conteúdo do texto em vários locais na hierarquia publicada. Você também pode personalizar a localização e o nome da propriedade do público-alvo. Por exemplo:

   ```XML
   <ditaelement>
      <name>title</name>
      <componentpath>foundation/components/title</componentpath>
      <type>STANDALONE</type>
      <target>para</target>
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   O mapeamento de elemento acima especifica que o conteúdo do texto do elemento `<title>` será salvo como valor de uma propriedade chamada `jcr:title` no nó de saída.

1. `xmlprop` pode ser usado para serializar o XML inteiro de um determinado elemento para uma propriedade de nó. O componente pode ler essa propriedade do nó e fazer renderização personalizada. Por exemplo:

   ```XML
   <ditaelement>
       <name>svg-container</name>
      <class>+ topic/foreign svg-d/svg-container</class>
       <componentpath>fmdita/components/dita/svg</componentpath>
       <type>STANDALONE</type>
       <target>para</target>
      <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   O mapeamento de elemento acima especifica que toda a marcação XML do elemento `<svg-container>` será salva como valor de uma propriedade chamada `data` no nó de saída.

1. Há um mapeamento de atributo especial para lidar com a resolução de caminho no processo de geração de saída. Por exemplo:

   ```XML
   <attributemap>
      <attribute from="href" to="fileReference" ispath="true" rel="source" />
      <attribute from="height" to="height" />
       <attribute from="width" to="width" />
   </attributemap>
   ```

   Para o `attributemap` acima, o atributo `href` no elemento DITA será mapeado para uma propriedade de nó denominada `fileReference`. Agora, como `ispath` está definido como `true`, o processo de geração de saída resolve esse caminho e o define na propriedade do nó `fileReference`.

   A forma como essa resolução acontece é determinada com base no valor do atributo `rel` no mapeamento de atributos.

   - Se `rel=source`, então o valor de `href` é resolvido em relação ao arquivo de origem DITA que está sendo processado no momento. O valor de `href` é resolvido e colocado no valor da propriedade `fileReference`.

   - Se `rel=target`, então o valor de `href` é resolvido em relação ao local de publicação raiz. O valor de `href` é resolvido e colocado no valor da propriedade `fileReference`.

   Se não quiser que ocorra pré-processamento ou resolução nos atributos de caminho, não será necessário especificar o atributo `ispath`. O valor é copiado como está e o componente pode fazer a resolução necessária.


## Esquema de elemento DITA

Veja a seguir um exemplo do esquema do elemento DITA no arquivo `elementmapping.xml`:

```XML
<ditaelement>        
    <name>element_name</name>    
    <class>element_class</class>    
    <componentpath>fmdita/components/dita/component_name</componentpath>    
    <type>COMPOSITE|STANDALONE</type>     
    <attributeprop>propname_a</attributeprop>      
    <textprop>propname_t</textprop>    
    <xmlprop>propname_x</xmlprop>     
    <xpath>xpath expression string</xpath>     
    <target>head|para</target>     
    <wrapelement>div</wrapelement>     
    <wrapclass>class_name</wrapclass>     
    <attributemap>         
        <attribute from="attrname"         to="propname"         ispath="true|false"         rel="source|target" />    
    </attributemap>    
    <skip>true|false</skip> 
</ditaelement>
```

A tabela a seguir descreve os elementos do esquema de elemento DITA:

| Elemento | Descrição |
|-------|-----------|
| `<ditaelement>` | O nó de nível superior de cada elemento de mapeamento. |
| `<class>` | O atributo de classe do elemento DITA de destino para o qual você está gravando o componente.<br> Por exemplo, o atributo de classe para o tópico DITA é: <br> `- topic/topic` |
| `<componentpath>` | O caminho CRXDE do componente do AEM mapeado. |
| `<type>` | Valores possíveis:<br> -   **COMPOSITE**: processar elementos filho também <br> -   **INDEPENDENTE**: ignora o processamento de elementos filho |
| `<attributeprop>` | Usado para mapear atributos e valores DITA serializados para nós do AEM como propriedade. Por exemplo, se você tiver o elemento `<note type="Caution">` e o componente mapeado para esse elemento tiver `<attributeprop>attr_t</ attributeprop>`, o atributo e o valor do nó serão serializados para a propriedade `attr_t` do nó AEM correspondente \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Salvar a saída `getTextContent()` na propriedade definida por `propname_t.` <br> **Observação:** esta é uma propriedade otimizada. |
| `<xmlprop>propname_x </xmlprop>` | Salvar XML serializado deste nó na propriedade definida por `propname_x.<br> `**Observação:** Esta é uma propriedade otimizada. |
| `<xpath>` | Se o elemento XPath for fornecido no mapeamento de elementos, juntamente com o nome e a classe do elemento, a condição XPath também deverá ser atendida para que o mapeamento do componente seja usado. |
| `<target>` | Coloque o elemento DITA no repositório crx no local especificado.<br> Valores possíveis: <br> - **cabeçalho**: Sob o nó de cabeçalho <br> - **texto**: Sob o nó de parágrafo |
| `<wrapelement>` | O elemento HTML no qual envolver o conteúdo. |
| `<wrapclass>` | O valor do elemento para a propriedade `wrapclass.` |
| `<attributemap>` | Nó de contêiner contendo um ou mais nós `<attribute>`. |
| `<attribute from="attrname" to="propname" ispath="true\|false" rel="source\|target" />` | Mapeia os atributos DITA para propriedades do AEM: <br> -   **`from`**: Nome do atributo DITA <br> -   **`to`**: nome da propriedade do componente AEM <br> -   **`ispath`**: Se o atributo for um valor de caminho \(por exemplo: *image*\) <br> -   **`rel`**: Se o caminho for a origem ou o destino <br> **Observação:** se `attrname` começar com `%`, mapeie `attrname minus '%'` para prop &#39; `propname`&#39;. |

**Observações adicionais**

- Se você planeja substituir o mapeamento de elemento padrão, é recomendável não fazer as alterações no arquivo `elementmapping.xml` padrão. Você deve criar um novo arquivo XML de mapeamento e colocar o arquivo em outro local, de preferência na pasta de aplicativos personalizados que você cria.

- No arquivo `elementmapping.xml`, há muitas entradas de mapeamento que fazem referência ao componente fmdita/components/dita/wrapper. Wrapper é um componente genérico que renderiza construções DITA relativamente simples usando propriedades no nó do site para gerar HTML relevantes. Ele usa a propriedade `wrapelement` para gerar tags de delimitação e delega a renderização secundária aos componentes correspondentes. Isso é útil nos casos em que você deseja apenas um componente de contêiner. Em vez de criar um novo componente que renderize uma marca de contêiner específica como `div` ou `p`, você pode usar o componente Wrapper com as propriedades `wrapelement` e `wrapclass` para obter o mesmo efeito.

- Não é recomendável salvar grandes quantidades de texto nas propriedades de JCR de string. O cálculo do tipo de propriedade otimizada na geração de saída garante que o conteúdo de texto grande não seja salvo como um tipo de sequência. Em vez disso, quando o conteúdo maior que um determinado limite precisa ser salvo, o tipo da propriedade é alterado para binário. Por padrão, esse limite está configurado para 512 bytes, mas pode ser alterado no Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) alterando a configuração **Salvar como Limite Binário**.

- Se você estiver planejando substituir alguns \(e não todos\) dos mapeamentos de elementos, não será necessário replicar todo o arquivo `elementmapping.xml`. É necessário criar um novo arquivo de mapeamento XML e definir apenas os elementos que você está substituindo.

- Depois de criar o arquivo XML no local personalizado, atualize a configuração `Override Element Mapping` no pacote `com.adobe.fmdita.config.ConfigManager`.


