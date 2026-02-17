---
title: Sobrepor as tags do HTML na saída do AEM Sites não herdada
description: Defina as configurações de vídeo e imagem para a saída do aem sites com base no mapeamento dos componentes principais
feature: Installation
role: Admin
level: Experienced
exl-id: 726420e0-fe52-4334-b72a-8eb8bcae4d6c
source-git-commit: e0b0df19b7ec691a894130eb42df827921b4890c
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---

# Sobrepor tags do HTML na saída do AEM Sites

Você pode adicionar e personalizar tags HTML na saída do AEM Sites gerada usando a predefinição do AEM Sites com base no mapeamento dos componentes principais do Editor da Web. Para personalizar as marcas HTML, você pode sobrepor o arquivo `config.xml`. Por exemplo, você pode configurar os mapas de vídeo e imagem na saída do AEM Sites.

Execute as seguintes etapas para sobrepor e atualizar o arquivo `config.xml`:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Navegue até o arquivo de configuração disponível no seguinte local:

   `/libs/cq/xssprotection/config.xml`

1. Crie um nó de sobreposição da pasta `xssprotection` no nó de aplicativos.

1. Navegue até o arquivo de configuração disponível no nó `apps`:

   `/apps/fmdita/config/config.xml`

1. Atualize as tags a seguir para os vídeos e imagens. Em seguida, salve o arquivo.

Vídeos:

```XML
    <tag name="video" action="validate">
    <attribute name="src">
      <regexp-list>
        <regexp name="anything"/>
      </regexp-list>
    </attribute>
    <attribute name="width">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="height">
       <regexp-list>
          <regexp name="anything"/>
       </regexp-list>
     </attribute>
     <attribute name="data">
       <regexp-list>
         <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="class">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="poster">
      <regexp-list>
        <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="controls">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="source" action="validate">
      <attribute name="src">
        <regexp-list>
           <regexp name="anything"/>
        </regexp-list>
      </attribute>
    </tag>
```

Mapas de imagem:

```XML
        <tag name="map" action="validate">
    <attribute    name="name">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <!-- Image & image related tags -->
    <tag name="img" action="validate">
    <attribute name="src" onInvalid="removeTag">
        <regexp-list>
            <regexp name="onsiteURL"/>
            <regexp name="offsiteURL"/>
        </regexp-list>
    </attribute>
    <attribute name="name"/>
    <attribute name="alt"/>
    <attribute name="height"/>
    <attribute name="width"/>
    <attribute name="border"/>
    <attribute name="align"/>
    <attribute name="usemap">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="hspace">
        <regexp-list>
            <regexp name="number"/>
        </regexp-list>
    </attribute>
    <attribute name="vspace">
        <regexp-list>
            <regexp name="number"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="area" action="validate">
    <attribute name="shape">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="coords">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="href">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
   </tag>
```




Saiba mais sobre as práticas recomendadas do [Security](https://experienceleague.adobe.com/pt-br/docs/experience-manager-65/content/implementing/developing/introduction/security).
