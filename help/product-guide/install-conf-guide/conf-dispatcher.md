---
title: Configurar o Dispatcher
description: Saiba como configurar o Dispatcher
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 5%

---

# Configurar o Dispatcher {#id213BCM0M05U}

Se você planeja usar uma instância do Dispatcher no AEM Author junto com o AEM Guides, será necessário executar as seguintes configurações adicionais para concluir a configuração:

>[!NOTE]
>
> O Dispatcher é a ferramenta de balanceamento de carga e/ou cache do Adobe Experience Manager. Para obter mais detalhes sobre como usar o Dispatcher, consulte [Visão geral do Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=pt-BR).

## Ativar AllowEncodedSlashes em URLs

Os URLs com barras codificadas não são ativados por padrão na configuração do AEM Dispatcher, mas, ao trabalhar no AEM Guides, é necessário ativar isso. Para fazer isso, você precisa definir o parâmetro `AllowEncodedSlashes` como **Ligado** na configuração do Apache, conforme mostrado no seguinte trecho:

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

Execute as seguintes etapas para atualizar o arquivo `mime.types`:

1. Conecte-se ao servidor do Dispatcher usando SSH e navegue até o arquivo `httpd.conf`.

1. Verifique o caminho do arquivo `mime.types`.

1. Abra o arquivo `mime.types` e procure por &quot; text/html&quot;. O mapeamento padrão para &quot; text/html&quot; é:

   `text/html html htm`

1. Atualize o mapeamento adicionando as extensões ditamap e dita como:

   `text/html html htm ditamap dita`

1. Salvar e fechar o arquivo.


Essa atualização de configuração garante que o mapa DITA e os arquivos de tópico renderizados pelo Dispatcher sejam mostrados como HTML na interface do usuário do Assets.

## Permitir URL de solicitação de Preferências do Usuário

Ao usar uma Dispatcher com o AEM Guides, se a instância do Autor tiver um dispatcher na frente, faça as duas alterações a seguir:

- Inclua o URL de solicitação POST em uma lista de permissões. Um exemplo de regra `/filters` é fornecido abaixo: Adicione esta regra ao arquivo de configurações do Dispatcher:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Certifique-se de que o padrão de URL `/libs/cq/security/userinfo.json` não esteja armazenado em cache no Dispatcher do Autor, portanto, adicione uma regra `\(like below\)` em `author\_dispatcher.any`

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

