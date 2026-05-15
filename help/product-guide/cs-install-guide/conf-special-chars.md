---
title: Configurar caracteres especiais permitidos
description: Saiba como Configurar caracteres especiais permitidos
exl-id: 7ff4305f-71bb-4155-b8e5-911cea6f0ad9
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/4E8kj37-4mj6StL4NBMzoebW6XgyfNV5e5emGg3EX8c
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 208
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


**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](conf-web-editor.md)
