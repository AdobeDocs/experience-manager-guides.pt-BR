---
title: Recurso nativo do PDF Publish | Adicionar código de barras
description: Saiba como adicionar códigos de barras.
exl-id: 206bdcf9-2bcd-4bf1-815a-c97cdf0dc415
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 0%

---

# Adicionar um código de barras à saída do PDF

Um código de barras é um padrão de dados que as máquinas podem ler. Os clientes podem digitalizar códigos de barras com um scanner de código de barras ou a câmera do smartphone. Informações de codificação, como detalhes do produto, números de inventário ou URLs de site, podem ser úteis. A adição de códigos de barras ajuda a capturar os dados facilmente, melhora a experiência do cliente e facilita um melhor gerenciamento e segurança dos dados.

É possível criar um estilo para o código de barras. e use-o para inserir um código de barras em um layout de página. Aplique o estilo a um exemplo de código de barras no layout de página desejado.


Este tutorial ajuda você a adicionar códigos de barras na saída do PDF.

## Etapas para gerar um código de barras

Para gerar um código de barras, execute as seguintes etapas:

### Atualizar o CSS do modelo para renderizar um valor de código de barras

Modifique o arquivo `layout.css` para renderizar um código de barras durante a geração do PDF. Vários tipos de código de barras, como &quot;qrcode&quot; e &quot;pdf417&quot;, são compatíveis.  Para obter mais detalhes, consulte [Tipos de código de barras](#barcode-types).



```css
...
.barcode { 
-ro-replacedelement: barcode;   
-ro-barcode-type: code128;   
-ro-barcode-size: 100%;   
-ro-barcode-content: content();   
object-fit: contain;   
margin-top: 2mm;
 
}
...
```

### Usar o estilo CSS para gerar o código de barras

Você pode gerar o código de barras de maneiras diferentes. Alguns exemplos são os seguintes:

**Exemplo 1**

Adicione um espaço reservado para código de barras no cabeçalho do modelo e aplique o estilo:

1. Editar **Modelos** > **Layouts de Página**
1. Selecione um layout de página. Por exemplo, é possível selecionar o layout de página BackCover, que contém o cabeçalho ou o rodapé.
1. Adicione o trecho a seguir ao local em que deseja inserir o código de barras.

   `<span class="barcode">Sample barcode</span></p>`.

   >[!NOTE]
   >
   > Use o mesmo nome de classe definido em `layout.css`.

1. Substitua `<Sample barcode>` pelo valor que você deseja que o scanner de código de barras leia.

É possível visualizar o código de barras ao gerar o PDF de saída usando o modelo, que inclui o layout da página. Depois de executar as etapas anteriores, é possível gerar a saída de PDF com um código de barras.

A captura de tela a seguir exibe um exemplo de código de barras em uma saída de PDF.

<img src="./assets/barcode-output-sample.png" alt="Exemplo de saída com código de barras" width="700" border="2px">

**Exemplo 2**

Modifique o arquivo `Common.plt` no modelo **Básico** para adicionar um código de barras após o título do projeto.

Para criar um código de barras para um número ISBN, adicione um número ISBN. Em seguida, use o número ISBN para gerar o código de barras.

```html
...

  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode">978-1-56619-909-4</span></p>
  </div>
} 
...
```

**Exemplo 3**

Para criar um código de barras usando os metadados do mapa:

Use todos os metadados presentes no elemento `<topicmeta>` de um mapa DITA para exibir como código de barras. Certifique-se de usar o XPath correto. Por exemplo, você pode adicionar um `<resourceid>` no `<topicmeta>` de um mapa DITA.

No exemplo a seguir, a ID do recurso serve como a entrada principal para gerar o código de barras.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<map id="GUID-3c330691-4dac-4020-904a-d2d6246aeeb1-en">
  <title>Barcode Sample</title>
  <topicmeta>
    <resourceid id="7a5bda1c-b1db-4fd8-8763-a731e2e8abba">
    </resourceid>
  </topicmeta>
  <topicref href="GUID-139f6c64-bea3-4f17-8b22-ee131557e249-en.dita" type="topic">
  </topicref>
</map>  
```



Você pode usar a ID do recurso em um layout de página da seguinte maneira:


```html
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
```

## Tipos de código de barras {#barcode-types}

Alguns dos códigos de barras usados com frequência são os seguintes:

| Tipo | -ro-barcode-type | Detalhes adicionais |
| ---| --- | --- |
| Código QR | qrcode | A simbologia do código de barras QR de acordo com a norma ISO/IEC 18004:2015. |
| Código 128 | code128 | A simbologia do código de barras 128, conforme definido na norma ISO/IEC 15417:2007. |
| Código 32 | code32 | Código 32, também conhecido como harmacode italiano. |
| Código 49 | code49 | Código 49 de acordo com ANSI/AIM-BC6-2000. |
| Código 11 | código11 |                            |
| Código 93 | code93 |                            |
| Code16k | code16k |                            |
| PDF417 | pdf417 | As simbologias de código de barras PDF417/MicroPDF417 de acordo com ISO/IEC 15438:2006 e ISO/IEC 24728:2006. |
| Código 3 de 9 | code39 | O código 3 de 9 código de barras de acordo com a ISO/IEC 16388:2007. |
| MSI Plessey | msiplessey |                            |
| Código do canal | channelcode | Código do canal de acordo com ANSI/AIM BC12-1998. |
| Codabar | codabar | Simbologia do código de barras de Codabar de acordo com a norma BS EN 798:1996. |
| EAN-8 | ean-8 | Simbologia de código de barras EAN de acordo com BS EN 797:1996. |
| EAN-13 | ean-13 | Simbologia de código de barras EAN de acordo com BS EN 797:1996. |
| UPC-A | upc-a | Simbologia do código de barras UPC de acordo com a norma BS EN 797:1996. |
| UPC-E | upc-e | Simbologia do código de barras UPC de acordo com a norma BS EN 797:1996. |
| Complemento Ean/UPC | complemento | Simbologia do código de barras suplementar EAN/UPC de acordo com a norma BS EN 797:1996. |
| Telepen | telepen | Também conhecido como Telepen Alpha. |
| Barra de Dados GS1/Barra de Dados 14 | barra de dados | Barra de dados GS1 de acordo com ISO/IEC 24724:2011. |
| Barra de Dados GS1 Expandida / Barra de Dados 14 Expandida | barra de dados expandida | Barra de dados GS1 expandida de acordo com ISO/IEC 24724:2011. |
| GS1 Databar Limited | limitado à barra de dados | GS1 DataBar Limited de acordo com ISO/IEC 24724:2011. |
| POSTNET (Técnica de codificação numérica postal) | postnet | A simbologia de código de barras POSTNET (Postal Numeric Encoding Technique) usada pelo Serviço Postal dos Estados Unidos. |
| Número farmazentral (PZN-8) | pzn8 | Uma simbologia baseada no código 39 utilizada pela indústria farmacêutica na Alemanha. |
| Pharmacode | farmacode |                            |
| Codablock F | codablockf | Simbologia de acordo com AIM Europa &quot;Uniform Symbology Specification Codablock F&quot;, 1995. |
| Logmars | logmars | O padrão LOGMARS (Logistics Applications of Automated Marking and Reading Symbols) usado pelo Departamento de Defesa dos EUA. |
| Runas astecas | aztec-runes | Simbologia do código de barras das runas astecas de acordo com ISO/IEC 24778:2008, anexo A. |
| Código asteca | aztec-code | Código de barras de código asteca de acordo com ISO/IEC 24778:2008. |                            |
| DataMatrix | matriz de dados | Matriz de dados Código de barras ECC 200 de acordo com ISO/IEC 16022:2006. |
| Código um | code-one |                            |
