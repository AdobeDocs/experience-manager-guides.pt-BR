---
title: Configurar Regx para caracteres válidos de nome de arquivo
description: Saiba como configurar o Regx para caracteres válidos de nome de arquivo
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 0%

---

# Configurar Regx para caracteres válidos de nome de arquivo {#id214BD0550E8}

A partir da versão AEM Guides 3.8, como Administrador, você poderá definir uma lista de caracteres especiais válidos permitidos em nomes de arquivo. Em versões anteriores, os usuários podiam definir nomes de arquivos contendo caracteres especiais como `@`, `$`, `>` e muito mais. Esses caracteres especiais geravam problemas ao abrir tópicos do painel do mapa DITA ou clicar no link do tópico no índice, o que geralmente fazia com que a página não abrisse devido a caracteres especiais no URL.

Usando a configuração que permite definir um regx para caracteres de nome de arquivo válidos, você tem controle total sobre como os arquivos são nomeados internamente no sistema. Você pode definir uma lista de caracteres especiais permitidos nos nomes de arquivo. Por padrão, a configuração de nome de arquivo válido contém &quot;`a-z A-Z 0-9 - _`&quot;. Ao criar um novo arquivo, você pode ter qualquer caractere especial no título do arquivo, mas internamente ele será substituído por &quot;`-`&quot; no nome do arquivo. Por exemplo, você pode ter o título do arquivo como &quot;Introdução 1&quot; ou &quot;Introduction@1&quot;, o nome de arquivo correspondente gerado para ambos os casos seria &quot;Introdução-1&quot;.

Ao definir uma lista de caracteres válidos, lembre-se de que esses caracteres &quot;`*/:[\]|#%{}?&<>"/+`&quot; sempre serão substituídos por um &quot;`-`&quot;.

Se você não configurar a lista de caracteres especiais válida, o processo de criação de arquivo poderá fornecer resultados inesperados. Para evitar esses erros, é altamente recomendável fazer essa alteração de configuração.

As guias a seguir fornecem instruções para configurar Regx para caracteres de nome de arquivo válidos com base na configuração do Experience Manager Guides: Cloud Service ou No local.


>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar regex para caracteres válidos de nome de arquivo:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | O valor é um padrão regex. Ele deve ter três caracteres básicos e a lista deve começar com um hífen \(-\).<br> **Valor padrão**: \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> Semelhante à lista de caracteres de nome de arquivo válidos, você também pode especificar uma lista de caracteres de nome de arquivo válidos para a saída do AEM Site. Para obter mais detalhes, consulte [Configurar nomes de arquivo válidos para a saída do site do AEM](conf-file-names-valid-regx-aem-site-output.md#).

>[!TAB No local]

Para configurar regx para caracteres \(ou permitidos\) válidos em nomes de arquivos, execute as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote *com.adobe.fmdita.config.ConfigManager*.

1. Na propriedade **Regex para Caracteres Válidos**, verifique se a propriedade está definida como \[-a-zA-Z0-9\_\]. Você pode adicionar mais caracteres a essa lista, no entanto, ela deve ter esses caracteres básicos e a lista deve começar com um hífen &quot;-&quot;.

   >[!NOTE]
   >
   > Essa propriedade se aplica somente aos nomes de arquivo, e não aos nomes de pastas.

1. Clique em **Salvar**.


>[!NOTE]
>
> Semelhante à lista de caracteres de nome de arquivo válidos, você também pode especificar uma lista de caracteres de nome de arquivo válidos para a saída do AEM Site. Para obter mais detalhes, consulte [Configurar nomes de arquivo válidos para a saída do site do AEM](conf-file-names-valid-regx-aem-site-output.md#).

>[!ENDTABS]
