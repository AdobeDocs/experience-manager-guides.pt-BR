---
title: Traduzir conteúdo
description: Saiba como traduzir conteúdo
exl-id: 5af78233-343e-47ba-b60c-b7f4789e2406
feature: Translation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/WjrAoZplwWbFYxySm-faIIda81AWTYnqhvbdsRk8tjU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 877
ht-degree: 8%

---

# Traduzir conteúdo {#id181GB0400UI}

Automatize a tradução de conteúdo da página, ativos e conteúdo gerado pelo usuário para criar e manter sites multilíngues. Para automatizar fluxos de trabalho de tradução, você integra provedores de serviços de tradução ao AEM e cria projetos para traduzir o conteúdo em vários idiomas. O AEM permite fluxos de trabalho de tradução humana e de máquina.

- Tradução humana: o conteúdo é enviado para seu provedor de tradução e traduzido por tradutores profissionais. Quando concluído, o conteúdo traduzido é retornado e importado para o AEM. Quando seu provedor de tradução é integrado ao AEM, o conteúdo é trocado automaticamente entre o AEM e o provedor de tradução

- Tradução automática: o serviço de tradução automática traduz imediatamente seu conteúdo


A tradução de conteúdo envolve as seguintes etapas:

1. Conecte o AEM com seu [provedor de serviços de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=pt-BR) e crie configurações da estrutura de integração de tradução.

1. Associe as páginas do seu idioma principal com o serviço de tradução e as configurações da estrutura.

1. Identifique o tipo de conteúdo [para traduzir](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=pt-BR).

1. [Prepare o conteúdo para tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=pt-BR) criando o idioma principal e as páginas raiz das cópias de idioma.

1. Crie [projetos de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=pt-BR) para coletar o conteúdo para traduzir e para preparar o processo de tradução.

1. Use os projetos de tradução para [gerenciar o processo de tradução de conteúdo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=pt-BR).


Quando seu provedor de serviços de tradução não fornece um conector para integração com o AEM, o AEM oferece suporte à exportação e importação manuais de conteúdo traduzido no formato XML.

>[!TIP]
>
> Consulte a seção *Tradução* no guia de práticas recomendadas para obter práticas recomendadas sobre a tradução de conteúdo.

## Configure a guia Tradução no painel de mapa DITA

Para ocultar a guia Tradução no painel de mapa DITA, execute as seguintes etapas:

1. Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração.
1. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar a guia tradução no painel de mapa:

   | PID | Chave de propriedade | Valor de propriedade |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Booleano\ ( true/ false\).<br> **Valor padrão**: `true` |

   >[!NOTE]
   >
   > Essa configuração é habilitada por padrão e a guia Translation não está disponível no painel de mapa.


## Configurar o fluxo de trabalho de tradução baseado em componentes

Se o conector do fornecedor de tradução não suportar conteúdo DITA, o fluxo de trabalho de tradução baseado em componentes precisará ser ativado. Depois de ativado, o conteúdo traduzível é enviado como metadados de ativos. No entanto, o conector precisa ser compatível com a tradução de metadados de ativos para que esse fluxo de trabalho funcione.

Com base no fluxo de trabalho de tradução usado na configuração, a opção de fluxo de trabalho de tradução baseado em componentes deve ser configurada. Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar o fluxo de trabalho de tradução baseado em componentes:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Booleano: <br> - Se estiver usando tradução humana, *Desabilite* \( `false`\) a opção **Fluxo de Trabalho de Tradução Baseado em Componentes**. <br> - Se você estiver usando tradução automática, *Habilite \( `true`\)* a opção **Fluxo de Trabalho de Tradução Baseado em Componentes**. |



## Configurar o fluxo de trabalho de tradução herdado

>[!IMPORTANT]
>
> É recomendável usar o fluxo de trabalho de tradução mais recente, disponível no AEM Guides 2024.06.0 e posterior, para um desempenho aprimorado. No entanto, se você tiver ativado qualquer personalização no processo de tradução e ela for afetada pelo novo fluxo de trabalho, considere reverter para o fluxo de trabalho de tradução herdado como uma solução alternativa.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar o fluxo de trabalho de tradução herdado:


| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `translation.workflow.version.legacy` | Booleano: <br> - Se você usar o fluxo de trabalho de tradução mais recente, *Desabilite* \( `false`\) a opção **Executar fluxo de trabalho de tradução herdado**.  <br> - Se você usar a tradução herdada, *Habilite \( `true`\)* a opção **Executar fluxo de trabalho de tradução herdada**. <br> **Valor padrão**: falso |




>[!NOTE]
>
> Se você estiver usando o conector de tradução, verifique se configurou o conector conforme descrito no tópico *[Configurando a estrutura de integração de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=pt-BR)* na documentação do Adobe Experience Manager.

>[!IMPORTANT]
>
> Depois de definir as configurações de tradução, defina a Configuração na nuvem apropriada nas pastas de idioma.

## Configurar pós-processamento de cópias de idioma temporárias

Quando você inicia o fluxo de trabalho de tradução, o sistema cria cópias temporárias de idioma do conteúdo original. Você pode optar por ativar ou desativar a operação de pós-processamento nesses arquivos temporários. Na operação de pós-processamento, as referências de entrada e saída dos arquivos são resolvidas, o estado do documento é definido, juntamente com outras operações. Se você habilitar o pós-processamento nesses arquivos temporários, o processo de tradução poderá levar mais tempo para ser concluído. Portanto, é recomendável manter a opção de pós-processamento desativada.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar o pós-processamento de cópias de idioma temporárias:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Booleano: <br> - Se você não quiser executar a operação de pós-processamento nos arquivos temporários, *Desabilite* \( falso\) a opção **Cópias de idioma pós-processamento**.<br> - Se você deseja executar a operação de pós-processamento nos arquivos temporários, *Habilite* \( true\) a opção **Cópias de idioma pós-processamento**.<br> **Valor padrão**: falso |

