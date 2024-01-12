---
title: Incluir atributo @navtitle por padrão
description: Saiba como incluir o atributo @navtitle por padrão
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Incluir atributo @navtitle por padrão {#id2115BC0J0XA}

É possível adicionar diferentes tipos de arquivos de referência em um mapa, por exemplo, tópico, referência, tarefa, mapas \(sub\) e assim por diante. A maioria desses arquivos oferece suporte ao `@navtitle` atributo. No entanto, poucos autores o usam de forma consistente. Se quiser impor o uso do `@navtitle` em todos os arquivos referenciados em um mapa, é possível fazer isso com uma configuração simples.

Uma vez habilitado, cada arquivo de referência adicionado em um mapa receberá automaticamente a `@navtitle` atributo adicionado às suas propriedades. A variável `@navtitle` também obterá o valor do `title` elemento do conteúdo referenciado.

Para incluir `@navtitle` atributo por padrão nas propriedades dos arquivos de referência, execute as seguintes etapas:

1. Para baixar o arquivo de configuração da interface do usuário, faça logon no Adobe Experience Manager como administrador.

1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecionar **Guias** na lista de ferramentas e clique no botão **Perfis de pasta**.
1. Clique no link **Perfil global** bloco.
1. Selecione o **Configuração do editor XML** e clique em **Editar** ícone na parte superior
1. Clique em **Baixar** ícone para baixar o arquivo ui\_config.json no sistema local.
1. Você pode fazer essa alteração no nível Global ou em um perfil de nível de pasta. Dependendo de onde você deseja fazer essa alteração, é necessário baixar o respectivo arquivo ui\_config.json. Para obter mais informações sobre como baixar o arquivo ui\_config.json, consulte [Configurar e personalizar o editor da Web de XML](conf-folder-level.md#id2065G300O5Z).

1. Procure por `ditaAttributes` definição.

   A definição padrão de `ditaAttributes` é:

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Altere o `required` parâmetro como:

   ```
   "required": {"navtitle": true}
   ```

1. Salve o arquivo.

1. Faça upload do arquivo no perfil correspondente \(Global ou Folder\).


Com essa configuração, cada arquivo de referência adicionado a um mapa conterá a variável `@navtitle` atributo por padrão.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
