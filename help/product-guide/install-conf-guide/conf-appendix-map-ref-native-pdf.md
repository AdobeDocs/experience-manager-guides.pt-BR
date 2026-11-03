---
title: Configurar renderização do apêndice para referências de mapa na saída do PDF nativo
description: Saiba como configurar o Experience Manager Guides para renderizar tópicos adicionados em um submapa em um apêndice como conteúdo de apêndice na saída nativa do PDF.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 63ae0f947d50646bed34cd815db6b9fb585fc015
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%
---

# Configurar renderização do apêndice para referências de mapa na saída do PDF nativo

Na saída do PDF Nativo, os tópicos referenciados em um submapa dentro de um elemento `<appendix>` podem ser renderizados como capítulos em vez de apêndices. Por padrão, o Experience Manager Guides classifica as referências de mapa por nome de elemento e essas informações são perdidas quando os mapas são nivelados durante o processamento.

Use esta configuração para classificar referências de mapa usando o atributo `class` gerado pelo DITA-OT. Os tópicos em um submapa do apêndice são renderizados como apêndices.

>[!NOTE]
>
>Essa configuração altera a forma como as referências de mapa são classificadas. Ela está desativada por padrão. Habilite-a somente se o conteúdo colocar tópicos em um submapa em um `<appendix>` e você os vir renderizados como capítulos na saída do PDF Nativo.

## Quando usar esta configuração

Considere o exemplo a seguir de um mapa de livros:

- Um elemento `<appendix>` faz referência a tópicos diretamente. Esses tópicos são renderizados como apêndices no PDF gerado.

  ```XML
  <booktitle>
      <mainbooktitle>Product Guide</mainbooktitle>
    </booktitle>
    <frontmatter>
      <booklists>
        <toc/>
        <tablelist/>
      </booklists>
      <preface href="topics/preface.dita">
      </preface>
    </frontmatter>
    <chapter class="foo" href="topics/getting-started.dita">
    </chapter>  
    <appendix href="topics/appendix-reference-tables.dita">
    </appendix>
    <appendix href="topics/appendix-troubleshooting.dita">
    </appendix>
    <backmatter>
      <booklists>
        <indexlist/>
      </booklists>
    </backmatter>
  </bookmap>`
  ```

- Outro elemento `<appendix>` faz referência a um submapa, e o submapa faz referência a tópicos usando `<topicref>`.

  ```xml
  <booktitle>
      <mainbooktitle>Product Guide</mainbooktitle>
    </booktitle>
    <frontmatter>
      <booklists>
        <toc/>
        <tablelist/>
      </booklists>
      <preface href="topics/preface.dita">
      </preface>
    </frontmatter>
    <chapter class="foo" href="topics/getting-started.dita">
    </chapter>  
    <appendix format="ditamap" href="submap-for-appendix.ditamap" type="map">
    </appendix>
    <backmatter>
      <booklists>
        <indexlist/>
      </booklists>
    </backmatter>
  </bookmap>
  ```

  O submapa do apêndice:

  ```xml
  <map id="GUID-cc306264-825c-455e-89db-d27af9197a2f">
    <title>submap-for-appendix</title>
    <topicref href="topics/appendix-reference-tables.dita" type="reference">
    </topicref>
    <topicref href="topics/appendix-troubleshooting.dita" type="topic">
    </topicref>
  </map>
  ```

Sem essa configuração, os tópicos do primeiro apêndice são renderizados como apêndices, mas os tópicos do submapa são renderizados como capítulos. Somente os tópicos são publicados; o próprio submapa é usado para hierarquia e não aparece na saída.

## Definir a configuração

Veja a seguir as instruções para definir essa configuração:

1. Use as instruções fornecidas em [Substituições de configuração](../install-conf-guide/download-install-config-override.md) para criar o arquivo de configuração.

2. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

   | PID | Chave de propriedade | Valor de propriedade |
   | --------------------------------------- | -------------------------------- | ----------------------------- |
   | `com.adobe.fmdita.config.ConfigManager` | `guides.publish.config` | {USE_DITA_OT_GENERATED_CLASS&quot;: falso} |

3. Defina o valor como `true` para habilitar a configuração e implante a configuração usando o Cloud Manager.