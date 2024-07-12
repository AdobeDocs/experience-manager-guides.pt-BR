---
title: Configurar nomes de arquivo
description: Saiba como desativar o pós-processamento para uma pasta carregada no Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: ff6e1322-9655-42aa-b353-199c70c9de49
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Desativar pós-processamento para uma pasta

Por padrão, todos os ativos carregados são processados usando o fluxo de trabalho Atualizar ativo do DAM. O Experience Manager Guides executa um processamento adicional, chamado pós-processamento, como parte desse fluxo de trabalho. Isso também ajuda a gerar as UUIDs

Ao carregar seus arquivos e pastas para o servidor do *Adobe Experience Manager Assets*, você também pode desabilitar o pós-processamento e a geração de UUIDs.


Execute as seguintes etapas para desativar o pós-processamento em um determinado caminho ou ignorar o pós-processamento de uma pasta:


1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.config.ConfigManager**.

1. Selecione a opção **Caminhos ignorados para processamento Post** para ignorar uma pasta para pós-processamento.

   Valor da cadeia de caracteres para definir qualquer NODE_OPTIONS padrão (propriedade de vários valores, cadeias de caracteres com caminho que omite `/` no final)

   **Valor Padrão**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Essa propriedade é desabilitada por padrão e a guia Tradução está disponível no painel de mapa.

1. Selecione a opção **Caminhos habilitados para processamento Post** para habilitar um caminho para pós-processamento.

   Valor da cadeia de caracteres para definir qualquer NODE_OPTIONS padrão (propriedade de vários valores, cadeias de caracteres com caminho que omite `/` no final)

   **Valor Padrão**: `/content/dam/`

   >[!NOTE]
   >
   > Essa propriedade é desabilitada por padrão e a guia Tradução está disponível no painel de mapa.


1. Clique em **Salvar**.



## Regras para ativar ou desativar o pós-processamento

Por padrão, o pós-processamento é feito para cada caminho de pasta na pasta Experience Manager DAM. As configurações são aplicadas a qualquer pasta de acordo com as seguintes regras:

* Se o pai for ignorado para pós-processamento, mas a pasta filho estiver habilitada, o filho e todos os seus sucessores serão considerados habilitados.
* Se o pai estiver ativado para pós-processamento, mas o filho for ignorado, o filho e todos os seus sucessores serão considerados ignorados.
* Se o mesmo caminho de pasta existir nas configurações ignore.post.processing.paths e enabled.post.processing.paths, então ele será considerado ignorado para pós-processamento.
