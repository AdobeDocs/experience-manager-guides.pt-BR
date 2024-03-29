---
title: Widgets
description: Noções básicas sobre widgets
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 0%

---


# Widgets

Vários componentes básicos, conforme discutido na seção Componentes, podem ser combinados para criar um widget.
Os widgets podem ser usados para criar um novo componente &quot;mais complexo&quot; ou estruturar os itens de um componente.

Vamos mergulhar no conceito de um widget!

Começaremos criando um widget simples para exibir uma lista de idiomas.

```js title="basicWidget.js"
const widgetJSON =  {
    "component": "div", 
    "id": "widget_languages", 
    "items": [ // adding components to the widget
        {
            "component": "div",
            "items": [
                {
                    "component": "icon",
                    "icon": "info"
                },
                {
                    "component": "label",
                    "label": "List of some languages"
                }
            ]
        },
        {
            "component": "list",
            "data": "@languages"
        }
    ]
},
```

Aqui, `@languages` é uma matriz definida no modelo de `widget_languages` como: [&quot;Inglês&quot;, &quot;Francês&quot;, &quot;Hindi&quot;, &quot;Espanhol&quot;, &quot;Urdu&quot;]

O widget básico renderizado terá esta aparência:

![basic_widget](imgs/basic_widget.png "Widget básico")
