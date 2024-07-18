---
title: Barra superior e Barra de ferramentas
description: Personalização da barra superior e da barra de ferramentas
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: 4f41609368b64415993b93be27162b069e7b2e32
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# Personalização da barra superior e da barra de ferramentas

Para personalizar o `topbar` e o `toolbar`, vamos usar as ids: `topbar` ou `toolbar` e seguir a mesma exibição, estrutura de controlador.

Veja abaixo um exemplo simples de personalização da barra de ferramentas. Aqui, removemos o botão `Insert Numbered List` e substituímos o botão `Insert Paragraph` pelo nosso próprio componente usando um manipulador personalizado de cliques.

Para acessar a funcionalidade exposta sob o objeto `proxy`, precisaremos acessá-la usando `this.proxy.getValue`, digamos, para buscar um valor.

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
        init: function() {
            console.log(this.proxy.getValue("canUndo"))
            this.proxy.subscribeAppEvent({
              key: "editor.preview_rendered",
              next: async function (e) {
                console.log(this.proxy.getValue("canUndo"))
              }.bind(this)
            })
        },
        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
