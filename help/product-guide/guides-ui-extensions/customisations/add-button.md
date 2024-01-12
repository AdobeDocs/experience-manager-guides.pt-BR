---
title: Personalização simples
description: Exemplo de personalização simples
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---


# Exemplo de personalização simples

Vamos agora saber como integrar essas personalizações no aplicativo Guias do AEM.

Queremos adicionar este botão em uma visualização existente do aplicativo.
Para isso, precisamos de 3 coisas básicas:

1. A variável `id` da visualização JSON à qual queremos adicionar nosso componente.
2. A variável `target`, ou seja, o local no JSON ao qual queremos adicionar o novo componente. A variável `target` é definido usando um `key` e `value`. O par de valor principal pode ser qualquer atributo usado para definir o componente que pode ajudar na identificação exclusiva dele.
Também podemos usar índices para fazer referência ao target.
Temos 3 viewStates:  `APPEND`, `PREPEND`, `REPLACE`.
3. O JSON do componente recém-criado e os métodos correspondentes.

Digamos que queiramos adicionar um botão à caixa de ferramentas de anotação usada na revisão, que abre o arquivo no AEM.

```typescript
export default {
  id: 'annotation_toolbox', 
  view: {
    items: [
      {
        component: 'button',
        icon: 'linkOut',
        title: 'Open topic in Assets view',
        'on-click': 'openTopicInAEM',
        target: {
          key: 'value',
          value: 'addcomment',
          viewState: VIEW_STATE.APPEND

        },
      },
    ],
  },
  controller: {
    openTopicInAEM: function (args) {
        const topicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC)
        const {allTopics = {}} = tcx.model.getValue(tcx.model.KEYS.REVIEW_DATA) || {}
        tcx.appGet('util').openInAEM(allTopics[topicIndex])
    },
  },
}
```

No exemplo acima, temos:

1. o `id` do JSON no qual queremos inserir nosso componente, ou seja, `annotation_toolbox`
2. o target é o `addcomment` botão. Adicionamos nosso botão após a variável `addcomment` botão usando o viewState `append`.
3. Definimos o evento de clique do botão no controlador.

O JSON para o &quot;annotation_toolbox&quot;  `.src/jsons/review_app/annotation_toolbox.json`

Antes da personalização, a caixa de ferramentas de anotação tinha esta aparência:

![annotation-toolbox](imgs/annotation_toolbox.png "Caixa de ferramentas de anotação")

Após a personalização, a caixa de ferramentas de anotação fica assim:

![custom-annotation-toolbox](imgs/customised_annotation_toolbox.png "Caixa de ferramentas de anotação personalizada")

## Adição de CSS

Para manter a consistência, fornecemos o componente já estilizado. O JSON inserido terá estilos inerentes aplicados a ele. A maneira principal de gerenciar o css é por meio da chave extraClass nas extensões.

```js
{    
    "view":{
        items:[
            {
                compoenent:"button",
                extraClass:"underline bg-red",
            }
        ]
    }
}
```

Você pode colocar estilos personalizados com classes CSS adicionando um arquivo css às clientlibs. Durante a build, também criamos [Tailwind](https://tailwindcss.com/docs/utility-first) saída para as classes de utilitários em tailwind. A configuração para o mesmo pode ser encontrada no `tailwind.config.js` em `./tailwind.config.js`
