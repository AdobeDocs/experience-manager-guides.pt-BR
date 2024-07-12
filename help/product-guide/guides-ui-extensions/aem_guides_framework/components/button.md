---
title: Botão
description: Botão
role: User, Admin
exl-id: 40e3f254-f94e-4f43-8ff5-2e6e1eb1cb6f
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 5%

---

# Botão

Para exibir um botão, usamos o componente, botão.
O componente de botão na interface do usuário representa um html `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Isso produzirá um botão com o rótulo `Yes, login`. As outras propriedades incluem, entre outras, variante, rótulo, clique.
> **_OBSERVAÇÃO:_** `on-<events>` é a sintaxe para invocar os comandos nos controladores.

O botão renderizado terá esta aparência:

![Botão](imgs/yes_login_button.png "Botão")
