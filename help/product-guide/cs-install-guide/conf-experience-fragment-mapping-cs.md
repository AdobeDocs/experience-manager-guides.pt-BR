---
title: Configure o mapeamento baseado em JSON entre um tópico e um modelo de Fragmento de experiência.
description: Saiba como configurar o mapeamento baseado em JSON entre um tópico e um modelo de Fragmento de experiência.
feature: Output Generation
role: Admin
level: Experienced
exl-id: 2b59db60-61b5-4a7e-bbf1-35cab8b89323
TQID: https://experienceleague.adobe.com/bV5SVF5pLwakZ-0auAHQc8dRH6e7axDGZQufU0i9p14
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 406
ht-degree: 0%

---

# Criar um mapeamento entre um tópico e um Fragmento de experiência

O Adobe Experience Manager Guides fornece o recurso para criar um mapeamento baseado em JSON entre um tópico e um modelo de Fragmento de experiência. Você pode usar esse mapeamento para publicar conteúdo presente em alguns ou todos os elementos de um tópico em um Fragmento de experiência.

1. Para baixar o *experienceFragmentMapping.json*, entre no Adobe Experience Manager como administrador.
1. Selecione o link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione Guias na lista de ferramentas e selecione a **Pasta Perfis**.
1. Selecione o bloco do perfil que você deseja configurar. É possível configurar o mapeamento para o perfil global ou de nível de pasta. Por exemplo, selecione o bloco **Perfil Global**.
1. Selecione a guia **Configuração do Editor XML** e selecione o ícone **Editar** na parte superior.
1. Selecione o ícone **Baixar** para baixar o arquivo *experienceFragmentMapping.json* no sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.

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

O Experience Manager Guides converte o tópico completo para o HTML, que pode ser mapeado para os componentes principais usados no Fragmento de experiência. Por exemplo, o conteúdo em uma marca `<p>` pode ser mapeado para criar um componente de texto no Fragmento de experiência.
* `name`: especifique o elemento HTML. Por exemplo, `<div>`, `<img>`
* `class`: especifique a marca do elemento DITA correspondente ao elemento HTML. Por exemplo, `<p>` `<image>`
* `resourceType`: especifique o tipo de recurso aplicável ao componente usado no Fragmento de experiência. Por exemplo, `wcm/foundation/components/text` é o resourceType do componente wcm `text`.
* `attributeMap`: Forneça informações adicionais ao componente, como se um componente de texto deve ser renderizado como `RichText` ou contém o `fileReference` de um componente de imagem.




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



Ao publicar os Fragmentos de experiência no Editor da Web, selecione o `Template` na lista suspensa da caixa de diálogo **Gerar fragmento de experiência** para exibir o mapeamento disponível para o modelo no campo **Mapeamento**. Se nenhum mapeamento personalizado estiver presente para um modelo, o mapeamento padrão será listado. Você pode usar o mapeamento padrão para publicar todo o tópico como um Fragmento de experiência.

Para obter mais detalhes, consulte [Publicar Fragmentos de Experiência](../user-guide/publish-experience-fragment.md).
