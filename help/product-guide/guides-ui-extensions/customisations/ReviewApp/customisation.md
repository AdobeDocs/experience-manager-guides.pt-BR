---
title: Personalização
description: Personalização do aplicativo de revisão
role: User, Admin
exl-id: 9f6a4e9f-fc13-40b5-a30f-151c94faff81
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Personalização do aplicativo de revisão

Para facilitar a personalização do aplicativo de revisão, fornecemos alguns ganchos listados e explicados abaixo:

## Comentário de revisão

- id: `review_comment`
- gancho: `this.updateExtraProps`:

Conforme discutido [aqui](../../aem_guides_framework/basic-customisation.md), qualquer novo atributo adicionado durante a personalização fica em `this.model.extraProps`. O método `updateExtraProps` permite adicionar atributos a um comentário de revisão, manipulando também a atualização e o armazenamento do atributo adicionado no servidor.

### Exemplo de uso

Por exemplo, você deseja adicionar os campos `commentRationale` e `severity` aos seus comentários.
Vamos atualizar a `commentRationale` para &quot;Esta é uma frase importante&quot;. e de `severity` para &quot;CRÍTICO&quot;.
Isso pode ser feito usando a sintaxe:

```typescript
  this.next('updateExtraProps', {
    'commentRationale': 'This is an important sentence.',
    'severity': 'CRITICAL'
  })
```

O trecho de código acima lidará com a atualização e o salvamento dos valores. Os valores salvos podem ser renderizados na interface do usuário definindo a exibição.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Painel de revisão em linha

- id: `inline_review_panel`

1. gancho: `onNewCommentEvent`
O gancho `onNewCommentEvent` permite lançar um evento ou chamar um método em um novo evento de comentário ou resposta.
Os argumentos recebidos em `onNewCommentEvent` incluem:
   - events: o evento de comentário/resposta despachado.
   - newComment: booleano
Se o evento despachado foi um novo evento de comentário, isto é `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: booleano
Se o evento despachado tiver sido um novo evento de resposta.

2. gancho: `sendExtraProps`

Este gancho é benéfico se você quiser estender um `event` e enviar `extraProps` do painel de revisão em linha. Explicaremos o uso desses dois ganchos abaixo.

### Exemplo do painel de revisão em linha

Digamos que queiramos enviar um extraProp, `userInfo`, sempre que um novo comentário ou resposta for despachada. Agora, isso será feito por meio do painel de revisão em linha, no entanto, não temos a referência ao commentId do comentário recém-gerado, portanto, para fazer isso, podemos escrever o seguinte código.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.getValue('currTopicIndex') || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },
```

No trecho de código acima, estamos verificando se o evento despachado foi um novo comentário ou uma nova resposta. No caso de um novo comentário ou resposta, estamos chamando o método `setUserInfo`

```typescript
    setUserInfo(event) {
      this.loader?.getUserInfo(event.user).subscribe(userData => {
        const extraProps = {
          "userFirstName": userData?.givenName || '',
          "userLastName": userData?.familyName || '',
          "userTitle": userData?.title || '',
          "userJobTitle": userData?.jobTitle || '',
          'userEmail': userData?.email || '',
        }
        const data = {... event, extraProps}
        this.next(
          'sendExtraProps',
          data
        )
      })
    },
```

No método acima, estendemos o evento para enviar extraProps que incluem o nome do usuário, email, título etc. Estender o evento dessa maneira garante que os extraProps sejam enviados com a commentId correta, garantindo que sejam anexados ao comentário correto.

O gancho `updateExtraProps` inerentemente chama o gancho `sendExtraProps`, então quando usar o quê?

Usamos `updateExtraProps` no controlador `review_comment`, que já tem o `id` do comentário e, portanto, você só precisa mencionar o `extraProps.`

O `inline_review_panel`, no entanto, não tem acesso à id do comentário. Portanto, sempre que você precisar despachar um evento do painel de revisão em linha, o `sendExtraProps` será útil.
