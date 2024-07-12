---
title: Configurar Regx para caracteres válidos de nome de arquivo
description: Saiba como configurar o Regx para caracteres válidos de nome de arquivo
exl-id: 05e9ca3c-28ff-4f82-8061-3d20307890ff
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Configurar Regx para caracteres válidos de nome de arquivo {#id214BD0550E8}

A partir da versão AEM Guides 3.8, como administrador, você pode definir uma lista de caracteres especiais válidos permitidos em nomes de arquivo. Em versões anteriores, os usuários podiam definir nomes de arquivos contendo caracteres especiais como `@`, `$`, `>` e muito mais. Esses caracteres especiais geravam problemas ao abrir tópicos do painel do mapa DITA ou clicar no link do tópico no índice, o que geralmente fazia com que a página não abrisse devido a caracteres especiais no URL.

Usando a configuração que permite definir um regx para caracteres de nome de arquivo válidos, você tem controle total sobre como os arquivos são nomeados internamente no sistema. Você pode definir uma lista de caracteres especiais permitidos nos nomes de arquivo. Por padrão, a configuração de nome de arquivo válido contém &quot;`a-z A-Z 0-9 - _`&quot;. Ao criar um novo arquivo, você pode ter qualquer caractere especial no título do arquivo, mas internamente ele será substituído por &quot;`-`&quot; no nome do arquivo. Por exemplo, você pode ter o título do arquivo como &quot;Introdução 1&quot; ou &quot;Introduction@1&quot;, o nome de arquivo correspondente gerado para ambos os casos seria &quot;Introdução-1&quot;.

Ao definir uma lista de caracteres válidos, lembre-se de que esses caracteres &quot;`*/:[\]|#%{}?&<>"/+`&quot; sempre serão substituídos por um &quot;`-`&quot;.

Se você não configurar a lista de caracteres especiais válida, o processo de criação de arquivo poderá fornecer resultados inesperados. Para evitar esses erros, é altamente recomendável fazer essa alteração de configuração.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar regex para caracteres válidos de nome de arquivo:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | O valor é um padrão regex. Ele deve ter três caracteres básicos e a lista deve começar com um hífen \(-\).<br> **Valor padrão**: \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> Semelhante à lista de caracteres de nome de arquivo válidos, você também pode especificar uma lista de caracteres de nome de arquivo válidos para a saída do site AEM. Para obter mais detalhes, consulte [Configurar nomes de arquivo válidos para saída do site AEM](conf-file-names-valid-regx-aem-site-output.md#).

**Tópico pai:**[ Configurar nomes de arquivo](conf-file-names.md)
