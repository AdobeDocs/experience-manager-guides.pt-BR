---
sidebar_position: 2
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# Personalização de menus de contexto

Os seguintes menus de contexto podem ser personalizados:

- `file_options`
controladoras:
   - Exibição de mapa: `ditamap_viewer_controller`
   - Painel Repositório: `repository_panel_controller`
   - Painel Favoritos: `collection_tree_controller`
   - Links de referência de propriedades de arquivo: `file_references_links_controller`
   - Painel de pesquisa do repositório: `repository_search_controller`
   - Painel do esquema do assunto: `subject_scheme_tree_controller`

- `folder_options`
controladoras:
   - Painel Repositório: `repository_panel_controller`
   - Painel Favoritos: `collection_tree_controller`

- `collection_options`
controladoras:
   - Painel Favoritos: `collection_tree_controller`

- `map_view_options`
controladoras:
   - Exibição de mapa: `ditamap_viewer_controller`

- `baseline_panel_menu`
controladoras:
   - Painel da linha de base: `baseline_panel`

- `preset_item_menu`
controladoras:
   - Painel de predefinição: `preset_panel`

Você também pode criar seu próprio menu de contexto definindo uma nova ID exclusiva.

Agora, cada menu de contexto tem um `controller id` associada a ele. Esse controlador manipula o `on-event` funcionalidade para as várias opções do menu de contexto

Vejamos um exemplo para entender

```js title=customise_context_menu.js"
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
            const path  = this.model.selectedItem.path
            this.loader.loadDitaFile(path).then((file) => {
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
2. `contextMenuWidget` é usado para definir o `widget id` ou o `component` que chama o menu de contexto e lida com a `events`.

O resto permanece o mesmo, pelo que `view` é usado para definir os itens, `target` identifica onde substituir, anexar ou anexar a opção e o `contextMenuWidget` o controlador manipula o `on-click` eventos.
