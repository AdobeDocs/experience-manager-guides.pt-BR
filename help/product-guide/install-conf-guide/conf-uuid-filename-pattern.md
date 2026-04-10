---
title: Configurar padrão de nome de arquivo UUID
description: Saiba como configurar o padrão de nome de arquivo UUID
feature: Migration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Configurar padrão de nome de arquivo UUID

Ao importar conteúdo, não é necessário que os nomes de arquivo sejam baseados na UUID. Em um sistema que usa nomes de arquivo baseados em UUID, é obrigatório que todos os arquivos sejam referenciados usando seus UUIDs em vez de seus nomes de arquivo originais. Se um arquivo importado não tiver nomes de arquivos baseados em UUID, você poderá configurar o sistema para adicionar uma UUID à propriedade do arquivo. Essa UUID é então usada para se referir a esses arquivos, nos quais a UUID não é usada para nomear os arquivos.

## Etapas para configurar o padrão de nome de arquivo UUID

As guias a seguir fornecem instruções para configurar o padrão de nome de arquivo UUID com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar o padrão de nome de arquivo UUID:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Cadeia de caracteres especificando o regex do padrão de nome de arquivo UUID. <br> Se um arquivo não seguir o padrão especificado, uma UUID será adicionada à propriedade do arquivo e todas as referências ao arquivo serão atualizadas com a UUID atribuída ao arquivo. <br> **Valor padrão**: `"^GUID-(?<id>.*)"` |

>[!TAB No local]

Execute as seguintes etapas para verificar nomes de arquivo em relação a um padrão UUID e atribuir UUID a arquivos que não tenham uma UUID atribuída:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.fmdita.config.ConfigManager*.

1. Na propriedade **Padrões de Nome de Arquivo UUID**, especifique um padrão para verificar os nomes dos arquivos importados.

   Se um arquivo não seguir o padrão especificado, uma UUID será adicionada à propriedade do arquivo e todas as referências ao arquivo serão atualizadas com a UUID atribuída ao arquivo.

1. Selecione **Salvar**.

>[!ENDTABS]





