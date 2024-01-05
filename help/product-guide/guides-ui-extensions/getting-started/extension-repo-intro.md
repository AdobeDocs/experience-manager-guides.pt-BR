---
title: Introdução ao repositório de extensões
description: Estrutura do diretório do pacote de extensão de guias AEM
source-git-commit: 9345278dd02f5736e5384f3a97b2422894d20339
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---


# Estrutura do diretório do pacote de extensão de guias AEM

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
├── dist
│   ├── guides-extension.js
│   ├── guides-extension.umd.cjs
│   ├── build.css
├── node_modules
├── package.json
├── package-lock.json 
└── .gitignore
└── buildCSS.mjs // for creating tailwind classes
└── vite.config.js // config for specifying TS and javascript build options
└── taliwind.config.js // config for tailwind we can add custom config for a design system here
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```

## /src

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
```

O diretório de origem conterá os arquivos typescript ou javascript da sua extensão. O arquivo index.ts é o ponto de entrada da sua extensão. Você pode importar todos os seus componentes aqui e exportá-los como um único objeto. Esse objeto será usado pela extensão para renderizar os componentes.

### /dist

Este é o diretório de build final. Ele contém o JS e o CSS finais, que precisam ser copiados para o AEM

```test
├── dist
│   ├── gudies-extension.js // you can either choose es module (this one) or .cjs(other one) file
│   ├── gudies-extension.umd.cjs
│   ├── build.css // this is your tailwind css output
```

## /jsons

Esse diretório contém os JSONs para as várias exibições. Você pode usar esses JSONs para identificar os destinos e personalizar a exibição.

```text
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```
