---
title: Configurar o Dispatcher
description: Saiba como configurar o Dispatcher
exl-id: 525de1c3-5a79-4d65-89b4-ca05ae660c2c
feature: Installation
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/RTgKeZZYjXP5ebOpTys9RL6-Q9IcPbkLZJ13ueRZwVI'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 4%
---
# Configurar o Dispatcher {#id213BCM0M05U}

Se você planeja usar uma instância do Dispatcher no AEM Author junto com o AEM Guides, será necessário executar as seguintes configurações adicionais para concluir a configuração:

>[!NOTE]
>
> O Dispatcher é a ferramenta de balanceamento de carga e/ou cache do Adobe Experience Manager. Para obter mais detalhes sobre como usar o Dispatcher, consulte [Visão geral do Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=en).

## Ativar AllowEncodedSlashes em URLs

Os URLs com barras codificadas não são ativados por padrão na configuração do AEM Dispatcher, mas, ao trabalhar no AEM Guides, é necessário ativar isso. Para fazer isso, você precisa definir o parâmetro AllowEncodedSlashes como On na configuração do Apache, conforme mostrado no seguinte snippet:

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## Configurar o arquivo mime.types para DITA

Ao usar uma Dispatcher com o AEM Guides, você deve garantir que os arquivos de mapa e tópico do DITA sejam renderizados como HTML para que os autores visualizem o conteúdo conforme esperado \(em vez de formato de texto bruto\).

Execute as seguintes etapas para atualizar o arquivo mime.types:

1. Conecte-se ao servidor do Dispatcher usando SSH e navegue até o arquivo httpd.conf.

1. Verifique o caminho do arquivo &quot;mime.types&quot;.

1. Abra o arquivo mime.types e procure por &quot; text/html&quot;. O mapeamento padrão para &quot; text/html&quot; é:

   `text/html html htm`

1. Atualize o mapeamento adicionando as extensões ditamap e dita como:

   `text/html html htm ditamap dita`

1. Salvar e fechar o arquivo.


Essa atualização de configuração garante que o mapa DITA e os arquivos de tópico renderizados pelo Dispatcher sejam mostrados como HTML na interface do usuário do Assets.

## Permitir URL de solicitação de Preferências do Usuário

Ao usar uma Dispatcher com o AEM Guides, se a instância do Autor tiver um dispatcher na frente, faça as duas alterações a seguir:

- Inclua o URL de solicitação POST em uma lista de permissões. Um exemplo de regra &quot; `/filters`&quot; é fornecido abaixo - Adicione esta regra ao arquivo de configurações do Dispatcher:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Verifique se o padrão de URL &quot; /libs/cq/security/userinfo.json&quot; não está armazenado em cache no Dispatcher do autor. Portanto, adicione uma regra \(como abaixo\) em author\_dispatcher.any

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Tópico pai:**[ Baixar e instalar](download-install.md)
