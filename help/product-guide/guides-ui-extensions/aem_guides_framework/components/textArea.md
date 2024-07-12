---
title: Área do texto
description: Área do texto
role: User, Admin
exl-id: 4c576acc-fa6a-4c41-9b92-443ba51dc8ee
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 3%

---

# Campo de texto e área de texto

Para usar o texto como uma entrada, usamos os componentes, o campo de texto e a área de texto.
O componente de área de texto na interface representa um html `<textarea/>`.

```js title="textArea.js"
const textAreaJSON =  {
    "component": "textarea", //tells the component name
    "id": "input_name", // can be used to give a unique identifier to a component
    "data": "@name", // the variable storing the inputted text
    "on-keyup": {
        "name": "submitName",
        "eventArgs": {
            "keys": [
            "ENTER"
            ]
        }
    },
},
```

Aqui, `on-keyup` é a sintaxe para invocar os comandos nos controladores.
Isso produzirá uma textArea onde pressionar ENTER chamará o evento `submitName`

A área de texto renderizada terá esta aparência:

![área-texto](./imgs/text_area.png "Área-texto")
