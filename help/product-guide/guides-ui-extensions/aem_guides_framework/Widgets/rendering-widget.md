---
title: Widgets de renderização
description: Como a renderização funciona em widgets JUI
source-git-commit: f9a72e44fe1a3d90180ff728189a24ea9c7b1b1a
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Widgets de renderização

Podemos renderizar um widget referenciando-o usando seu `id`

Para renderizar o widget `widget_languages` em qualquer lugar no aplicativo, podemos usar a sintaxe simples:

```json
{
    "component": "widget",
    "id": "widget_languages"
}
```

Os widgets também podem ser usados para renderizar itens complexos, digamos que eu queira renderizar a lista de contribuidores para cada arquivo.
Aqui, o widget pode ser construído como:

```js title="fileContributorsWidget.js"
const widgetJSON =  {
    component: "div", 
    id: "file_contributors", 
    items: [ // adding components to the widget
        {
            component: "div",
            items: [
                {
                    component: "icon",
                    icon: "file"
                },
                {
                    component: "label",
                    label: "@fileName"
                }
            ]
        },
        {
            component: "list",
            data: "@contributors",
            itemConfig: {
                component: "label"
            }
        }
    ]
},
```

Agora, para renderizar uma lista de contribuidores para cada arquivo, escrevemos a lista como:

```js title="fileContributorsList.js"
const listJSON = {
    component: "list"
    data: "@files"
    itemConfig: {
        component: "widget",
        id: "file_contributors"
    }
}
```

Aqui `@files` é uma lista de objetos de arquivo contendo campos

```typescript
- fileName: string
- contributors: Array<String>
```
