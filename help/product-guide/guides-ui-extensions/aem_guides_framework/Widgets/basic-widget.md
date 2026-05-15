---
title: Widgets
description: Noções básicas sobre widgets
role: User, Admin
exl-id: 96e960df-d595-4d58-8ad4-27057f857bac
TQID: https://experienceleague.adobe.com/SssVShlzFB3kjQCV-cNAOZVYb0TYSQ1CjtWoax2Q-LU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 86
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
