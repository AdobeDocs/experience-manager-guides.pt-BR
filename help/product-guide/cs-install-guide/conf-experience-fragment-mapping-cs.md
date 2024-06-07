---
title: Configure o mapeamento baseado em JSON entre um tópico e um modelo de Fragmento de experiência.
description: Saiba como configurar o mapeamento baseado em JSON entre um tópico e um modelo de Fragmento de experiência.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: f252537d15d7e8f8651dddb0ae635905705e4adf
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Criar um mapeamento entre um tópico e um Fragmento de experiência

O Adobe Experience Manager Guides fornece o recurso para criar um mapeamento baseado em JSON entre um tópico e um modelo de Fragmento de experiência. Você pode usar esse mapeamento para publicar conteúdo presente em alguns ou todos os elementos de um tópico em um Fragmento de experiência.

1. Para baixar o *experienceFragmentMapping.json*, faça logon no Adobe Experience Manager como administrador.
1. Selecione o link Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione Guias na lista de ferramentas e selecione o **Perfis de pasta**.
1. Selecione o bloco do perfil que você deseja configurar. É possível configurar o mapeamento para o perfil global ou de nível de pasta. Por exemplo, selecione a variável **Perfil global** bloco.
1. Selecione o **Configuração do editor XML** e selecione a guia **Editar** ícone na parte superior.
1. Selecione o **Baixar** ícone para baixar o *experienceFragmentMapping.json*  no sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.

1. Você precisa seguir as seguintes validações:

   1. Deve ser um arquivo JSON
   2. Ela deve conter uma matriz contendo pelo menos um objeto, e cada objeto deve conter o seguinte:


      `"template": string `

      `"mapping": array`

      Cada objeto de mapeamento deve conter o seguinte:

      `"name": string`

      `"class": string`

      `"resourceType": string`

      `"attributeMap": array`


1. Salve o arquivo e faça upload dele.

Os Guias do Experience Manager convertem o tópico completo em HTML, que pode ser mapeado para os componentes principais usados no Fragmento de experiência. Por exemplo, o conteúdo em um `<p>` pode ser mapeada para criar um componente de texto no Fragmento de experiência.
* `name`: especifique o elemento de HTML. Por exemplo, `<div>`, `<img>`
* `class`: especifique a tag do elemento DITA correspondente ao elemento HTML. Por exemplo, `<p>` `<image>`
* `resourceType`: especifique o tipo de recurso aplicável ao componente usado no Fragmento de experiência. Por exemplo, `wcm/foundation/components/text` é o resourceType para o wcm `text` componente.
* `attributeMap`: forneça informações adicionais ao componente, como se um componente de texto deve ser renderizado como `RichText` ou contém o `fileReference` de um componente de imagem.




Arquivo de exemplo:

```
[
  {
    "template": "default",
    "mapping": [
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  },
  {
    "template": "/conf/we-retail/settings/wcm/templates/experience-fragment-web-variation",
    "mapping": [
      {
        "name": "div",
        "class": "title",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "h1, h2, h3, h4, h5, h6",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "div",
        "class": "p",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "img",
        "class": "image",
        "resourceType": "wcm/foundation/components/image",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "fileReference"
          }
        ]
      },
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  }
]
```



Ao publicar os Fragmentos de experiência no Editor da Web, selecione `Template` na lista suspensa do **Gerar fragmento de experiência** caixa de diálogo para exibir o mapeamento disponível para o modelo na **Mapeamento** campo. Se nenhum mapeamento personalizado estiver presente para um modelo, o mapeamento padrão será listado. Você pode usar o mapeamento padrão para publicar todo o tópico como um Fragmento de experiência.

Para obter mais detalhes, consulte [Publicar fragmentos de experiência](../user-guide/publish-experience-fragment.md).

