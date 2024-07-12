---
title: Widgets de renderização
description: Como a renderização funciona em widgets JUI
role: User, Admin
exl-id: 381cc7b9-c957-40be-9db4-8347eefe2fa7
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
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
