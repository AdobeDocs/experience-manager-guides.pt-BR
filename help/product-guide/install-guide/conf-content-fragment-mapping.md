---
title: Configure o mapeamento baseado em JSON entre um tópico e um modelo de fragmento de conteúdo.
description: Saiba como configurar o mapeamento baseado em JSON entre um tópico e um modelo de fragmento de conteúdo.
exl-id: 21446bcb-e7df-4823-acc3-1fdc7473f0d1
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Criar um mapeamento entre um tópico e um fragmento de conteúdo

O AEM Guides fornece o recurso para criar um mapeamento baseado em JSON entre um tópico e um modelo de fragmento de conteúdo. Use esse mapeamento para publicar em um fragmento de conteúdo o conteúdo presente em alguns ou todos os elementos de um tópico.

1. Para baixar o *contentFragmentMapping.json*, faça logon no Adobe Experience Manager como administrador.
1. Selecione o link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione Guias na lista de ferramentas e selecione a **Pasta Perfis**.
1. Selecione o bloco **Perfil Global**.
1. Selecione a guia **Configuração do Editor XML** e selecione o ícone **Editar** na parte superior.
1. Selecione o ícone **Baixar** para baixar o arquivo *contentFragmentMapping.json* no sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.

1. Você precisa seguir as seguintes validações:

   1. Deve ser um arquivo JSON
   2. Ela deve conter uma matriz contendo pelo menos um objeto, e cada objeto deve conter o seguinte:


      `"name": string `

      `"mapping": array`

      Cada objeto de mapeamento deve conter o seguinte:

      `"modelField": string`

      `"xpath": string`

      `"outputType": string`
1. Salve o arquivo e faça upload dele.

Arquivo de exemplo:

```
[
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "topicData",
        "xpath": "/topic[1]/body[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Full Topic"
  },
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "heroImage",
        "xpath": "/topic[1]/body[1]/p[1]/image[1]",
        "outputType": "outerHTML"
      },
      {
        "modelField": "dataTable",
        "xpath": "/topic[1]/body[1]/table[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Sample Example with XPath"
  }
]
```

Você pode publicar todo o tópico com o mapeamento padrão. Selecione o mapeamento `Full Topic` na lista suspensa da caixa de diálogo **Publish Como fragmento de conteúdo** e tenha o campo &quot;topicData&quot; no modelo de fragmento de conteúdo.
