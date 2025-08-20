---
title: Fazer upload de arquivos
description: Saiba como fazer upload de arquivos para o repositório do AEM e lidar com erros. Conhecer a interface do usuário do console de ativos, o aplicativo de desktop AEM, a assimilação de ativos em massa e usar o FrameMaker para upload em massa.
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
feature: Content Management
role: User
source-git-commit: 0259c0c0b7270d860198f17e6ea5f5829df038d5
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 1%

---

# Fazer upload de arquivos {#id176FF000JUI}

Provavelmente você teria um repositório de conteúdo DITA existente que gostaria de usar com o Adobe Experience Manager Guides. Para tal conteúdo existente, você pode usar qualquer uma das seguintes abordagens para fazer upload em massa de conteúdo para o repositório do Adobe Experience Manager.

>[!IMPORTANT]
>
> Exiba [Adicionar ativos digitais ao Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=pt-BR) para obter informações detalhadas sobre os métodos de carregamento de conteúdo com suporte no Adobe Experience Manager.

## Interface do usuário do console do Assets

Para [adicionar ativos digitais ao Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=pt-BR#filename-handling?lang=pt-BR#upload-assets) usando a interface de usuário do Console do Assets, selecione o ativo necessário na área de trabalho e arraste na interface de usuário do Adobe Experience Manager \(navegador da Web\) para a pasta de destino. Ao fazer upload de ativos, verifique se os nomes de arquivo não incluem caracteres não permitidos ou proibidos.

Para obter mais detalhes, exiba a seção [Manipulação de nome de arquivo e caracteres proibidos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=pt-BR#filename-handling) na documentação do Adobe Experience Manager.

## Aplicativo de desktop do Adobe Experience Manager

Use o aplicativo de desktop do Adobe Experience Manager se você for um profissional criativo e quiser gerenciar os ativos no desktop local. É possível abrir e editar esses ativos com seus aplicativos de desktop. Você também pode manter versões e compartilhar seus arquivos com outros usuários. Para obter mais detalhes, consulte [aplicativo de desktop do Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html?lang=pt-BR).

## Assimilador de ativos em massa

Se você tiver migrações em grande escala e assimilações ocasionais em massa, use o Assimilador de ativos em massa para fazer upload de conteúdo. Com essa ferramenta, você pode carregar conteúdo em massa de armazenamentos de dados compatíveis, como o Azure ou S3. Para obter mais detalhes, consulte [Assimilação de ativos em massa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=pt-BR#asset-bulk-ingestor).

## Usar o FrameMaker para upload em massa

O Adobe FrameMaker vem com um poderoso conector Adobe Experience Manager que permite carregar facilmente seu DITA existente e outros documentos do FrameMaker \(`.book` e `.fm`\) no Adobe Experience Manager. Você pode usar várias funcionalidades de upload de arquivos, como fazer upload de um único arquivo, fazer upload de uma pasta completa com ou sem dependências \(como referências de conteúdo, referências cruzadas e elementos gráficos\).

Para obter mais detalhes sobre como usar o recurso de carregamento em massa no FrameMaker, consulte a seção *Criar uma pasta do CRX e carregar arquivos* no Guia do Usuário do FrameMaker.

## Tratamento de erros ao fazer upload do conteúdo {#id201MI0I04Y4}

No caso de falha ao carregar um ou mais arquivos, um prompt é exibido no final do processo de upload com uma lista de arquivos que falharam ao carregar, como mostrado no trecho abaixo.

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Para obter mais detalhes sobre como os vários cenários de carregamento de arquivos funcionam, exiba [Gerenciar arquivos e pastas](authoring-file-management.md#).

Caso use uma ferramenta como o aplicativo de desktop do Adobe Experience Manager ou o Assimilador de ativos em massa, a ação a ser executada em um arquivo duplicado é controlada por uma configuração no servidor do Adobe Experience Manager. Entre em contato com o administrador do sistema para saber sobre essa configuração.

**Tópico pai:**&#x200B;[ Gerenciar conteúdo](authoring.md)
