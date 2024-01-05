---
title: Barra superior e Barra de ferramentas
description: Personalização da barra superior e da barra de ferramentas
source-git-commit: 5962414dfc065543b946cac1468a5f62013073cf
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 0%

---


# Personalização da barra superior e da barra de ferramentas

Para personalizar o `topbar` e `toolbar`, usaremos as ids: `topbar` ou `toolbar`e siga a mesma visualização, estrutura da controladora.

Veja abaixo um exemplo simples de personalização da barra de ferramentas. Aqui, removemos a variável `Insert Numbered List` e substituiu o botão `Insert Paragraph` com nosso próprio componente usando um manipulador personalizado ao clicar.

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
