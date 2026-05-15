---
title: Configurar modelo de tópico DITA personalizado
description: Saiba como configurar um modelo de tópico DITA personalizado
exl-id: a9b2c479-7bf6-4c62-addd-fdfe74dc1f69
feature: Template Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/YGsNmqPAjBHtBEa-o53tns-h1DLRkTZNIq3PNbG8LNw
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 365
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

1. [Criar modelo de criação personalizado](conf-folder-level.md#id1917D0EG0HJ)

1. Adicione um modelo personalizado ao perfil global ou de nível de pasta, conforme explicado na seção [Configurar modelos de criação](conf-folder-level.md#id1889D0IL0Y4)


## Configurar caminho da pasta de modelo DITA personalizado {#id191LCF0095Z}

O AEM Guides permite configurar uma pasta para armazenar o mapa e os modelos DITA personalizados. Por padrão, os arquivos de modelo são armazenados na seguinte pasta no DAM:

`/content/dam/dita-templates/`

Para gerenciar arquivos de modelo de tópico e mapa, há pastas dedicadas para armazenar o tópico e os modelos de mapa. Por padrão, todos os modelos de tópico são armazenados em `/content/dam/dita-templates/topics`

pasta. Todos os modelos de mapa são armazenados na pasta `/content/dam/dita-templates/maps`.

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

1. Procure e clique no pacote *com.adobe.fmdita.config.ConfigManager*.

1. Na propriedade **Local dos Modelos**, especifique um local para armazenar modelos personalizados.

1. Clique em **Salvar**.


Se o local especificado existir no DAM, todos os modelos de mapa e tópico padrão serão copiados para essa pasta. Se o local não existir, a pasta será criada com todos os modelos de mapa e tópico padrão.

**Tópico pai:**&#x200B;[&#x200B; Configurar tópico e mapear modelos](conf-template-tags.md)
