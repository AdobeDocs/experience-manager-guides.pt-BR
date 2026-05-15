---
title: Menus de contexto
description: Personalização de menus de contexto
role: User, Admin
exl-id: 25aa76dd-ef05-41ed-b980-14bbc1626059
TQID: https://experienceleague.adobe.com/TJyqos515-hGMn2S0fG4Nqs-kKz2MDF7cM40PSuZFMY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 154
ht-degree: 0%

---

# Personalização de menus de contexto

Os seguintes menus de contexto podem ser personalizados:

- `file_options`
controladoras:
   - Exibição de mapa: `ditamap_viewer_controller`
   - Painel do Repositório: `repository_panel_controller`
   - Painel Favoritos: `collection_tree_controller`
   - Links de Referência de Propriedades de Arquivo: `file_references_links_controller`
   - Painel de Pesquisa do Repositório: `repository_search_controller`
   - Painel do Esquema do Assunto: `subject_scheme_tree_controller`

- `folder_options`
controladoras:
   - Painel do Repositório: `repository_panel_controller`
   - Painel Favoritos: `collection_tree_controller`

- `collection_options`
controladoras:
   - Painel Favoritos: `collection_tree_controller`

- `map_view_options`
controladoras:
   - Exibição de mapa: `ditamap_viewer_controller`

- `baseline_panel_menu`
controladoras:
   - Painel da Linha de Base: `baseline_panel`

- `preset_item_menu`
controladoras:
   - Painel de Predefinição: `preset_panel`

Você também pode criar seu próprio menu de contexto definindo uma nova ID exclusiva.

Agora, cada menu de contexto tem um `controller id` associado a ele. Este controlador manipula a funcionalidade `on-event` para as várias opções do menu de contexto

Vejamos um exemplo para entender

```js title=customise_context_menu.js"
const loadDitaFile = (filePath, uuid) =>{
  return $.ajax({
    type: 'POST',
    url: '/bin/referencelistener',
    data: {
        operation: 'getdita',
        path: filePath,
        type: uuid ? 'UUID' : 'PATH',
        cache: false,
    },
  })
}

const fileOptions = {
    id: "file_options",
    contextMenuWidget: "repository_panel",
    view: {
            items: [
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Delete",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Edit",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    "displayName": "Download",
                    "data": {
                      "eventid": "downloadFile"
                    },
                    "icon": "downloadFromCloud",
                    "class": "menu-separator",         
                    target: {
                        key:"displayName",value: "Duplicate",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
            ]

    },

    controller: {
        downloadFile(){
            const path  = this.getValue('selectedItems')[0].path
            loadDitaFile(path).then((file) => {
              function download_file(name, contents) {
                const mime_type = "text/plain";
        
                const blob = new Blob([contents], {type: mime_type});
        
                const dlink = document.createElement('a');
                dlink.download = name;
                dlink.href = window.URL.createObjectURL(blob);
                dlink.onclick = function() {
                    // revokeObjectURL needs a delay to work properly
                    const that = this;
                    setTimeout(function() {
                        window.URL.revokeObjectURL(that.href);
                    }, 1500);
                };
        
                dlink.click();
                dlink.remove();
            }
            download_file(path,file.xml)
            });
          }
    }
}
```

Agora vamos entender o que esse código está fazendo.

1. `id` é usado para identificar o menu de contexto que queremos personalizar.
2. `contextMenuWidget` é usado para definir o `widget id` ou o `component` que chama o menu de contexto e manipula o `events`.

O restante permanece o mesmo, em que `view` é usado para definir os itens, `target` identifica onde substituir, anexar ou anexar a opção e o controlador `contextMenuWidget` manipula os eventos `on-click`.
