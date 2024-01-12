---
title: Área do texto
description: Área do texto
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 3%

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
