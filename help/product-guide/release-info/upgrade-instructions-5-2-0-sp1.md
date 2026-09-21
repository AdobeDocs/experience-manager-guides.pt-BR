---
title: Notas de versão | Instruções de atualização do Adobe Experience Manager Guides 5.2.0 Service Pack 1
description: Saiba mais sobre a matriz de compatibilidade e como atualizar para a versão 5.2.0 Service Pack 1 do Adobe Experience Manager Guides.
source-git-commit: b975fd2c2d79fb56f180484431af135d35eec750
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 4%
---
# Instruções de atualização do 5.2.0 Service Pack 1 (setembro de 2026)

Este artigo aborda as instruções de atualização e a matriz de compatibilidade da versão 5.2.0 Service Pack 1 do Adobe Experience Manager Guides.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão 5.2.0 do Service Pack 1](../release-info/whats-new-5-2-1.md).

Para obter a lista de problemas que foram corrigidos nesta versão, consulte [Problemas corrigidos na versão 5.2.0 Service Pack 1](../release-info/fixed-issues-5-2-0-sp1.md).

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com o Experience Manager Guides 5.2.0 Service Pack 1.

| Guias do AEM | Versão do AEM | Pacote de serviços |
| --- | --- | --- |
| 5.2.0 Service Pack 1 (UUID) | 6.5 LTS | 2 |
| 5.2.0 Service Pack 1 (UUID) | 6.5 | 24, 23, 22 |

Para obter mais detalhes, consulte a seção [Requisitos técnicos](../install-conf-guide/aemg-technical-requirements.md) no Guia de Instalação e Configuração no Local.


### Recursos do Java SDK

Use os recursos a seguir ao desenvolver plug-ins Java personalizados ou integrações com o Experience Manager Guides. Verifique se a versão do SDK corresponde à versão instalada do Experience Manager Guides.

| Versão | Versão do Java SDK | Maven Central | Referência da API Java |
|---|---|---|----|
| 5.2.0 Service Pack 1 (UUID) | 5.2.2 | [API do AEM Guides SDK 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/) | [Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) |

Para obter mais detalhes, consulte [Configurar e usar o JAR da API do repositório central Maven](https://experienceleague.adobe.com/pt-br/docs/experience-manager-guides/using/api-reference/introduction).


### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão | FMPS | FM |
| --- | --- | --- |
| 5.2.0 Service Pack 1 (UUID) | Compatível | 2026 ou superior |

### Conector de oxigênio

| Versão | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.2.0 Service Pack 1 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| Pacote de conteúdo dos componentes do Experience Manager Guides para Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

### Nova versão do modelo de site do AEM


| Guias do AEM | Versão do AEM | Versão dos componentes | Versão do site |
|---|---|---| ---|
| 5.2.0 UUID do Service Pack 1 | 6.5 LTS | guides-components.all-1.4.1 | ND |
| 5.2.0 UUID do Service Pack 1 | 6,5 | guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Pré-requisitos

Antes de iniciar o processo de atualização do Experience Manager Guides 5.2.0 Service Pack 1, verifique se você:

1. Atualização para o Experience Manager Guides versão 5.2.0.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.

## Caminho de atualização para o Experience Manager Guides 5.2.0 Service Pack 1

Você pode atualizar facilmente sua versão atual do Experience Manager Guides para a versão 5.2.0 Service Pack 1 no **AEM 6.5** ou **AEM 6.5 LTS**.

>[!IMPORTANT]
>
> - **Para AEM 6.5 LTS**: o Experience Manager Guides 5.2.0 Service Pack 1 é compatível somente com o AEM 6.5 LTS Service Pack 2.
> - **Para o AEM 6.5**: o Experience Manager Guides 5.2.0 Service Pack 1 é compatível somente com o AEM 6.5 Service Pack 24, 23 e 22.
> - Se você estiver usando o AEM 6.5 e planeja migrar para o AEM 6.5 LTS, conclua a atualização do AEM primeiro antes de prosseguir com a atualização do Experience Manager Guides 5.2.0. Para obter detalhes, consulte [Atualização para o Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/pt-br/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Antes de prosseguir com a atualização para a versão 5.2.0 Service Pack 1 do Experience Manager Guides, você deve considerar os seguintes pontos:

- Se você estiver usando a versão 5.2.0, é possível atualizar diretamente para a versão 5.2.0 Service Pack 1.
- Se você estiver usando a versão 5.0.0, 5.0.3, 5.1.0, 5.1.3 ou 5.1.4, é possível atualizar diretamente para a versão 5.2.0.
- Se você estiver usando a versão 4.6.3, 4.6.4, 5.0.x, é possível atualizar diretamente para a versão 5.1.0.
- Se você estiver usando a versão 4.6.0, 4.6.1, será necessário atualizar para a versão 4.6.3, 4.6.4 ou 5.0.0 antes de atualizar para a versão 5.1.0.
- Se você estiver usando a versão 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 ou 4.1.x, será necessário atualizar para a versão 4.4 antes de atualizar para a versão 5.1.0.
- Se você estiver usando a versão 4.0, será necessário atualizar para a versão 4.2 antes de atualizar para a versão 4.3.x.
- Se você estiver usando a versão 3.8.5, será necessário atualizar para a versão 4.0 antes de atualizar para a versão 4.2.
- Se você estiver usando uma versão anterior à 3.8.5, consulte a seção Atualizar Experience Manager Guides no guia de instalação específico do produto, disponível no [arquivo PDF de ajuda do Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

## Processo de atualização para o Experience Manager Guides 5.2.0 Service Pack 1

>[!IMPORTANT]
>
> O pós-processamento e a indexação podem levar algumas horas. É recomendável iniciar o processo de atualização fora do horário de pico.

1. Baixe o pacote da versão 5.2.0 Service Pack 1 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote de versão no qual deseja atualizar e aguarde até que o pacote seja instalado.
1. *(Opcional)* Atualize o plug-in do conector Oxygen lançado com a versão para a qual você está atualizando.
1. Limpe o cache do navegador após instalar o pacote.
1. Se você habilitou a configuração `Enable markup find and replace` para acessar o recurso Localizar e substituir na exibição de origem para conteúdo capturado anteriormente, será necessário reindexar o índice `guidesAssetLucene`. Para obter detalhes, exiba [Reindexação para Localizar e substituir](../install-conf-guide/custom-indexing-on-prem.md).







