---
title: Traduzir conteúdo no AEM Guides
description: Saiba como traduzir conteúdo
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
feature: Translation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 7%

---

# Traduzir conteúdo {#id181GB0400UI}

Automatize a tradução de conteúdo da página, ativos e conteúdo gerado pelo usuário para criar e manter sites multilíngues. Para automatizar fluxos de trabalho de tradução, você integra provedores de serviços de tradução ao AEM e cria projetos para traduzir o conteúdo em vários idiomas. O AEM permite fluxos de trabalho de tradução humana e de máquina.

- Tradução humana: o conteúdo é enviado para seu provedor de tradução e traduzido por tradutores profissionais. Quando concluído, o conteúdo traduzido é retornado e importado para o AEM. Quando seu provedor de tradução é integrado ao AEM, o conteúdo é trocado automaticamente entre o AEM e o provedor de tradução

- Tradução automática: o serviço de tradução automática traduz imediatamente seu conteúdo


A tradução de conteúdo envolve as seguintes etapas:

1. Conecte o AEM com seu [provedor de serviços de tradução](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) e crie [configurações da estrutura de integração de tradução](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Associe as páginas do seu idioma principal com o [serviço de tradução e configurações de estrutura](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identifique o tipo de conteúdo [para traduzir](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Prepare o conteúdo para tradução](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-prep.html) criando o idioma principal e as páginas raiz das cópias de idioma.

1. Crie [projetos de tradução](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-manage.html) para coletar o conteúdo para traduzir e para preparar o processo de tradução.

1. Use os projetos de tradução para [gerenciar o processo de tradução de conteúdo](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/tc-manage.html).


Quando seu provedor de serviços de tradução não fornece um conector para integração com o AEM, o AEM oferece suporte à exportação e importação manuais de conteúdo traduzido no formato XML.

>[!TIP]
>
> Consulte a seção *Tradução* no guia de práticas recomendadas para obter práticas recomendadas sobre a tradução de conteúdo.

## Configure a guia Tradução no painel de mapa DITA

A opção Ocultar guia Tradução não está habilitada por padrão e você precisa habilitá-la no configMgr. Para ocultar a guia Tradução no painel de mapa DITA, execute as seguintes etapas:

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

## Configurar o fluxo de trabalho de tradução baseado em componentes

Se o conector do fornecedor de tradução não suportar conteúdo DITA, o fluxo de trabalho de tradução baseado em componentes precisará ser ativado. Depois de ativado, o conteúdo traduzível é enviado como metadados de ativos. No entanto, o conector precisa ser compatível com a tradução de metadados de ativos para que esse fluxo de trabalho funcione.

Com base no fluxo de trabalho de tradução usado na configuração, a opção de fluxo de trabalho de tradução baseado em componentes deve ser configurada da seguinte maneira:

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

## Configurar o fluxo de trabalho de tradução herdado

>[!IMPORTANT]
> 
> É recomendável usar o fluxo de trabalho de tradução mais recente, disponível no AEM Guides 4.6.0 e posterior, para um desempenho aprimorado. No entanto, se você tiver ativado qualquer personalização no processo de tradução e ela for afetada pelo novo fluxo de trabalho, considere reverter para o fluxo de trabalho de tradução herdado como uma solução alternativa.



Por padrão, a opção de fluxo de trabalho de tradução herdada está desativada. Você pode configurar essa opção executando as seguintes etapas:

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

## Configurar comportamento de tradução pela primeira vez

Por padrão, quando você executa uma tradução pela primeira vez, arquivos XML vazios são criados para o idioma de destino. Esses arquivos são traduzidos somente após a aprovação. Para controlar esse comportamento, você pode habilitar a configuração `Initialize destination language copy with source content` usando estas etapas:

>[!NOTE]
>
> Essa configuração é aplicável somente quando o fluxo de trabalho de tradução herdado está desativado.

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.config.ConfigManager**.

1. Selecione a configuração `Initialize destination language copy with source content`.

   - Quando ativado, uma cópia sem controle de versão contendo o conteúdo original é criada a partir da cópia de trabalho, em vez de gerar arquivos XML vazios durante a primeira tradução.
   - (*Padrão*) Quando desabilitado, o comportamento padrão se aplica e arquivos XML vazios são criados para o idioma de destino durante a primeira tradução.

1. Clique em **Salvar**.





<!---

This was added for 2406 CS IG

## Configure the legacy translation workflow 

It is recommended that you use the latest translation workflow, which provides enhanced performance. However, you can configure the legacy translation workflow if necessary.

Based on the translation workflow used in your setup, provide the following (property) details to configure the legacy translation workflow: the component-based translation workflow option should be configured as follows:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ! Add the syntax of http as given in previous config

    Note: Configure htttp code as given in previous sample
    

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.



1.  Configure the **Run legacy translation workflow** option as per your setup:

    -   If you use the latest translation workflow, then *Disable* \( `false`\) the **Run legacy translation workflow** option. The latest translation workflow is enabled by default. <br> 

    -   If you use the legacy translation, then *Enable \( `true`\)* the **Run legacy translation workflow** option.

1.  Click **Save**.


--->


## Configurar pós-processamento de cópias de idioma temporárias

Quando você inicia o fluxo de trabalho de tradução, o sistema cria cópias temporárias de idioma do conteúdo original. Você pode optar por ativar ou desativar a operação de pós-processamento nesses arquivos temporários. Na operação de pós-processamento, as referências de entrada e saída dos arquivos são resolvidas, o estado do documento é definido, juntamente com outras operações. Se você habilitar o pós-processamento nesses arquivos temporários, o processo de tradução poderá levar mais tempo para ser concluído. Portanto, é recomendável manter a opção de pós-processamento desativada.

Por padrão, a opção pós-processamento de arquivos temporários está desativada. Você pode configurar essa opção executando as seguintes etapas:

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
