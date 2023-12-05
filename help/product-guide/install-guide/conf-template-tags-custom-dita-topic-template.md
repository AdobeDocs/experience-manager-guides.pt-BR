---
title: Configurar modelo de tópico DITA personalizado
description: Saiba como configurar um modelo de tópico DITA personalizado
exl-id: a9b2c479-7bf6-4c62-addd-fdfe74dc1f69
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# Configurar modelo de tópico DITA personalizado {#id16A7G0O02TD}

Os Guias do AEM vêm com os seguintes modelos de tópico DITA:

- Tópico

- Tarefa

- Conceito

- Referência

- Glossário

- Resolução de problemas

- Em branco


Você pode usar qualquer um desses modelos para criar modelos de tópicos de acordo com seus requisitos de criação. O modelo DITA em branco não contém nenhuma estrutura ou elementos como os outros modelos. Você pode usar o modelo em branco como base caso seu modelo seja altamente personalizado e não se baseie em nenhum modelo de tópico DITA regular.

Para personalizar o modelo de tópico DITA e usá-lo para criação, é necessário executar as três tarefas principais a seguir:

1. *\(Opcional\)* [Configurar caminho da pasta de modelo DITA personalizado](#id191LCF0095Z)

1. [Criar modelo de criação personalizado](conf-folder-level.md#id1917D0EG0HJ)

1. Adicione um modelo personalizado ao perfil global ou de nível de pasta, conforme explicado na seção [Configurar modelos de criação](conf-folder-level.md#id1889D0IL0Y4) seção


## Configurar caminho da pasta de modelo DITA personalizado {#id191LCF0095Z}

O Guia AEM permite configurar uma pasta para armazenar o mapa e os modelos DITA personalizados. Por padrão, os arquivos de modelo são armazenados na seguinte pasta no DAM:

`/content/dam/dita-templates/`

Para gerenciar arquivos de modelo de tópico e mapa, há pastas dedicadas para armazenar o tópico e os modelos de mapa. Por padrão, todos os modelos de tópico são armazenados no `/content/dam/dita-templates/topics`

pasta. Todos os modelos de mapa são armazenados no `/content/dam/dita-templates/maps` pasta.

Como administrador, você pode optar por criar modelos de mapa ou tópico personalizados na pasta padrão ou criar sua própria pasta para armazenar modelos personalizados. Se você planeja usar a pasta padrão, ignore esse processo.

Para configurar uma pasta para seus modelos de tópico DITA personalizados, execute as seguintes etapas:

>[!IMPORTANT]
>
> Você pode ignorar esse processo se quiser usar a pasta padrão para armazenar modelos personalizados.

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link *com.adobe.fmdita.config.ConfigManager* pacote.

1. No **Localização dos modelos** especifique um local para armazenar modelos personalizados.

1. Clique em **Salvar**.


Se o local especificado existir no DAM, todos os modelos de mapa e tópico padrão serão copiados para essa pasta. Se o local não existir, a pasta será criada com todos os modelos de mapa e tópico padrão.

**Tópico pai:**[ Configurar tópico e modelos de mapa](conf-template-tags.md)
