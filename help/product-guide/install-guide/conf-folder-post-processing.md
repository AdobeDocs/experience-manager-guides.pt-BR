---
title: Configurar nomes de arquivo
description: Saiba como desativar o pós-processamento para uma pasta carregada no Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 532e7c562a233619a8c4b7cbdbaef44bc73eb4b2
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---


# Desativar pós-processamento para uma pasta

Por padrão, todos os ativos carregados são processados usando o fluxo de trabalho Atualizar ativo do DAM. Os Guias do Experience Manager executam um processamento adicional, chamado pós-processamento, como parte desse fluxo de trabalho. Isso também ajuda a gerar as UUIDs

Ao fazer upload de arquivos e pastas para o *Adobe Experience Manager Assets* também é possível desativar o pós-processamento e a geração de UUIDs.


Execute as seguintes etapas para desativar o pós-processamento em um determinado caminho ou ignorar o pós-processamento de uma pasta:


1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. Selecione o **Caminhos ignorados para pós-processamento** para ignorar uma pasta para pós-processamento.

   Valor da string para definir qualquer NODE_OPTIONS padrão (propriedade de vários valores, strings com caminho que omite `/` no final)

   **Valor padrão**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Essa propriedade é desabilitada por padrão e a guia Tradução está disponível no painel de mapa.

1. Selecione o **Caminhos habilitados para pós-processamento** para ativar um caminho para pós-processamento.

   Valor da string para definir qualquer NODE_OPTIONS padrão (propriedade de vários valores, strings com caminho que omite `/` no final)

   **Valor padrão**: `/content/dam/`

   >[!NOTE]
   >
   > Essa propriedade é desabilitada por padrão e a guia Tradução está disponível no painel de mapa.


1. Clique em **Salvar**.



## Regras para ativar ou desativar o pós-processamento

Por padrão, o pós-processamento é feito para cada caminho de pasta na pasta Experience Manager DAM. As configurações são aplicadas a qualquer pasta de acordo com as seguintes regras:

* Se o pai for ignorado para pós-processamento, mas a pasta filho estiver habilitada, o filho e todos os seus sucessores serão considerados habilitados.
* Se o pai estiver ativado para pós-processamento, mas o filho for ignorado, o filho e todos os seus sucessores serão considerados ignorados.
* Se o mesmo caminho de pasta existir nas configurações ignore.post.processing.paths e enabled.post.processing.paths, então ele será considerado ignorado para pós-processamento.
