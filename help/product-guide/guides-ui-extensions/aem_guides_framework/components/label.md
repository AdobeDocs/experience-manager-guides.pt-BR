---
title: Rótulo
description: Rótulo
role: User, Admin
exl-id: aceefb08-3198-4c3a-90ec-ac1cdde28582
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%

---

# Rótulo

Para exibir qualquer texto ou string, usamos o componente, rótulo.
O componente de rótulo na IU representa um html `<label/>`.

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
