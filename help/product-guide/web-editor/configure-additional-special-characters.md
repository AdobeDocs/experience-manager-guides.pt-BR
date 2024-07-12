---
title: Configurar caracteres especiais adicionais na barra de ferramentas do Editor da Web
description: Saiba como configurar caracteres especiais adicionais no editor da Web do AEM Guides.
feature: Web Editor
role: User
exl-id: 0fbc05a5-a6b0-4f6b-bbc4-8fca03581d90
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Como configurar caracteres especiais adicionais na barra de ferramentas do Editor da Web

Há uma opção de atalho na barra de ferramentas do editor da Web para permitir que o autor insira os caracteres especiais.
O mesmo pode ser visto na captura de tela abaixo:

![Caracteres Especiais](assets/special-chars.png)


Essa lista de caracteres pode ser configurada aqui. Se precisar adicionar mais caracteres a isso, siga as etapas abaixo:

+ Faça logon no AEM e abra o modo CRXDE Lite.

+ Crie o arquivo symbol.json no seguinte local: &#39;/apps/fmdita/xmleditor/&#39; (Você pode copiar o padrão de - local &#39;/libs/fmdita/clientlibs/clientlibs/xmleditor/symbols.json&#39;)

+ Adicione a definição de caractere especial no arquivo symbol.json como:

```
{
      "label": "Logical Symbols",
      "items": [
        {
          "name": "≥",
          "title": "Greater-Than or Equal To"
        },
        {
          "name": "≤",
          "title": "Smaller-Than or Equal To"
        }
      ]
}
```

A estrutura do arquivo symbol.json é explicada abaixo:

+ &quot;label&quot;: &quot;Logical Symbols&quot;: especifica a categoria dos caracteres especiais. No trecho, uma categoria com o nome &quot;Símbolo lógico&quot; é definida.

+ &quot;items&quot;: isso define a coleção de caracteres especiais na categoria.

+ &quot;name&quot;: &quot;≥&quot;, &quot;title&quot;: &quot;Greater-Than or Equal To&quot;: esta é a definição do caractere especial. Ela começa com o rótulo &quot;name&quot;, que não deve ser alterado. O nome é seguido pelo caractere especial. O &quot;título&quot; é o nome ou o título do caractere especial que aparece como a dica de ferramenta desse caractere especial.

É possível definir várias definições de caracteres especiais em uma categoria.

Isso adicionará outra categoria na caixa de diálogo de caracteres especiais:

![Categoria de Símbolo Especial](assets/special-char-category.png)

![Inserir caractere especial](assets/insert-special-char.png)

>[!MORELIKETHIS]
>
>+ [Guia de Instalação e Configuração](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-6/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)
