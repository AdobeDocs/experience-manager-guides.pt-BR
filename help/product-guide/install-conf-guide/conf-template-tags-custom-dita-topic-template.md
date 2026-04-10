---
title: Configurar modelo de tópico DITA personalizado
description: Saiba como configurar um modelo de tópico DITA personalizado
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 2%

---

# Configurar modelo de tópico DITA personalizado {#id16A7G0O02TD}

O AEM Guides vem com os seguintes modelos de tópico DITA:

- Tópico

- Tarefa

- Conceito

- Referência

- Glossário

- Resolução de problemas

- Em branco


Você pode usar qualquer um desses modelos para criar modelos de tópicos de acordo com seus requisitos de criação. O modelo DITA em branco não contém nenhuma estrutura ou elementos como os outros modelos. Você pode usar o modelo em branco como base caso seu modelo seja altamente personalizado e não se baseie em nenhum modelo de tópico DITA regular.

Para personalizar o modelo de tópico DITA e usá-lo para criação, é necessário executar as três tarefas principais a seguir:

1. *\(Opcional\)* [Configurar caminho de pasta de modelo DITA personalizado](#id191LCF0095Z)

1. [Criar modelo de criação personalizado](conf-profiles.md#id1917D0EG0HJ)

1. Adicione um modelo personalizado ao perfil global ou de nível de pasta, conforme explicado na seção [Configurar modelos de criação](conf-profiles.md#id1889D0IL0Y4)


## Configurar caminho da pasta de modelo DITA personalizado {#id191LCF0095Z}

O AEM Guides permite configurar uma pasta para armazenar o mapa e os modelos DITA personalizados. Por padrão, os arquivos de modelo são armazenados na seguinte pasta no DAM:

`/content/dam/dita-templates/`

Para gerenciar arquivos de modelo de tópico e mapa, há pastas dedicadas para armazenar o tópico e os modelos de mapa. Por padrão, todos os modelos de tópico são armazenados em `/content/dam/dita-templates/topics`

pasta. Todos os modelos de mapa são armazenados na pasta `/content/dam/dita-templates/maps`.

Como administrador, você pode optar por criar modelos de mapa ou tópico personalizados na pasta padrão ou criar sua própria pasta para armazenar modelos personalizados. Se você planeja usar a pasta padrão, ignore esse processo.

As guias a seguir fornecem instruções para configurar o caminho de pasta do modelo DITA personalizado com base na configuração do Experience Manager Guides: Cloud Service ou no local.


>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar uma pasta para seus modelos de tópico DITA personalizados:

>[!IMPORTANT]
>
> Você pode ignorar esse processo se quiser usar a pasta padrão para armazenar modelos personalizados.

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Especifique um local para armazenar modelos personalizados.<br> Se o local especificado existir no DAM, todos os modelos de mapa e tópico padrão serão copiados para essa pasta. Se o local não existir, a pasta será criada com todos os modelos de mapa e tópico padrão. |

>[!TAB No local]

Para configurar uma pasta para seus modelos de tópico DITA personalizados, execute as seguintes etapas:

>[!IMPORTANT]
>
> Você pode ignorar esse processo se quiser usar a pasta padrão para armazenar modelos personalizados.

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote *com.adobe.fmdita.config.ConfigManager*.

1. Na propriedade **Local dos Modelos**, especifique um local para armazenar modelos personalizados.

1. Clique em **Salvar**.


Se o local especificado existir no DAM, todos os modelos de mapa e tópico padrão serão copiados para essa pasta. Se o local não existir, a pasta será criada com todos os modelos de mapa e tópico padrão.


>[!ENDTABS]


**Tópico pai:**[ Configurar tópico e mapear modelos](conf-template-tags.md)
