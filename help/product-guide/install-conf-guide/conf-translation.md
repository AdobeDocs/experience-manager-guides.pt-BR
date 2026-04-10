---
title: Traduzir conteúdo
description: Saiba como traduzir conteúdo
feature: Translation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '1368'
ht-degree: 6%

---

# Traduzir conteúdo {#id181GB0400UI}

Automatize a tradução de conteúdo da página, ativos e conteúdo gerado pelo usuário para criar e manter sites multilíngues. Para automatizar fluxos de trabalho de tradução, você integra provedores de serviços de tradução ao AEM e cria projetos para traduzir o conteúdo em vários idiomas. O AEM permite fluxos de trabalho de tradução humana e de máquina.

- Tradução humana: o conteúdo é enviado para seu provedor de tradução e traduzido por tradutores profissionais. Quando concluído, o conteúdo traduzido é retornado e importado para o AEM. Quando seu provedor de tradução é integrado ao AEM, o conteúdo é trocado automaticamente entre o AEM e o provedor de tradução

- Tradução automática: o serviço de tradução automática traduz imediatamente seu conteúdo


As guias a seguir fornecem instruções para tradução de conteúdo com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Conecte o AEM com seu [provedor de serviços de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=pt-BR) e crie configurações da estrutura de integração de tradução.

1. Associe as páginas do seu idioma principal com o serviço de tradução e as configurações da estrutura.

1. Identifique o tipo de conteúdo [para traduzir](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=pt-BR).

1. [Prepare o conteúdo para tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=pt-BR) criando o idioma principal e as páginas raiz das cópias de idioma.

1. Crie [projetos de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=pt-BR) para coletar o conteúdo para traduzir e para preparar o processo de tradução.

1. Use os projetos de tradução para [gerenciar o processo de tradução de conteúdo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=pt-BR).


>[!TAB No local]

1. Conecte o AEM com seu [provedor de serviços de tradução](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) e crie [configurações da estrutura de integração de tradução](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Associe as páginas do seu idioma principal com o [serviço de tradução e configurações de estrutura](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identifique o tipo de conteúdo [para traduzir](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Prepare o conteúdo para tradução](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-prep.html) criando o idioma principal e as páginas raiz das cópias de idioma.

1. Crie [projetos de tradução](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-manage.html) para coletar o conteúdo para traduzir e para preparar o processo de tradução.

1. Use os projetos de tradução para [gerenciar o processo de tradução de conteúdo](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-manage.html).

>[!ENDTABS]

Quando seu provedor de serviços de tradução não fornece um conector para integração com o AEM, o AEM oferece suporte à exportação e importação manuais de conteúdo traduzido no formato XML.

>[!TIP]
>
> Consulte a seção *Tradução* no guia de práticas recomendadas para obter práticas recomendadas sobre a tradução de conteúdo.

## Configure a guia Tradução no painel de mapa DITA

As guias a seguir fornecem instruções para ocultar a guia Tradução no painel de mapa DITA com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração.
1. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar a guia tradução no painel de mapa:

   | PID | Chave de propriedade | Valor de propriedade |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Booleano\ ( true/ false\).<br> **Valor padrão**: `true` |

   >[!NOTE]
   >
   > Essa configuração é habilitada por padrão e a guia Translation não está disponível no painel de mapa.


>[!TAB No local]

A opção Ocultar guia Tradução não está habilitada por padrão e você precisa habilitá-la no configMgr.


1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.config.ConfigManager**.

1. Selecione a opção **Ocultar Guia de Tradução** para ocultar a guia de tradução no painel do mapa.

   >[!NOTE]
   >
   > Essa propriedade é desabilitada por padrão e a guia Tradução está disponível no painel de mapa.

1. Clique em **Salvar**.

>[!ENDTABS]


## Configurar o fluxo de trabalho de tradução baseado em componentes

Se o conector do fornecedor de tradução não suportar conteúdo DITA, o fluxo de trabalho de tradução baseado em componentes precisará ser ativado. Depois de ativado, o conteúdo traduzível é enviado como metadados de ativos. No entanto, o conector precisa ser compatível com a tradução de metadados de ativos para que esse fluxo de trabalho funcione.

As guias a seguir fornecem instruções para o fluxo de trabalho de tradução com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Com base no fluxo de trabalho de tradução usado na configuração, a opção de fluxo de trabalho de tradução baseado em componentes deve ser configurada. Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar o fluxo de trabalho de tradução baseado em componentes:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Booleano: <br> -   Se você estiver usando tradução humana, *Desabilite* \( `false`\) a opção **Fluxo de Trabalho de Tradução Baseado em Componentes**. <br> -   Se você estiver usando tradução automática, *Habilite \( `true`\)* a opção **Fluxo de Trabalho de Tradução Baseado em Componentes**. |

>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.config.ConfigManager**.

1. Configure a opção **Fluxo de trabalho de tradução DITA baseado em componentes** de acordo com sua configuração:

   - Se você estiver usando tradução humana, *Desabilite* a opção **Fluxo de Trabalho de Tradução Baseado em Componentes**.

   - Se você estiver usando tradução automática, *Habilite* a opção **Fluxo de Trabalho de Tradução Baseado em Componentes**.

   >[!NOTE]
   >
   > Se você estiver usando o conector de tradução, verifique se configurou o conector conforme descrito no tópico *[Configurando a estrutura de integração de tradução](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-tic.html)* na documentação do AEM.

1. Clique em **Salvar**.

>[!IMPORTANT]
>
> Depois de definir as configurações de tradução, defina a Configuração na nuvem apropriada nas pastas de idioma.

>[!ENDTABS]


## Configurar o fluxo de trabalho de tradução herdado

As guias a seguir fornecem instruções para configurar essa opção com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

>[!IMPORTANT]
>
> É recomendável usar o fluxo de trabalho de tradução mais recente, disponível no AEM Guides 2024.06.0 e posterior, para um desempenho aprimorado. No entanto, se você tiver ativado qualquer personalização no processo de tradução e ela for afetada pelo novo fluxo de trabalho, considere reverter para o fluxo de trabalho de tradução herdado como uma solução alternativa.

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar o fluxo de trabalho de tradução herdado:


| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `translation.workflow.version.legacy` | Booleano: <br> - Se você usar o fluxo de trabalho de tradução mais recente, *Desabilite* \( `false`\) a opção **Executar fluxo de trabalho de tradução herdado**.  <br> -   Se você usar a tradução herdada, *Habilite \( `true`\)* a opção **Executar fluxo de trabalho de tradução herdada**. <br> **Valor padrão**: falso |


>[!NOTE]
>
> Se você estiver usando o conector de tradução, verifique se configurou o conector conforme descrito no tópico *[Configurando a estrutura de integração de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=pt-BR)* na documentação do Adobe Experience Manager.

>[!IMPORTANT]
>
> Depois de definir as configurações de tradução, defina a Configuração na nuvem apropriada nas pastas de idioma.

>[!TAB No local]

>[!IMPORTANT]
> 
> É recomendável usar o fluxo de trabalho de tradução mais recente, disponível no AEM Guides 4.6.0 e posterior, para um desempenho aprimorado. No entanto, se você tiver ativado qualquer personalização no processo de tradução e ela for afetada pelo novo fluxo de trabalho, considere reverter para o fluxo de trabalho de tradução herdado como uma solução alternativa. Por padrão, a opção de fluxo de trabalho de tradução herdada está desativada.

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.config.ConfigManager**.

1. Configurar a opção de fluxo de trabalho de tradução herdada de acordo com sua configuração:

   - (*Padrão*) Se quiser usar o fluxo de trabalho de tradução mais recente, desabilite a opção **Executar fluxo de trabalho de tradução herdado**.
   - Se você quiser usar o fluxo de trabalho de tradução herdado, habilite a opção **Executar fluxo de trabalho de tradução herdado**.

1. Clique em **Salvar**.

>[!ENDTABS]

## Configurar pós-processamento de cópias de idioma temporárias

Quando você inicia o fluxo de trabalho de tradução, o sistema cria cópias temporárias de idioma do conteúdo original. Você pode optar por ativar ou desativar a operação de pós-processamento nesses arquivos temporários. Na operação de pós-processamento, as referências de entrada e saída dos arquivos são resolvidas, o estado do documento é definido, juntamente com outras operações. Se você habilitar o pós-processamento nesses arquivos temporários, o processo de tradução poderá levar mais tempo para ser concluído. Portanto, é recomendável manter a opção de pós-processamento desativada.

As guias a seguir fornecem instruções para configurar essa opção com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar o pós-processamento de cópias de idioma temporárias:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Booleano: <br> -   Se você não deseja executar a operação de pós-processamento nos arquivos temporários, *Desabilite* \( falso\) a opção **Cópias de idioma pós-processamento**.<br> -   Se você deseja executar a operação de pós-processamento nos arquivos temporários, *Habilite* \( true\) a opção **Cópias de idioma pós-processamento**.<br> **Valor padrão**: falso |

>[!TAB No local]

>[!NOTE]
>
> Por padrão, a opção pós-processamento de arquivos temporários está desativada.

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.config.ConfigManager**.

1. Configure a opção **Cópias de idioma pós-processamento** de acordo com sua configuração:

   - \(*Padrão*\) Se você não deseja executar a operação de pós-processamento nos arquivos temporários, *Desabilite* a opção **Cópias de idioma pós-processamento**.

   - Se você deseja executar a operação de pós-processamento nos arquivos temporários, *Habilite* a opção **Cópias de idioma pós-processamento**.

1. Clique em **Salvar**.

>[!ENDTABS]