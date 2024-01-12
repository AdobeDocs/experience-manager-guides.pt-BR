---
title: Traduzir conteúdo nas guias do AEM
description: Saiba como traduzir conteúdo
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
feature: Translation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 9%

---

# Traduzir conteúdo {#id181GB0400UI}

Automatize a tradução de conteúdo da página, ativos e conteúdo gerado pelo usuário para criar e manter sites multilíngues. Para automatizar workflows de tradução, você integra provedores de serviços de tradução ao AEM e cria projetos para traduzir o conteúdo em vários idiomas. O AEM permite workflows de tradução humana e de máquina.

- Tradução humana: o conteúdo é enviado para seu provedor de tradução e traduzido por tradutores profissionais. Quando concluído, o conteúdo traduzido é retornado e importado para o AEM. Quando seu provedor de tradução é integrado ao AEM, o conteúdo é trocado automaticamente entre o AEM e o provedor de tradução

- Tradução automática: o serviço de tradução automática traduz imediatamente seu conteúdo


A tradução de conteúdo envolve as seguintes etapas:

1. Conecte o AEM com seu [provedor de serviços de tradução](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) e criar [configurações da estrutura de integração de tradução](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Associe as páginas do seu idioma principal com a [serviço de tradução e configurações da estrutura](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identificar o tipo de [conteúdo a ser traduzido](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Prepare o conteúdo para tradução](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html) criando o idioma principal e as páginas raiz das cópias de idioma.

1. Criar [projetos de tradução](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) para coletar o conteúdo para traduzir e para preparar o processo de tradução.

1. Use os projetos de tradução para [gerenciar a tradução de conteúdo](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) processo.


Quando seu provedor de serviços de tradução não fornece um conector para integração com o AEM, o AEM oferece suporte à exportação e importação manuais de conteúdo traduzido no formato XML.

>[!TIP]
>
> Consulte a *Tradução* seção no Guia de práticas recomendadas para práticas recomendadas sobre a tradução de conteúdo.

## Configure a guia Tradução no painel de mapa DITA

A opção Ocultar guia Tradução não está habilitada por padrão e você precisa habilitá-la no configMgr. Para ocultar a guia Tradução no painel de mapa DITA, execute as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. Selecione o **Ocultar guia Tradução** para ocultar a guia tradução no painel do mapa.

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

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. Configure o **Fluxo de trabalho de tradução DITA com base em componentes** opção de acordo com sua configuração:

   - Se você estiver usando tradução humana, *Desativar* o **Fluxo de trabalho de tradução baseado em componentes** opção.

   - Se você estiver usando a tradução automática, *Ativar* o **Fluxo de trabalho de tradução baseado em componentes** opção.

   >[!NOTE]
   >
   > Se estiver usando o conector de tradução, verifique se você configurou o conector conforme descrito na seção *[Configuração da estrutura de integração de tradução](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html)* tópico na documentação do AEM.

1. Clique em **Salvar**.


>[!IMPORTANT]
>
> Depois de definir as configurações de tradução, defina a Configuração na nuvem apropriada nas pastas de idioma.

## Configurar pós-processamento de cópias de idioma temporárias

Quando você inicia o fluxo de trabalho de tradução, o sistema cria cópias temporárias de idioma do conteúdo original. Você pode optar por ativar ou desativar a operação de pós-processamento nesses arquivos temporários. Na operação de pós-processamento, as referências de entrada e saída dos arquivos são resolvidas, o estado do documento é definido, juntamente com outras operações. Se você habilitar o pós-processamento nesses arquivos temporários, o processo de tradução poderá levar mais tempo para ser concluído. Portanto, é recomendável manter a opção de pós-processamento desativada.

Por padrão, a opção pós-processamento de arquivos temporários está desativada. Você pode configurar essa opção executando as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. Configure o **Pós-processamento de cópias de idioma** opção de acordo com sua configuração:

   - \(*Padrão*\) Se você não quiser executar a operação de pós-processamento nos arquivos temporários, *Desativar* o **Pós-processamento de cópias de idioma** opção.

   - Se você quiser executar a operação de pós-processamento nos arquivos temporários, *Ativar* o **Pós-processamento de cópias de idioma** opção.

1. Clique em **Salvar**.
