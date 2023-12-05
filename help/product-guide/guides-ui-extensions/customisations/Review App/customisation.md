---
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---
# Personalização do aplicativo de revisão

Para facilitar a personalização do aplicativo de revisão, fornecemos alguns ganchos listados e explicados abaixo:

## Comentário de revisão

- id: `review_comment`
- gancho: `this.updateExtraProps`:

Como discutido [aqui](../../aem_guides_framework/basic_customisation.md), qualquer novo atributo adicionado durante a personalização fica em `this.model.extraProps`. O método `updateExtraProps` permite adicionar atributos a um comentário de revisão, lidando com a atualização e o armazenamento do atributo adicionado no servidor também.

### Exemplo de uso

Por exemplo, você deseja adicionar campos `commentRationale` e `severity` aos seus comentários.
Vamos atualizar o `commentRationale` a &quot;Esta é uma frase importante.&quot; e a variável `severity` para &quot;CRÍTICO&quot;.
Isso pode ser feito usando a sintaxe:

```typescript
 this.updateExtraProps(
        {'commentRationale': 'This is an important sentence.',
        'severity': 'CRITICAL'}
      )
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
O gancho `onNewCommentEvent` permite lançar um evento ou chamar um método em um novo comentário ou evento de resposta.
Os argumentos recebidos no `onNewCommentEvent` incluem:
   - events: o evento de comentário/resposta despachado.
   - newComment: booleano Se o evento despachado foi um novo evento de comentário, ou seja, `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: booleano se o evento despachado foi um novo evento de resposta.

2. gancho: `sendExtraProps`

Esse gancho é benéfico se você quiser estender um `event` e enviar `extraProps` no painel de revisão em linha. Explicaremos o uso desses dois ganchos abaixo.

### Exemplo do painel de revisão em linha

Digamos que queremos enviar um extraProp, `userInfo`, sempre que um novo comentário ou resposta for enviado. Agora, isso será feito por meio do painel de revisão em linha, no entanto, não temos a referência ao commentId do comentário recém-gerado, portanto, para fazer isso, podemos escrever o seguinte código.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.model.currTopicIndex || "0"
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
        this.sendExtraProps(
          data
        )
      })
    },
```

No método acima, estendemos o evento para enviar extraProps que incluem o nome do usuário, email, título etc. Estender o evento dessa maneira garante que os extraProps sejam enviados com a commentId correta, garantindo que sejam anexados ao comentário correto.

O gancho `updateExtraProps` chama inerentemente o gancho `sendExtraProps`E quando usar o quê?

Usamos `updateExtraProps` no `review_comment` controlador, que já tem a função do comentário `id` e, portanto, é necessário mencionar o `extraProps.`

A variável `inline_review_panel` no entanto, o não tem acesso à id do comentário, portanto, sempre que for necessário enviar um evento do painel de revisão em linha, a variável `sendExtraProps` será útil.
