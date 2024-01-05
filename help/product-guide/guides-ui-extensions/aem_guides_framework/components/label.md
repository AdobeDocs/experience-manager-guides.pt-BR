---
title: Etiqueta
description: Etiqueta
source-git-commit: 2e1cb576fa3b0a765304508e5f7962a154f1a72c
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%

---

# Etiqueta

Para exibir qualquer texto ou string, usamos o componente, rótulo.
O componente de rótulo na JUI representa um html `<label/>`.

Veja abaixo um exemplo de adição de rótulo estático

```js title="staticLabel.js"
const staticLabelJSON =  {
    "component": "label", //tells the component name
    "label": "This is an example label", // the string to be displayed
}
```

Abaixo do JSON é exibida uma string dinâmica:

```js title="dynamicLabel.js"
const labelJSON =  {
    "component": "label", //tells the component name
    "label": "@name", // the variable storing the text to be displayed
},
```

O rótulo renderizado terá esta aparência:

![rótulo](./imgs/label.png "Rótulo")