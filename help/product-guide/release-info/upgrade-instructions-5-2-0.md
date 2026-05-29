---
title: Notas de versão | Instruções de atualização da versão 5.2.0 do Adobe Experience Manager Guides
description: Saiba mais sobre a matriz de compatibilidade e como atualizar para a versão 5.2.0 do Adobe Experience Manager Guides.
source-git-commit: 1dc529ba8913c30fba876f101c3b52474e8a71dd
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 4%

---

# Instruções de atualização da versão 5.2.0 (maio de 2026)

Este artigo aborda as instruções de atualização e a matriz de compatibilidade da versão 5.2.0 do Adobe Experience Manager Guides.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 5.2.0](../release-info/whats-new-5-2-0.md).

Para obter a lista de problemas que foram corrigidos nesta versão, consulte [Problemas corrigidos na versão 5.2.0](../release-info/fixed-issues-5-2-0.md).

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade para os aplicativos de software compatíveis com a versão Experience Manager Guides 5.2.0.

| Guias do AEM | Versão do AEM | Pacote de serviços |
| --- | --- | --- |
| 5.2.0 (UUID) | 6.5 LTS | 2 |
| 5.2.0 (UUID) | 6.5 | 24, 23, 22 |

Para obter mais detalhes, consulte a seção [Requisitos técnicos](../install-guide/download-install-technical-requirements.md) no Guia de Instalação e Configuração no Local.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão | FMPS | FM |
| --- | --- | --- |
| 5.2.0 (UUID) | Compatível | 2026 ou superior |

### Conector de oxigênio

| Versão | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.2.0 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| Pacote de conteúdo dos componentes do Experience Manager Guides para Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

### Nova versão do modelo de site do AEM


| Guias do AEM | Versão do AEM | Versão dos componentes | Versão do site |
|---|---|---| ---|
| UUID 5.2.0 | 6.5 LTS | guides-components.all-1.4.1 | ND |
| UUID 5.2.0 | 6,5 | guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Pré-requisitos

Antes de iniciar o processo de atualização do Experience Manager Guides 5.2.0, verifique se você tem:

1. Atualizado para o Experience Manager Guides versão 5.0.0, 5.0.3, 5.1.0, 5.1.3 ou 5.1.4.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.

## Caminho de atualização para o Experience Manager Guides 5.2.0

Você pode atualizar facilmente sua versão atual do Experience Manager Guides para a versão 5.2.0 no **AEM 6.5** ou **AEM 6.5 LTS**.

>[!IMPORTANT]
>
> - **Para o AEM 6.5 LTS**: o Experience Manager Guides 5.2.0 é compatível somente com o AEM 6.5 LTS Service Pack 2.
> - **Para o AEM 6.5**: o Experience Manager Guides 5.2.0 é compatível somente com o AEM 6.5 Service Pack 24, 23 e 22.
> - Se você estiver usando o AEM 6.5 e planeja migrar para o AEM 6.5 LTS, conclua a atualização do AEM primeiro antes de prosseguir com a atualização do Experience Manager Guides 5.2.0. Para obter detalhes, consulte [Atualização para o Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Antes de prosseguir com a atualização para a versão 5.2.0 do Experience Manager Guides, você deve considerar os seguintes pontos:

- Se você estiver usando a versão 5.0.0, 5.0.3, 5.1.0, 5.1.3 ou 5.1.4, é possível atualizar diretamente para a versão 5.2.0.
- Se você estiver usando a versão 4.6.3, 4.6.4, 5.0.x, é possível atualizar diretamente para a versão 5.1.0.
- Se você estiver usando a versão 4.6.0, 4.6.1, será necessário atualizar para a versão 4.6.3, 4.6.4 ou 5.0.0 antes de atualizar para a versão 5.1.0.
- Se você estiver usando a versão 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 ou 4.1.x, será necessário atualizar para a versão 4.4 antes de atualizar para a versão 5.1.0.
- Se você estiver usando a versão 4.0, será necessário atualizar para a versão 4.2 antes de atualizar para a versão 4.3.x.
- Se você estiver usando a versão 3.8.5, será necessário atualizar para a versão 4.0 antes de atualizar para a versão 4.2.
- Se você estiver usando uma versão anterior à 3.8.5, consulte a seção Atualizar Experience Manager Guides no guia de instalação específico do produto, disponível no [arquivo PDF de ajuda do Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

## Processo de atualização para o Experience Manager Guides 5.2.0

>[!IMPORTANT]
>
> O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

1. Baixe o pacote da versão 5.2.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote de versão no qual deseja atualizar e aguarde até que o pacote seja instalado.
1. *(Opcional)* Atualize o plug-in do conector Oxygen lançado com a versão para a qual você está atualizando.
1. Limpe o cache do navegador após instalar o pacote.
1. Se você habilitou a configuração `Enable markup find and replace` para acessar o recurso Localizar e substituir na exibição de origem para conteúdo capturado anteriormente, será necessário reindexar o índice `guidesAssetLucene`. Para obter detalhes, exiba [Reindexação para Localizar e substituir](../install-conf-guide/custom-indexing-on-prem.md).
1. Atualize a configuração do sistema para incorporar as novas configurações introduzidas na versão 5.2.0, garantindo o suporte para os seguintes aprimoramentos:


| Configurações adicionadas | Arquivo de configuração | Exibir rótulo da configuração | Nome da configuração |
|-----|-----|------|-----|
| Ativar ou desativar o novo editor | `com.adobe.fmdita.config.ConfigManager` | Ativar editor 2.0 | `enable.markup.editor` |
| Ativar ou desativar a Nova Linha de Base | `com.adobe.fmdita.config.ConfigManager` | Linha de base mais rápida (v2) | `enable.baseline.v2` |
| Ignorar propriedades de metadados para marcar uma versão como suja | `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | Ignorar propriedade de metadados para versão suja | `xmleditor.dirtychecker.ignoremetadata` |
| Recurso de localização e substituição na exibição do Source | `com.adobe.fmdita.config.ConfigManager` | Ativar localização e substituição de marcação | `enable.markup.findreplace` |
| Habilitar ou desabilitar o cancelamento de links de mesmo nível para a Linha de Base antiga | `com.adobe.fmdita.config.ConfigManager` | Ignorar links de mesmo nível para Linha de Base V1 | `guides.baseline.v1.skip.peer.links` |
| Habilite ou desabilite a inicialização de cópias de destino com conteúdo de origem no fluxo de trabalho de tradução. Isso é aplicável somente quando o fluxo de trabalho de tradução herdado está desativado.  | `com.adobe.fmdita.config.ConfigManager` | Inicializar cópia do idioma de destino com conteúdo de origem | `translation.workflow.propagate.source.content` |
| Limpeza da loja de referência | `com.adobe.fmdita.config.ConfigManager` | Exclusão da árvore de guias ativada | `btree.deletion.enabled` |
| Replicação de ativos DITA | `com.adobe.fmdita.config.ConfigManager` | Replicar ativos DITA | `publish.replicate` |
| Processamento de ativos | `com.adobe.fmdita.config.ConfigManager` | Habilitar o trabalho agendado de processamento de ativos do Guides | `enable.asset.processing.scheduler` |

Para obter informações detalhadas sobre essas definições de configuração, exiba [Atualizações de configuração](../install-conf-guide/configuration-on-prem.md).







