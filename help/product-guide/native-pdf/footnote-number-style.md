---
title: Recurso de publicação de PDF nativo | Usar estilos personalizados em notas de rodapé
description: Saiba como aplicar estilo aos números em notas de rodapé.
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 0%

---

# Aplicar estilos de nota de rodapé


As notas de rodapé são notas colocadas na parte inferior de uma página que comenta ou cita uma referência para uma parte designada do texto.

Cada nota de rodapé tem um marcador na parte inferior da página, que geralmente é um número ou um símbolo, como um asterisco. Dentro do conteúdo principal, o mesmo marcador de nota de rodapé é exibido como uma chamada de nota de rodapé e é indicado pelo mesmo número ou símbolo que um sobrescrito.




## Alterar os estilos de chamadas e marcadores de notas de rodapé

É possível alterar os estilos das chamadas e dos marcadores de notas de rodapé e gerenciar sua aparência na saída de PDF. Esses estilos ajudam a identificar rapidamente as notas de rodapé no documento.


**Exemplo 1**:

Use o exemplo fornecido para adicionar um colchete antes e depois da chamada de nota de rodapé e do marcador:

* Adicione o prefixo &quot;(&quot; e o sufixo &quot;)&quot; usando o atributo content na variável `footnote-call` estilo, que adicionará os colchetes ao redor do número da nota de rodapé no conteúdo do tópico.
* Adicione o prefixo &quot;(&quot; e o sufixo &quot;)&quot; usando o atributo content na variável `footnote-marker` estilo, que adicionará os colchetes ao redor do número da nota de rodapé na parte inferior da página.

```css
...
.fn::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.fn::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```



<img src="./assets/pdf-output-footer-numbers.png" alt="Rodapé na saída do PDF" width="500" border="2px">

*Adicione colchetes ao redor da chamada de nota de rodapé e do marcador de nota de rodapé.*

**Exemplo 2**:

Também é possível sinalizar a chamada e o marcador da nota de rodapé com um asterisco ou um caractere grego inferior em vez de um número.


```css
.fn::footnote-call {
 content: counter(footnote, asterisks);
}
.fn::footnote-marker {
 content: counter(footnote, asterisks) " ";
}
```

Na saída, é possível visualizar algo como:

<img src="./assets/footnote-number-2.png" alt="Rodapé na saída do PDF" width="500" border="2px">

*Adicione asterisco a uma chamada de nota de rodapé e marcador.*

## Ocultar uma chamada de nota de rodapé

Também é possível aplicar um estilo a chamadas de nota de rodapé com atributos específicos. Por exemplo, use o seguinte estilo para ocultar uma nota de rodapé com as IDs: a chamada de nota de rodapé está oculta no conteúdo principal, mas o marcador de nota de rodapé aparece na parte inferior da página.

```css
.fn[id]::footnote-call {
		display: none;
                        }
```

## Formatar a área da nota de rodapé

A área da nota de rodapé é onde todas as notas de rodapé são colocadas, geralmente na parte inferior de uma página. É possível formatar a área da nota de rodapé usando os layouts de página ou estilos CSS.


### Layouts de página

É possível usar as propriedades de página dos layouts de página para estilizar a área da nota de rodapé nas diferentes seções de um documento PDF. Por exemplo, você pode especificar as margens e as propriedades de preenchimento da área da nota de rodapé em um capítulo. Também é possível alterar o lado da borda, o estilo, a cor, a largura e o raio.

Saiba como [trabalhar com as propriedades de página de um layout de página](./design-page-layout.md#page-props-page-layout).

### Estilos CSS

É possível aplicar estilos e formatar a área da nota de rodapé em um documento PDF. Por exemplo, é possível alterar o comprimento, o estilo, a cor e a largura da borda.

```css
	@page {
	  @footnote {
   		border-top-style: solid;
   		border-top-color: #FF0000;
   		border-top-width: 3px;
 		        }
	      }
```

## Reiniciar a numeração das notas de rodapé

Por padrão, as notas de rodapé são numeradas continuamente em um documento. No entanto, você pode usar layouts de página ou estilos CSS para reiniciar a numeração de notas de rodapé.


### Layouts de página

Você pode especificar um número nos layouts de página para reiniciar a numeração de notas de rodapé nas diferentes seções de um documento PDF. Por exemplo, selecione um número na **Reiniciar numeração de** no painel Propriedades da página para reiniciar a numeração da nota de rodapé de cada capítulo.

### Estilos CSS

Use o estilo a seguir para redefinir a numeração de notas de rodapé em cada página da saída de PDF:

```css
@page
{
counter-reset: footnote
}
```

Assim, as notas de rodapé em cada página reiniciam a partir do 1.

## Exibir notas de rodapé incorporadas

Normalmente, cada nota de rodapé aparece como um bloco ou começa em uma nova linha. Mas você também pode colocá-los na fila ou próximos um do outro.

```css
.fn{
  	display: inline;
              }
```

## Aplicar estilos a referências cruzadas de notas de rodapé

Também é possível fazer referência cruzada de uma nota de rodapé e fazer referência à mesma nota de rodapé várias vezes na saída em PDF. Isso ajuda a fazer referência à mesma citação ou nota detalhada várias vezes no documento, sem criar uma nota de rodapé para ela novamente.

Por exemplo, a captura de tela a seguir mostra como a mesma nota de rodapé é referenciada para todas as cidades na saída do PDF.
<img width="550" alt="referências de notas de rodapé em um pdf" src="./assets/link-footnotes.png" border="2px">

*Inserir a referência cruzada a uma nota de rodapé.*





Usando estilos CSS, você também pode formatar as referências cruzadas para notas de rodapé. Por exemplo, é possível alterar a cor de fundo das referências cruzadas.

```css
    .xref-fn{
	background-color: red;
	}
```



