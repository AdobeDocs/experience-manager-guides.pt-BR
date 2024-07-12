---
title: Incluir atributo @navtitle por padrão
description: Saiba como incluir o atributo @navtitle por padrão
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 1%

---

# Incluir atributo @navtitle por padrão {#id2115BC0J0XA}

É possível adicionar diferentes tipos de arquivos de referência em um mapa, por exemplo, tópico, referência, tarefa, mapas \(sub\) e assim por diante. A maioria desses arquivos oferece suporte ao atributo `@navtitle`. No entanto, poucos autores o usam de forma consistente. Se você quiser impor o uso do atributo `@navtitle` em todos os arquivos referenciados em um mapa, faça isso com uma configuração simples.

Uma vez habilitado, cada arquivo de referência adicionado em um mapa receberá automaticamente o atributo `@navtitle` adicionado às suas propriedades. O `@navtitle` também obterá o valor do elemento `title` do conteúdo referenciado.

Para incluir o atributo `@navtitle` por padrão nas propriedades dos arquivos de referência, execute as seguintes etapas:

1. Baixe o arquivo ui\_config.json.

   Você pode fazer essa alteração no nível Global ou em um perfil de nível de pasta. Dependendo de onde você deseja fazer essa alteração, é necessário baixar o respectivo arquivo ui\_config.json. Para obter mais informações sobre como baixar o arquivo ui\_config.json, consulte [Configurar e personalizar o Editor da Web de XML](conf-folder-level.md#id2065G300O5Z).

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
