---
title: Barra superior e Barra de ferramentas
description: Personalização da barra superior e da barra de ferramentas
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 0%

---

# Personalização da barra superior e da barra de ferramentas

Para personalizar o `topbar` e o `toolbar`, vamos usar as ids: `topbar` ou `toolbar` e seguir a mesma exibição, estrutura de controlador.

Veja abaixo um exemplo simples de personalização da barra de ferramentas. Aqui, removemos o botão `Insert Numbered List` e substituímos o botão `Insert Paragraph` pelo nosso próprio componente usando um manipulador personalizado de cliques.

```js title = toolbar_customisation.js
const toolbarExtend = {
    id: "toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Numbered List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                {
                    "component": "button",
                    "icon": "textParagraph",
                    "variant": "action",
                    "quiet": true,
                    "title": "Insert Paragraph",
                    "on-click": "INSERT_P"
                },

                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
        ]
    },
    controller: {

        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
