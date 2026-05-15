---
title: Incluir atributo @navtitle por padrão
description: Saiba como incluir o atributo @navtitle por padrão
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/h8rkQYPX4uJRWTdJKIHmdGrzbCIh--HtTrhsQ5QeuL8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 326
ht-degree: 0%

---

# Incluir atributo @navtitle por padrão {#id2115BC0J0XA}

É possível adicionar diferentes tipos de arquivos de referência em um mapa, por exemplo, tópico, referência, tarefa, mapas \(sub\) e assim por diante. A maioria desses arquivos oferece suporte ao atributo `@navtitle`. No entanto, poucos autores o usam de forma consistente. Se você quiser impor o uso do atributo `@navtitle` em todos os arquivos referenciados em um mapa, faça isso com uma configuração simples.

Uma vez habilitado, cada arquivo de referência adicionado em um mapa receberá automaticamente o atributo `@navtitle` adicionado às suas propriedades. O `@navtitle` também obterá o valor do elemento `title` do conteúdo referenciado.

Para incluir o atributo `@navtitle` por padrão nas propriedades dos arquivos de referência, execute as seguintes etapas:

1. Para baixar o arquivo de configuração da interface do usuário, faça logon no Adobe Experience Manager como administrador.

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Selecione a guia **Configuração do editor XML** e clique no ícone **Editar** na parte superior
1. Clique no ícone **Baixar** para baixar o arquivo ui\_config.json em seu sistema local.
1. Você pode fazer essa alteração no nível Global ou em um perfil de nível de pasta. Dependendo de onde você deseja fazer essa alteração, é necessário baixar o respectivo arquivo ui\_config.json. Para obter mais informações sobre como baixar o arquivo ui\_config.json, consulte [Configurar e personalizar o Editor da Web de XML](conf-folder-level.md#id2065G300O5Z).

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



**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](conf-web-editor.md)
