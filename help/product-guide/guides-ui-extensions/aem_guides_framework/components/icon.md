---
sidebar_position: 4
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 2%

---


# Ícone

Para exibir um ícone, usamos o componente, ícone.
O componente de área de texto na JUI representa um html `<icon/>`.

Ícones disponíveis em [Ícones do Espectro de Adobe](https://spectrum.adobe.com/page/icons/) são compatíveis com nosso aplicativo.

```js title="icon.js"
const iconJSON =  {
    "component": "icon", //tells the component name
    "icon": "info", // name of the icon to be used
    "size": "S", // size of the icon
    "title": "Information" // tooltip corresponding to the icon.
},
```

os ícones também podem ser adicionados aos botões.

O ícone renderizado terá esta aparência:

![ícone](./imgs/info_icon.png "Ícone")
