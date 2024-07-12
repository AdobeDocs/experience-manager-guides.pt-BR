---
title: Lista
description: Lista
role: User, Admin
exl-id: 333b5e24-efba-4a51-8f68-83b5d1d7daec
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 5%

---

# Lista

Para exibir uma lista, usamos a lista de componentes.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@languages", // an array of list items
},
```

Aqui, a linguagem é uma simples matriz de strings. `languages = ["English", "Hindi", "French"]`
Caso queiramos renderizar uma lista de objetos, podemos especificar a estrutura usando a configuração de item.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@projects", // an array of list items
    "itemConfig": { // used to define the structure of the list items.
    "component": "widget",
    "id": "checkbox_label"
    }
},
```

Normalmente itemConfig é um `widget`. Para saber mais sobre widgets, vá para [Widgets](../Widgets/basic-widget.md)

A lista renderizada terá esta aparência:

![lista](./imgs/list.png "Lista")
