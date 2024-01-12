---
title: Fazer upload de arquivos
description: Saiba como fazer upload de arquivos para o repositório AEM e lidar com erros. Conhecer a interface do usuário do console de ativos, o aplicativo de desktop AEM, a assimilação de ativos em massa e usar o FrameMaker para upload em massa.
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
feature: Content Management
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 0%

---

# Fazer upload de arquivos {#id176FF000JUI}

Provavelmente, você teria um repositório de conteúdo DITA existente que gostaria de usar com os Guias do AEM. Para tal conteúdo existente, você pode usar qualquer uma das seguintes abordagens para fazer upload em massa do seu conteúdo para o repositório AEM:

>[!IMPORTANT]
>
> Consulte [Adicionar ativos digitais ao Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) para obter informações detalhadas sobre os métodos de upload de conteúdo compatíveis com o AEM.

## Interface do usuário do console de ativos

Você pode selecionar o conteúdo na sua área de trabalho e arrastar a interface de usuário AEM \(navegador da web\) para a pasta de destino. Para obter mais detalhes, consulte [Fazer upload de ativos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#upload-assets) na documentação do AEM.

## Aplicativo de desktop do AEM 

Use o aplicativo de desktop AEM se você for um profissional criativo e quiser gerenciar os ativos no desktop local. É possível abrir e editar esses ativos com seus aplicativos de desktop. Você também pode manter versões e compartilhar seus arquivos com outros usuários. Para obter mais detalhes, consulte [aplicativo de desktop AEM](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html).

## Assimilador de ativos em massa

Se você tiver migrações em grande escala e assimilações ocasionais em massa, use o Assimilador de ativos em massa para fazer upload de conteúdo. Com essa ferramenta, você pode carregar conteúdo em massa de armazenamentos de dados compatíveis, como o Azure ou S3. Para obter mais detalhes, consulte [Assimilador de ativos em massa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## Usar o FrameMaker para upload em massa

O Adobe FrameMaker vem com um poderoso conector AEM que permite carregar facilmente seu DITA existente e outros documentos do FrameMaker \(`.book` e `.fm`\) no AEM. Você pode usar várias funcionalidades de upload de arquivos, como fazer upload de um único arquivo, fazer upload de uma pasta completa com ou sem dependências \(como referências de conteúdo, referências cruzadas e elementos gráficos\).

Para obter mais detalhes sobre como usar o recurso de upload em massa no FrameMaker, consulte a seção *Criar uma pasta do CRX e fazer upload de arquivos* no Guia do usuário do FrameMaker.

## Tratamento de erros ao fazer upload do conteúdo {#id201MI0I04Y4}

No caso de falha ao fazer upload de um ou mais arquivos, um prompt é exibido no final do processo de upload com uma lista de arquivos que falharam no upload:

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Para obter mais detalhes sobre como os vários cenários de upload de arquivos, consulte [Upload de conteúdo DITA](authoring-file-management.md#).

Caso você use uma ferramenta como o aplicativo de desktop AEM ou o assimilador de ativos em massa, a ação a ser executada em um arquivo duplicado é controlada por uma configuração no servidor AEM. Entre em contato com o administrador do sistema para saber sobre essa configuração.

**Tópico pai:**[ Gerenciar conteúdo](authoring.md)
