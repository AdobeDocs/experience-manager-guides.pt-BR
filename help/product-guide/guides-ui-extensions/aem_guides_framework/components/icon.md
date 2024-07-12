---
title: Ícone
description: Ícone
role: User, Admin
exl-id: 5ba41c77-7329-49fc-bce5-02682261ea8e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 6%

---

# Ícone

Para exibir um ícone, usamos o componente, ícone.
O componente de área de texto na interface representa um html `<icon/>`.

Os ícones disponíveis em [Ícones do Espectro de Adobe](https://spectrum.adobe.com/page/icons/) são compatíveis com nosso aplicativo.

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

![Ícone](./imgs/info_icon.png "Ícone")
