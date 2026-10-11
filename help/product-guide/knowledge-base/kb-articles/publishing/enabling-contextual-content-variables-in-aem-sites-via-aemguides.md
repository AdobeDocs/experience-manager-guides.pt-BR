---
title: Ativação das Variáveis de conteúdo contextual (CCVAR) nas páginas do AEM Sites geradas pelo AEM Guides
description: Trabalhar com variáveis de conteúdo contextual (CCVAR) em páginas do AEM Sites geradas pelo AEM Guides
feature: Web Editor
role: User, Admin
exl-id: f9adbb3f-6c1c-4d6f-b55d-1fb45acca91a
TQID: 'https://experienceleague.adobe.com/ehW4uJQaj3XqejwquxVwFo4vFx6q7qCsVIm6MowolZE'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 2%
---
# Ativação das Variáveis de conteúdo contextual (CCVAR) nas páginas do AEM Sites geradas pelo AEM Guides

As Variáveis de conteúdo contextual (CCVAR) são um recurso ACS Commons que permite aos autores usar variáveis de conteúdo dinâmico diretamente no texto criado. Embora o CCVAR seja usado com frequência no AEM Sites, este artigo explica como obter funcionalidade semelhante por meio de páginas geradas a partir do conteúdo criado no **AEM Guides** *principalmente usando palavras-chave definidas no mapa DITA*.


## O que são variáveis de conteúdo contextual (CCVAR)?

A CCVAR permite que os autores insiram variáveis dinâmicas em seu conteúdo, que é resolvido no tempo de execução com base no contexto. Por exemplo, variáveis como `((page_properties.pageTitle))` podem obter dinamicamente o título da página durante a renderização do conteúdo.


## Como ativar a CVAR em páginas do AEM Sites geradas pelo AEM Guides?

Considerando que o AEM Guides é usado como a fonte de todo o conteúdo (incluindo AEM Sites, PDF ou HTML5), para ativar as CCVARs nas páginas geradas pelo AEM Guides, é necessário usar palavras-chave para definir o nome da CCVAR. Para fazer isso em Guias, defina **palavras-chave** no mapa DITA usando elementos `<keydef>`. Essas palavras-chave podem corresponder a valores dinâmicos (ou nomes CVAR), permitindo que você as referencie em seus tópicos DITA.


## Pré-requisitos

Antes de continuar, verifique se os seguintes pré-requisitos foram atendidos:

1. **AEM ACS Commons Instalado**:
   - Verifique se o **ACS AEM Commons** está instalado em sua instância do AEM. Isso é necessário para usar a CCVAR.

2. **Configuração de variáveis de conteúdo contextuais**:
   - Conclua a configuração para **Variáveis de Conteúdo Contextual** no AEM usando a [documentação oficial](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html). Isso inclui:
     - Habilitando **Agregação de Propriedades**.
     - Configurando a **regravação de HTML** (se estiver usando a saída do HTML).
     - Configurando **regravação de JSON** (se estiver usando a saída JSON).



## Etapas para ativar a CCVAR no AEM Guides

### &#x200B;1. Definir palavras-chave no mapa DITA

- No AEM Guides, defina palavras-chave usando elementos `<keydef>` no mapa DITA para corresponder ao CCVAR.
- Por exemplo:

```xml
  <keydef keys="product">
    <topicmeta>
      <keywords>
        <keyword>((page_properties.pageTitle))</keyword>
      </keywords>
    </topicmeta>
  </keydef>
```

- O atributo `keys` (`product` neste exemplo) será usado para fazer referência a esta variável nos seus tópicos DITA.


## &#x200B;2. Usar palavras-chave em tópicos DITA

- No tópico, use a palavra-chave onde quer que a CCVar seja usada.
- Por exemplo:

```xml
  <p>This is the title of the product: <keyword keyref="product"/> </p>
```

- O atributo `keyref` aponta para o valor `keys` definido no elemento `<keydef>` (`product` neste caso).
- Durante a geração da saída, a palavra-chave será substituída pelo valor CCVar correspondente.


## &#x200B;3. Gerar saída

- Ao gerar a saída para o AEM Sites, as referências de palavra-chave serão resolvidas para os valores dinâmicos correspondentes.
- Por exemplo:
  - Se `((page_properties.pageTitle))` resolver para `My Product`, a saída exibirá:

```xml
   This is the title of the product: My Product.
```


## Exemplo de caso de uso

Suponha que você deseja inserir dinamicamente o idioma da página nos tópicos DITA. Veja como fazer isso:

**Definir a Palavra-chave no Mapa DITA**:

```xml
   <keydef keys="pageLanguage">
     <topicmeta>
       <keywords>
         <keyword>((inherited_page_properties.jcr:language))</keyword>
       </keywords>
     </topicmeta>
   </keydef>
```

**Referenciar a Palavra-chave em um Tópico DITA**:

```xml
   <p>The title of this page is: <keyword keyref="pageLanguage"/>.</p>
```

**Saída gerada**:

Se `((inherited_page_properties.jcr:language))` resolver para `en`, a saída exibirá:

```
     The language of this page is: en.
```


### Recursos

Para obter mais detalhes sobre **Variáveis de conteúdo contextuais**, consulte a documentação oficial:\
[Variáveis de conteúdo contextual no AEM Commons](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html)
