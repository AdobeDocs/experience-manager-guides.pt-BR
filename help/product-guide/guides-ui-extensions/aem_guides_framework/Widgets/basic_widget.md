---
sidebar_position: 1
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '84'
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
