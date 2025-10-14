---
title: Configurar Regx para caracteres válidos de nome de arquivo
description: Saiba como configurar o Regx para caracteres válidos de nome de arquivo
exl-id: 876dfc77-078f-4341-b99d-02a453d2e065
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---

# Configurar Regx para caracteres válidos de nome de arquivo {#id214BD0550E8}

A partir da versão AEM Guides 3.8, como administrador, você pode definir uma lista de caracteres especiais válidos permitidos em nomes de arquivo. Em versões anteriores, os usuários podiam definir nomes de arquivos contendo caracteres especiais como `@`, `$`, `>` e muito mais. Esses caracteres especiais resultavam em problemas ao abrir tópicos do Painel do mapa DITA ou clicar no link do tópico no índice, o que geralmente fazia com que a página não abrisse devido a caracteres especiais no URL.

Usando a configuração que permite definir um regx para caracteres de nome de arquivo válidos, você tem controle total sobre como os arquivos são nomeados internamente no sistema. Você pode definir uma lista de caracteres especiais permitidos nos nomes de arquivo. Por padrão, a configuração de nome de arquivo válido contém &quot;`a-z A-Z 0-9 - _`&quot;. Ao criar um novo arquivo, você pode ter qualquer caractere especial no título do arquivo, mas internamente ele será substituído por &quot;`-`&quot; no nome do arquivo. Por exemplo, você pode ter o título do arquivo como &quot;Introdução 1&quot; ou &quot;Introduction@1&quot;, o nome de arquivo correspondente gerado para ambos os casos seria &quot;Introdução-1&quot;.

Ao definir uma lista de caracteres válidos, lembre-se de que esses caracteres &quot;`*/:[\]|#%{}?&<>"/+`&quot; sempre serão substituídos por um &quot;`-`&quot;.

Se você não configurar a lista de caracteres especiais válida, o processo de criação de arquivo poderá fornecer resultados inesperados. Para evitar esses erros, é altamente recomendável fazer essa alteração de configuração imediatamente após atualizar sua build para a versão 3.8.

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
> Semelhante à lista de caracteres de nome de arquivo válidos, você também pode especificar uma lista de caracteres de nome de arquivo válidos para a saída do site AEM. Para obter mais detalhes, consulte [Configurar nomes de arquivo válidos para saída do site AEM](conf-file-names-valid-regx-aem-site-output.md#).

**Tópico pai:**&#x200B;[&#x200B; Configurar nomes de arquivo](conf-file-names.md)
