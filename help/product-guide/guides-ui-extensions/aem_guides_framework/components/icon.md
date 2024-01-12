---
title: Ícone
description: Ícone
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 6%

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
