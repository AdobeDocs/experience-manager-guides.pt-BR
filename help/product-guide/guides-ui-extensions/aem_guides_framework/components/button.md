---
title: Botão
description: Botão
source-git-commit: 2e1cb576fa3b0a765304508e5f7962a154f1a72c
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 5%

---


# Botão

Para exibir um botão, usamos o componente, botão.
O componente de botão na JUI representa um html `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Isso produzirá um botão com um rótulo de `Yes, login`. As outras propriedades incluem, entre outras, variante, rótulo, clique.
> **_NOTA:_**  A variável `on-<events>` é a sintaxe para invocar os comandos nas controladoras.

O botão renderizado terá esta aparência:

![botão](imgs/yes_login_button.png "Botão")
