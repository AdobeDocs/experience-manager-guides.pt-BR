---
title: Configurar caracteres especiais permitidos
description: Saiba como Configurar caracteres especiais permitidos
exl-id: 7ff4305f-71bb-4155-b8e5-911cea6f0ad9
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Configurar caracteres especiais permitidos {#id20CIL600035}

O Editor da Web permite inserir alguns caracteres especiais prontos para uso. Entretanto, é possível personalizar a lista de caracteres especiais que os autores podem inserir nos documentos. Se você personalizar a lista de caracteres especiais, ela substituirá o conjunto padrão de caracteres especiais. Somente os caracteres especiais adicionados em sua configuração são disponibilizados aos autores.

Execute as seguintes etapas para substituir a lista padrão de caracteres especiais:

1. Crie o arquivo `symbols.json` no seguinte local no repositório Git da Cloud Manager:

   ```
   /apps/fmdita/xmleditor/
   ```

1. Adicione a definição de caractere especial no arquivo `symbols.json` como:

   ```
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


A estrutura do arquivo `symbols.json` é explicada abaixo:

- `"label": "Arrows"`: Especifica a categoria dos caracteres especiais. No trecho, uma categoria com o nome `"Arrows"` é definida.
- `"items"`: isso define a coleção de caracteres especiais na categoria.
- `"name": "←", "title": "Left Arrow"`: esta é a definição do caractere especial. Ela começa com o rótulo `"name"`, que não deve ser alterado. O nome é seguido pelo caractere especial. O `"title"` é o nome ou o título do caractere especial que aparece como a dica de ferramenta desse caractere especial.

  É possível definir várias definições de caracteres especiais em uma categoria.


**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
