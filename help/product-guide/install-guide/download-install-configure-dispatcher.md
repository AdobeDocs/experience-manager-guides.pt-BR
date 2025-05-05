---
title: Configurar Dispatcher
description: Saiba como configurar o Dispatcher
exl-id: 525de1c3-5a79-4d65-89b4-ca05ae660c2c
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 3%

---

# Configurar Dispatcher {#id213BCM0M05U}

Se você planeja usar uma instância do autor do Dispatcher no AEM junto com o AEM Guides, é necessário executar as seguintes configurações adicionais para concluir a configuração:

>[!NOTE]
>
> O Dispatcher é a ferramenta de balanceamento de carga e/ou cache do Adobe Experience Manager. Para obter mais detalhes sobre como usar o Dispatcher, consulte [Visão geral do Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=en).

## Ativar AllowEncodedSlashes em URLs

Os URLs com barras codificadas não são ativados por padrão na configuração do Dispatcher do AEM, mas, ao trabalhar no AEM Guides, é necessário ativar isso. Para fazer isso, você precisa definir o parâmetro AllowEncodedSlashes como On na configuração do Apache, conforme mostrado no seguinte snippet:

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

**Tópico pai:**&#x200B;[ Baixar e instalar](download-install.md)
