---
title: Configure o mapeamento baseado em JSON entre um tópico e um modelo de fragmento de conteúdo.
description: Saiba como configurar o mapeamento baseado em JSON entre um tópico e um modelo de fragmento de conteúdo.
exl-id: 438e2964-b9c7-462a-a68c-8031bd97911c
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/w1XQiP79ta2-huLRGIdevylhP7VCYvmmOQVpQgI7w4w
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 275
ht-degree: 0%

---

# Criar um mapeamento entre um tópico e um fragmento de conteúdo



O Adobe Experience Manager Guides permite criar um mapeamento baseado em JSON entre um tópico e um modelo de fragmento de conteúdo. Você pode usar o mapeamento baseado em JSON para publicar conteúdo presente em alguns ou todos os elementos de um tópico em um fragmento de conteúdo.

>[!NOTE]
> 
> Se estiver usando versões 4.6 ou posteriores, não será necessário criar esse mapeamento. Você pode arrastar os elementos de tópico para os campos presentes no modelo de fragmento de conteúdo.
> Saiba como [publicar fragmentos de conteúdo](../user-guide/publish-content-fragment.md).


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

Você pode publicar todo o tópico com o mapeamento padrão. Selecione o mapeamento `Full Topic` na caixa de diálogo suspensa **Gerar fragmento de conteúdo** e tenha o campo &quot;topicData&quot; no modelo de fragmento de conteúdo.
