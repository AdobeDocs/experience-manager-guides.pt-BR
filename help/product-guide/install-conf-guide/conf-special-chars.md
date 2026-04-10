---
title: Configurar caracteres especiais permitidos
description: Saiba como Configurar caracteres especiais permitidos
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# Configurar caracteres especiais permitidos {#id20CIL600035}

O Editor da Web permite inserir alguns caracteres especiais prontos para uso. Entretanto, é possível personalizar a lista de caracteres especiais que os autores podem inserir nos documentos. Se você personalizar a lista de caracteres especiais, ela substituirá o conjunto padrão de caracteres especiais. Somente os caracteres especiais adicionados em sua configuração são disponibilizados aos autores.

As guias a seguir fornecem instruções para substituir a lista padrão de caracteres especiais com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

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

>[!TAB No local]

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. criar arquivo `symbols.json` no seguinte local:

   ```json
   /apps/fmdita/xmleditor/
   ```

1. Adicione a definição de caractere especial no arquivo `symbols.json` como:

   ```json
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

>[!ENDTABS]

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](customize-overview.md)
