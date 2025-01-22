---
title: Ativação de variáveis de conteúdo contextual (CCVAR) no AEM Sites via AEM Guides
description: Trabalhar com variáveis de conteúdo contextual (CCVAR) no AEM Sites via AEM Guides
exl-id: null
feature: Web Editor
role: User, Admin
source-git-commit: ac40ab63b691ea31dfa1a3c9f7644b357b3167a4
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 1%

---

# Ativação de variáveis de conteúdo contextual (CCVAR) no AEM Sites via AEM Guides

As Variáveis de conteúdo contextual (CCVAR) são um recurso ACS Commons que permite aos autores usar variáveis de conteúdo dinâmico diretamente no texto criado. Embora o CCVAR seja usado com frequência no AEM Sites, este artigo explica como obter funcionalidade semelhante por meio de páginas geradas a partir do conteúdo criado no **AEM Guides** *principalmente usando palavras-chave definidas no mapa DITA*.


## O que são variáveis de conteúdo contextual (CCVAR)?

A CCVAR permite que os autores insiram variáveis dinâmicas em seu conteúdo, que é resolvido no tempo de execução com base no contexto. Por exemplo, variáveis como `((page_properties.pageTitle))` podem obter dinamicamente o título da página durante a renderização do conteúdo.


## Como ativar o CVAR no AEM Sites gerado pela AEM Guides?

Considerando que o AEM Guides é usado como a fonte de todo o conteúdo (incluindo AEM Sites, PDF ou HTML5), para habilitar CCVARs em páginas geradas pelo AEM Guides, é necessário usar palavras-chave para definir o nome do CCVAR. Para fazer isso em Guias, defina **palavras-chave** no mapa DITA usando elementos `<keydef>`. Essas palavras-chave podem corresponder a valores dinâmicos (ou nomes CVAR), permitindo que você as referencie em seus tópicos DITA.


## Pré-requisitos

Antes de continuar, verifique se os seguintes pré-requisitos foram atendidos:

1. **Comuns AEM ACS Instalados**:
   - Certifique-se de que o **ACS AEM Commons** esteja instalado em sua instância do AEM. Isso é necessário para usar a CCVAR.

2. **Configuração de variáveis de conteúdo contextuais**:
   - Conclua a configuração para **Variáveis de Conteúdo Contextual** no AEM usando a [documentação oficial](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html). Isso inclui:
      - Habilitando **Agregação de Propriedades**.
      - Configurando **Reescrita de HTML** (se estiver usando a saída de HTML).
      - Configurando **regravação de JSON** (se estiver usando a saída JSON).



## Etapas para ativar a CCVAR no AEM Guides

### 1. Definir palavras-chave no mapa DITA

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


## 2. Usar palavras-chave em tópicos DITA

- No tópico, use a palavra-chave onde quer que a CCVar seja usada.
- Por exemplo:

```xml
  <p>This is the title of the product: <keyword keyref="product"/> </p>
```

- O atributo `keyref` aponta para o valor `keys` definido no elemento `<keydef>` (`product` neste caso).
- Durante a geração da saída, a palavra-chave será substituída pelo valor CCVar correspondente.


## 3. Gerar saída

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