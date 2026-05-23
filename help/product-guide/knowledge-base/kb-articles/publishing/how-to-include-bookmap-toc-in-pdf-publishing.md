---
title: Publicação de índice usando PDF nativo
description: Publicação de índice e outras listas de favoritos para o seu mapa de favoritos dita usando NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
TQID: https://experienceleague.adobe.com/GyB4TpCF64rEGNgHVPKq4fUCBQsJjqh4jWA0CJC4A-0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 322
ht-degree: 0%

---

# Gerar índice do mapa de livros na publicação do PDF

## Configurar o seu mapa de livros

Incluir o elemento `<toc>`:
No elemento `<frontmatter>` do seu mapa, localize o elemento `<booklists>`.  Aninhar um elemento `<toc>` dentro de `<booklists>` desta forma:

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

A especificação DITA também permite colocar o sumário e as listas de favoritos na seção `<backmatter>`.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

Exemplo de estrutura de mapa com índice, lista de figuras e lista de tabelas no material de frente e lista de índices no material de fundo.

```
<bookmap>
  <title>My Bookmap Title </title>
  <frontmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <tablelist/>
    </booklists>
  </frontmatter>

  <chapter href="chapter1.ditamap">
  <chapter href="chapter2.ditamap">
  </chapter>

  <backmatter>
    <booklists>
      <indexlist/>
    </booklists>
  </backmatter>
</bookmap>
```

O índice e as listas de favoritos são gerados automaticamente com base na estrutura definida no seu mapa de favoritos.

Depois que o bookmap for configurado, use o PDF nativo para gerar a saída do PDF. Ela processa a estrutura e as referências do mapa, incluindo o índice e as listas de favoritos.

## Design do índice e sua ordem no PDF

A funcionalidade nativa do PDF fornece um método conveniente para personalizar o layout e o design do índice.

Você pode controlar o design por meio de um layout de página separado para índice e estilos por meio de layout.css.

O índice e outros pedidos de listas de favoritos no PDF são baseados somente na estrutura do mapa de favoritos.

![toc](../assets/publishing/toc.png)


## Perguntas frequentes

### Como incluir o índice de um Ditamap em uma PDF

Os próprios mapas de dicionário não têm um sumário diretamente (índice), como um mapa tem. No entanto, os ditamaps desempenham um papel crucial na definição da estrutura do conteúdo e contribuem indiretamente para o processo de geração de índice.

Se você estiver publicando o Ditamap, o PDF Nativo fornecerá a funcionalidade para gerar o índice e a lista de livros automaticamente. Você pode habilitar/desabilitar a geração de índice no ditamap a partir das configurações do PDF Nativo.

![Habilitar Desabilitação do Sumário](../assets/publishing/pageorder.png)

## Recursos adicionais:

- [Documentação de layout da página de design nativa do PDF](https://experienceleague.adobe.com/pt-br/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Sessão de especialista nativa do PDF essentials pré-gravada](https://experienceleague.adobe.com/pt-br/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Publique qualquer consulta no [fórum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation?profile.language=pt) da Comunidade do AEM Guides.



