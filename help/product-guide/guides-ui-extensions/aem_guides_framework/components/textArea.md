---
sidebar_position: 3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 0%

---


# Campo de texto e área de texto

Para usar o texto como uma entrada, usamos os componentes, o campo de texto e a área de texto.
O componente de área de texto na JUI representa um html `<textarea/>`.

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

Aqui, `on-keyup` é a sintaxe para invocar os comandos nas controladoras.
Isso produzirá uma textArea onde pressionar ENTER chamará o evento `submitName`

A área de texto renderizada terá esta aparência:

![área-texto](./imgs/text_area.png "Área de texto")
