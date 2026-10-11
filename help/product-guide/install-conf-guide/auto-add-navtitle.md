---
title: Incluir atributo @navtitle por padrão
description: Saiba como incluir o atributo @navtitle por padrão
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 80784efb-e897-47cc-a10a-4050236b0fad
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 1%
---
# Incluir atributo @navtitle por padrão {#id2115BC0J0XA}

É possível adicionar diferentes tipos de arquivos de referência em um mapa, por exemplo, tópico, referência, tarefa, mapas \(sub\) e assim por diante. A maioria desses arquivos oferece suporte ao atributo `@navtitle`. No entanto, poucos autores o usam de forma consistente. Se você quiser impor o uso do atributo `@navtitle` em todos os arquivos referenciados em um mapa, faça isso com uma configuração simples.

Uma vez habilitado, cada arquivo de referência adicionado em um mapa receberá automaticamente o atributo `@navtitle` adicionado às suas propriedades. O `@navtitle` também obterá o valor do elemento `title` do conteúdo referenciado.

As guias a seguir fornecem instruções para incluir o atributo `@navtitle` por padrão nas propriedades dos arquivos de referência com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Para baixar o arquivo de configuração da interface do usuário, faça logon no Adobe Experience Manager como administrador.
1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Selecione a guia **Configuração do editor XML** e clique no ícone **Editar** na parte superior
1. Clique no ícone **Baixar** para baixar o arquivo ui\_config.json em seu sistema local.
1. Você pode fazer essa alteração no nível Global ou em um perfil de nível de pasta. Dependendo de onde você deseja fazer essa alteração, é necessário baixar o respectivo arquivo ui\_config.json. Para obter mais informações sobre como baixar o arquivo ui\_config.json, consulte [Configurar e personalizar o Editor da Web de XML](conf-profiles.md#id2065G300O5Z).

1. Procure a definição `ditaAttributes`.

   A definição padrão de `ditaAttributes` é:

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Altere o parâmetro `required` conforme mostrado abaixo:

   ```
   "required": {"navtitle": true}
   ```

   Quando definido como `true`, o botão **Atualizar atributo de título de navegação** está habilitado para aparecer na barra de ferramentas do Editor. Quando definido como `false` ou deixado em branco, o botão permanece oculto no Editor.
1. Salve o arquivo.

1. Faça upload do arquivo no perfil correspondente \(Global ou Folder\).


Com essa configuração, cada arquivo de referência adicionado a um mapa conterá o atributo `@navtitle` por padrão.

>[!TAB No local]

1. Baixe o arquivo ui\_config.json.

   Você pode fazer essa alteração no nível Global ou em um perfil de nível de pasta. Dependendo de onde você deseja fazer essa alteração, é necessário baixar o respectivo arquivo ui\_config.json. Para obter mais informações sobre como baixar o arquivo ui\_config.json, consulte [Configurar e personalizar o Editor da Web de XML](conf-profiles.md#id2065G300O5Z).

1. Procure a definição `ditaAttributes`.

   A definição padrão de `ditaAttributes` é:

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Alterar o parâmetro `required` como:

   ```json
   "required": {"navtitle": true}
   ```

1. Salve o arquivo.

1. Faça upload do arquivo no perfil correspondente \(Global ou Folder\).


Com essa configuração, cada arquivo de referência adicionado a um mapa conterá o atributo `@navtitle` por padrão.

>[!ENDTABS]

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor](customize-overview.md)
