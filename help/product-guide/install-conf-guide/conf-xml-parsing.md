---
title: Configurar entidade de análise XML para o Cloud Service e no local
description: Saiba como configurar a entidade de análise XML para o Cloud Service e no local
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e4019ae1e605bd26f7df676a4fab8c632fd8fa8e
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 1%
---
# Configurar limite de tamanho de entidade do analisador XML

O Experience Manager Guides permite configurar um limite no tamanho total da entidade que o analisador XML aceita durante a publicação. Isso ajuda a evitar problemas como ataques de expansão de entidade XML e processamento de cargas úteis grandes demais.

>[!NOTE]
>
>É possível configurar um limite no tamanho total da entidade aceito pelo analisador XML durante a publicação, reduzindo riscos como ataques de expansão de entidade XML e processamento de cargas úteis grandes demais. O controle de limite de tamanho de entidade difere entre o Java 21 e o Java 25; portanto, os ambientes que atualizam para o Java 25 são aconselhados a revisar e validar sua configuração para garantir que os workflows de publicação continuem a operar sem erros.

Essa configuração envolve duas propriedades relacionadas:

* **Aplicar Limite de Tamanho Total de Entidade do Analisador XML** (`dxml.publish.xml.apply.total.entity.size.limit`): Habilita ou desabilita a verificação de limite total de tamanho de entidade.
* **Limite de Tamanho Total da Entidade do Analisador XML** (`dxml.publish.xml.total.entity.size.limit`): especifica o valor (caracteres) JAXP `totalEntitySizeLimit` que é aplicado aos analisadores XML seguros quando o sinalizador de aplicação está habilitado.

As guias a seguir fornecem instruções para configurar essas propriedades com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService` | `dxml.publish.xml.apply.total.entity.size.limit` | **Valor padrão:** &quot;true&quot; |
   | `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService` | `dxml.publish.xml.total.entity.size.limit` | **Valor padrão:** &quot;50000000&quot; |

>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService*.

1. Defina as seguintes configurações de acordo com seus requisitos:

   * **Aplicar Limite de Tamanho Total de Entidade do Analisador XML** (`dxml.publish.xml.apply.total.entity.size.limit`): por padrão, essa configuração está desabilitada.
   * **Limite de Tamanho Total de Entidade do Analisador XML** (`dxml.publish.xml.total.entity.size.limit`): por padrão, esse valor está definido como `50000000` caracteres. Esta configuração só tem efeito quando a configuração **Aplicar Limite de Tamanho Total de Entidade** do Analisador XML está habilitada.

1. Selecione **Salvar**.

>[!ENDTABS]



