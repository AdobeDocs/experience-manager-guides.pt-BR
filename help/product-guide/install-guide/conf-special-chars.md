---
title: Configurar caracteres especiais permitidos
description: Saiba como Configurar caracteres especiais permitidos
exl-id: 3dd7752e-0836-480a-b1e1-6fa2099d404f
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Configurar caracteres especiais permitidos {#id20CIL600035}

O Editor da Web permite inserir alguns caracteres especiais prontos para uso. Entretanto, é possível personalizar a lista de caracteres especiais que os autores podem inserir nos documentos. Se você personalizar a lista de caracteres especiais, ela substituirá o conjunto padrão de caracteres especiais. Somente os caracteres especiais adicionados em sua configuração são disponibilizados aos autores.

Execute as seguintes etapas para substituir a lista padrão de caracteres especiais:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. criar `symbols.json` arquivo no seguinte local:

   ```json
   /apps/fmdita/xmleditor/
   ```

1. Adicione a definição de caractere especial na `symbols.json` arquivar como:

   ```json
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


A estrutura do `symbols.json` O arquivo é explicado abaixo:

- `"label": "Arrows"`: Especifica a categoria dos caracteres especiais. No trecho, uma categoria com o nome `"Arrows"` está definido.
- `"items"`: isso define a coleção de caracteres especiais na categoria.
- `"name": "←", "title": "Left Arrow"`: esta é a definição do caractere especial. Ele começa com o `"name"` rótulo, que não deve ser alterado. O nome é seguido pelo caractere especial. A variável `"title"` é o nome ou o título do caractere especial que aparece como a dica de ferramenta desse caractere especial.

  É possível definir várias definições de caracteres especiais em uma categoria.


**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
