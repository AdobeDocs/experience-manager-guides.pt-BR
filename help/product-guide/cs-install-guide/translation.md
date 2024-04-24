---
title: Traduzir conteúdo
description: Saiba como traduzir conteúdo
exl-id: 5af78233-343e-47ba-b60c-b7f4789e2406
feature: Translation
role: Admin
level: Experienced
source-git-commit: 4c7421391922d276ef82515fb4b1cbdc2397e4ce
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 11%

---

# Traduzir conteúdo {#id181GB0400UI}

Automatize a tradução de conteúdo da página, ativos e conteúdo gerado pelo usuário para criar e manter sites multilíngues. Para automatizar workflows de tradução, você integra provedores de serviços de tradução ao AEM e cria projetos para traduzir o conteúdo em vários idiomas. O AEM permite workflows de tradução humana e de máquina.

- Tradução humana: o conteúdo é enviado para seu provedor de tradução e traduzido por tradutores profissionais. Quando concluído, o conteúdo traduzido é retornado e importado para o AEM. Quando seu provedor de tradução é integrado ao AEM, o conteúdo é trocado automaticamente entre o AEM e o provedor de tradução

- Tradução automática: o serviço de tradução automática traduz imediatamente seu conteúdo


A tradução de conteúdo envolve as seguintes etapas:

1. Conecte o AEM com seu [provedor de serviços de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) e criar configurações da estrutura de integração de tradução.

1. Associe as páginas do seu idioma principal com o serviço de tradução e as configurações da estrutura.

1. Identificar o tipo de [conteúdo a ser traduzido](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=en).

1. [Prepare o conteúdo para tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en) criando o idioma principal e as páginas raiz das cópias de idioma.

1. Criar [projetos de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) para coletar o conteúdo para traduzir e para preparar o processo de tradução.

1. Use os projetos de tradução para [gerenciar a tradução de conteúdo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) processo.


Quando seu provedor de serviços de tradução não fornece um conector para integração com o AEM, o AEM oferece suporte à exportação e importação manuais de conteúdo traduzido no formato XML.

>[!TIP]
>
> Consulte a *Tradução* no guia de Práticas recomendadas para obter as práticas recomendadas sobre a tradução de conteúdo.

## Configure a guia Tradução no painel de mapa DITA

Para ocultar a guia Tradução no painel de mapa DITA, execute as seguintes etapas:

1. Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração.
1. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar a guia tradução no painel de mapa:

   | PID | Chave de propriedade | Valor de propriedade |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Booleano\\ ( true/ false\).<br> **Valor padrão**: `true` |

   >[!NOTE]
   >
   > Essa configuração é habilitada por padrão e a guia Translation não está disponível no painel de mapa.


## Configurar o fluxo de trabalho de tradução baseado em componentes

Se o conector do fornecedor de tradução não suportar conteúdo DITA, o fluxo de trabalho de tradução baseado em componentes precisará ser ativado. Depois de ativado, o conteúdo traduzível é enviado como metadados de ativos. No entanto, o conector precisa ser compatível com a tradução de metadados de ativos para que esse fluxo de trabalho funcione.

Com base no fluxo de trabalho de tradução usado na configuração, a opção de fluxo de trabalho de tradução baseado em componentes deve ser configurada. Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar o fluxo de trabalho de tradução baseado em componentes:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Booleano: <br> - Se você estiver usando tradução humana, então *Desativar* \( `false`\) o **Fluxo de trabalho de tradução baseado em componentes** opção. <br> - Se você estiver usando tradução automática, então *Habilitar \( `true`\)* o **Fluxo de trabalho de tradução baseado em componentes** opção. |

>[!NOTE]
>
> Se estiver usando o conector de tradução, verifique se você configurou o conector conforme descrito na seção *[Configuração da estrutura de integração de tradução](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en)* tópico na documentação do AEM.

>[!IMPORTANT]
>
> Depois de definir as configurações de tradução, defina a Configuração na nuvem apropriada nas pastas de idioma.

## Configurar pós-processamento de cópias de idioma temporárias

Quando você inicia o fluxo de trabalho de tradução, o sistema cria cópias temporárias de idioma do conteúdo original. Você pode optar por ativar ou desativar a operação de pós-processamento nesses arquivos temporários. Na operação de pós-processamento, as referências de entrada e saída dos arquivos são resolvidas, o estado do documento é definido, juntamente com outras operações. Se você habilitar o pós-processamento nesses arquivos temporários, o processo de tradução poderá levar mais tempo para ser concluído. Portanto, é recomendável manter a opção de pós-processamento desativada.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar o pós-processamento de cópias de idioma temporárias:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Booleano: <br> - Se você não quiser executar a operação de pós-processamento nos arquivos temporários, *Desativar* \( false\) o **Pós-processamento de cópias de idioma** opção.<br> - Se você quiser executar a operação de pós-processamento nos arquivos temporários, *Ativar* \( true\) o **Pós-processamento de cópias de idioma** opção.<br> **Valor padrão**: falso |

