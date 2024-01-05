---
title: Personalização do aplicativo
description: Personalização do aplicativo
source-git-commit: 20fb3f3556b5188764266e7fdf8aa876e45c1922
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Personalização do aplicativo

Nosso aplicativo segue uma estrutura MVC (Model, View, Controller)

## Modelo

O modelo define os vários atributos e armazena seus valores. Os valores dos vários atributos armazenados no modelo podem ser acessados do controlador usando a sintaxe

```typescript
this.model.attributeName
```

Para personalização no aplicativo, todos os atributos recém-criados serão adicionados a um mapa no modelo.
Para definir um novo atributo no modelo, usaremos a seguinte sintaxe no controlador:

```typescript
this.model.extraProps.set("key", value)
```

Para acessar um atributo adicionado ao modelo, usaremos a seguinte sintaxe:

```typescript
const value = this.model.extraProps.get("key")
```

## Exibir

A exibição define a interface do usuário do aplicativo. Usamos arquivos JSON para definir a visualização dos arquivos. Aqui, definimos os componentes, o css (conforme fornecido na classe de extração de componentes) e renderizamos os valores armazenados no modelo.
Em nosso aplicativo, cada exibição é definida usando um JSON. Os JSONs são referenciados usando suas IDs exclusivas chamadas de `id`.

## Controlador

O controlador é usado para manipular eventos e processar os dados. O controlador é usado para buscar e enviar dados do servidor, é a interface entre o que é exibido na interface do usuário e armazenado no back-end.

- Para definir valores na inicialização, usamos o `init` função.
- Para adicionar um método ao controlador, usamos a seguinte sintaxe:

```typescript
methodName: function(args){
    // functionality
}
```

A variável `methodName` aqui serve como `key` para fazer referência ao método no JSON (exibição) ou em outras funções

- Para chamar um método no controlador, usamos a sintaxe

```typescript
this.next('methodName', args)
```

## Exemplo

Agora vamos usar um exemplo simples para mostrar como esses três componentes interagem entre si.
Adicionaremos um botão que alterna o valor do rótulo em um clique

### Exibir exemplo

Abaixo, definimos o JSON para um botão que mostra um texto dinâmico armazenado no modelo sob o nome da variável `buttonLabel`.
Neste exemplo, clicar no botão altera seu rótulo.

```JSON
{
    "component": "button",
    "label": "@extraProps.buttonLabel",
    "variant": "cta",
    "on-click": "switchButtonLabel",
}
```

### Exemplo de modelo

neste caso, `extraProps.buttonLabel` mantém o rótulo do botão

### Exemplo de controlador

```typescript
  controller: {
    init: function () {
      this.model.extraProps.set("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.model.extraProps.get("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.model.extraProps.set("buttonLabel", buttonLabel)
    }
  }
```

O GIF abaixo mostra o código acima em ação
![basic_customization](imgs/basic_customisation.gif "Botão Personalização básica")
