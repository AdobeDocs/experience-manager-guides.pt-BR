---
title: Configurar nomes de arquivo
description: Saiba como desativar o pós-processamento para uma pasta carregada no Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: eaf974f4-c804-4392-b1f3-f4f24dd441f7
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bfc6cec48b5e3a50b472e97f456a06d2a32bb8d2
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 0%
---
# Desativar pós-processamento para uma pasta

>[!NOTE]
>
>A partir da versão 2027.01.0 para Cloud Service e da versão 5.4 para No local do Experience Manager Guides, o recurso do painel de Mapa será descontinuado para novos clientes. No entanto, ela permanecerá ativada para clientes existentes que já a estão usando. Se desejar desativar o painel Mapa, entre em contato com a equipe de Sucesso do cliente. É recomendável usar o console Mapa para gerenciamento e publicação de mapas a partir de agora.

Por padrão, todos os ativos carregados são processados usando o fluxo de trabalho Atualizar ativo do DAM. O Experience Manager Guides executa um processamento adicional, chamado pós-processamento, como parte desse fluxo de trabalho. Isso também ajuda a gerar as UUIDs

Ao carregar seus arquivos e pastas para o servidor do *Adobe Experience Manager Assets*, você também pode desabilitar o pós-processamento e a geração de UUIDs.

As guias a seguir fornecem instruções para desativar o pós-processamento de uma pasta com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para desativar o pós-processamento em um determinado caminho ou ignorar o pós-processamento de uma pasta:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valor da cadeia de caracteres para definir qualquer NODE_OPTIONS padrão (propriedade com vários valores, cadeias de caracteres com caminho que omitem `/` no final) <br> **Valor Padrão**: `/content/dam/projects/translation_output` |
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valor da cadeia de caracteres para definir qualquer NODE_OPTIONS padrão (propriedade com vários valores, cadeias de caracteres com caminho que omitem `/` no final) <br> **Valor Padrão**: `/content/dam` |

>[!TAB No local]

Execute as seguintes etapas para desativar o pós-processamento em um determinado caminho ou ignorar o pós-processamento de uma pasta:


1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.config.ConfigManager**.

1. Selecione a opção **Caminhos ignorados para pós-processamento** para ignorar uma pasta para pós-processamento.

   Valor da cadeia de caracteres para definir qualquer NODE_OPTIONS padrão (propriedade de vários valores, cadeias de caracteres com caminho que omite `/` no final)

   **Valor Padrão**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Essa propriedade é desabilitada por padrão e a guia Tradução está disponível no painel de mapa.

1. Selecione a opção **Caminhos habilitados para pós-processamento** para habilitar um caminho para pós-processamento.

   Valor da cadeia de caracteres para definir qualquer NODE_OPTIONS padrão (propriedade de vários valores, cadeias de caracteres com caminho que omite `/` no final)

   **Valor Padrão**: `/content/dam/`

   >[!NOTE]
   >
   > Essa propriedade é desabilitada por padrão e a guia Tradução está disponível no painel de mapa.


1. Clique em **Salvar**.

>[!ENDTABS]

## Regras para ativar ou desativar o pós-processamento

Por padrão, o pós-processamento é feito para cada caminho de pasta na pasta do Experience Manager DAM. As configurações são aplicadas a qualquer pasta de acordo com as seguintes regras:

* Se o pai for ignorado para pós-processamento, mas a pasta filho estiver habilitada, o filho e todos os seus sucessores serão considerados habilitados.
* Se o pai estiver ativado para pós-processamento, mas o filho for ignorado, o filho e todos os seus sucessores serão considerados ignorados.
* Se o mesmo caminho de pasta existir nas configurações ignore.post.processing.paths e enabled.post.processing.paths, então ele será considerado ignorado para pós-processamento.
