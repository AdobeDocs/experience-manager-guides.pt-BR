---
title: Personalização do aplicativo
description: Personalização do aplicativo
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
TQID: https://experienceleague.adobe.com/7DiEcUTAvp4rT3Fy9pIv4-zaHKwswjokjlaBgx8Pbyo
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 0%

---

# Personalização do aplicativo

## Funcionalidade exposta na estrutura de extensão

Expusemos um conjunto de funções e getters em um `proxy` que pode ser usado para acessar dados, configuração e eventos de acionador. Abaixo está uma lista e como acessá-las.

```typescript
interface EventData {
  key?: string,
  keys?: string[]
  view?: any,
  next?: any,
  error?: any,
  completed?: any,
  id?: any
}

* getValue(key)
* setValue(key, value)
* subject // getter
* subscribe(opts: EventData)
* subscribeAppEvent(opts: EventData)
* subscribeAppModel(key, next)
* subscribeParentEvent(opts: EventData)
* parentEventHandlerNext(eventName: string, opts: any)
* appModelNext(eventName:string, opts) 
* appEventHandlerNext(eventName:string, opts)
* next(eventName:string, opts, eventHandler?)
* viewConfig //getter
* args //getter
```

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
    init: function () {
      this.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

Abaixo do GIF, o código acima é exibido em ação
![basic_customization](imgs/basic_customisation.gif "Botão de personalização básica")


### Exibir exemplo de configuração

Nesse caso, acessamos o evento de modo de pesquisa usando `viewConfig` e acionamos um evento para atualizá-lo

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        console.log('Logging view config ', this.viewConfig)
        this.next(this.viewConfig.items[1].searchModeChangedEvent, { searchMode: true })
      }
    }
  }
```

### Exemplo de assinatura

Nesse caso, adicionamos a assinatura no arquivo renomear ao log do console quando a opção de renomeação de arquivo é clicada

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribe({
          key: 'rename',
          next: () => { console.log('rename using extension') }
        })
      }
    }
  }
```

### Exemplo de evento de aplicativo de assinatura

Nesse caso, console-se logon no documento ativo alterado (alterando guias na interface do editor)

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppEvent({
          key: 'app.active_document_changed',
          next: () => { console.log('Extension: active document changed') }
        })
      }
    }
  }
```

### Assinar o exemplo de eventos do modelo de aplicativo

Exemplo para assinar eventos de modelo de aplicativo, como `app.mode`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppModel('app.mode',
          () => { console.log('app mode subs') }
        )
      }
    }
  }
```

### Exemplo de eventos do controlador pai

Neste exemplo, adicionamos a assinatura no evento `tabChange`, que é um evento do controlador `left_panel_container` que atua
como controlador pai para `repository_panel`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeParentEvent({
          key: 'tabChange',
          next: () => { console.log('tab change subs') }
        })
        this.parentEventHandlerNext('tabChange', {
          data: 'map_panel'
        )
      }
    }
  }
```

### Próximo modelo de aplicativo e controlador de aplicativo

Elas podem ser acionadas diretamente ao conhecer o evento correto a ser acionado e seus dados

```typescript
  { 
    id: 'file_options', 
    controller: {
      init: function () {
        this.appModelNext('app.mode', 'author')
        this.appEventHandlerNext('app.active_document_changed', 'active doc changed')   
      }
    }
  } 
```
