---
title: Personalização do aplicativo
description: Personalização do aplicativo
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Personalização do aplicativo

Nosso aplicativo segue uma estrutura MVC (Model, View, Controller)

## Modelo

O modelo define os vários atributos e armazena seus valores. Os valores dos vários atributos armazenados no modelo podem ser acessados do controlador usando a sintaxe

```typescript
this.getValue('attributeName')
```

Para personalização no aplicativo, todos os atributos recém-criados serão adicionados a um mapa no modelo.
Para definir um novo atributo no modelo, usaremos a seguinte sintaxe no controlador:

```typescript
// If a key is not already in model then it will be added to extraProps
this.setValue('key', value)
```

Para acessar um atributo adicionado ao modelo, usaremos a seguinte sintaxe:

```typescript
const value = this.getValue("key")
```

## Exibir

A exibição define a interface do usuário do aplicativo. Usamos arquivos JSON para definir a visualização dos arquivos. Aqui, definimos os componentes, o css (conforme fornecido na classe de extração de componentes) e renderizamos os valores armazenados no modelo.
Em nosso aplicativo, cada exibição é definida usando um JSON. Os JSONs são referenciados usando suas IDs exclusivas chamadas de `id`.

## Controlador

O controlador é usado para manipular eventos e processar os dados. O controlador é usado para buscar e enviar dados do servidor, é a interface entre o que é exibido na interface do usuário e armazenado no back-end.

- Para definir valores na inicialização, usamos a função `init`.
- Para adicionar um método ao controlador, usamos a seguinte sintaxe:

```typescript
methodName: function(args){
    // functionality
}
```

O `methodName` aqui serve como `key` para fazer referência ao método no JSON (exibição) ou em outras funções

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

neste caso, `extraProps.buttonLabel` contém o rótulo do botão

### Exemplo de controlador

```typescript
  controller: {
    init: function (context) {
      context.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

O GIF abaixo mostra o código acima em ação
![basic_customization](imgs/basic_customisation.gif "Botão de personalização básica")
