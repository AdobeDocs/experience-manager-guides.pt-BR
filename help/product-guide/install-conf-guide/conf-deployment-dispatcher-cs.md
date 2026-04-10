---
title: Configuração de implantação e dispatcher
description: Saiba mais sobre a configuração de implantação e dispatcher no Experience Manager Guides as a Cloud Service
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 3%

---

# Configuração de implantação e dispatcher

Este artigo fornece informações sobre como implantar o Experience Manager Guides as a Cloud Service e configurar o Dispatcher.

## Implantar o Experience Manager Guides as a Cloud Service

Você pode começar implantando o Experience Manager Guides por meio da Cloud Manager. Para implantar o módulo, siga as instruções mencionadas em [implantação do AEM Guides as a Cloud Service](../release-info/deploy-xml-on-aemaacs.md).

>[!NOTE]
>
> A partir da versão 2024.2.0, o Experience Manager Guides só estará disponível como um complemento automatizado para o Experience Manager as a Cloud Service. Se estiver usando versões de dezembro de 2023 ou anteriores, você poderá baixar o Adobe Experience Manager Guides do repositório do GitHub e instalá-lo. Se você usa implantações manuais para o Experience Manager Guides, remova a linha `<module>dox.installer</module> from file dox/pom.xml` na base de código do gerenciador de nuvem do Git antes de habilitar o Experience Manager Guides para seu programa.

Execute as seguintes etapas para implantar o módulo Experience Manager Guides:

1. Faça logon no [!UICONTROL Cloud Manager].

1. Edite o programa para o qual deseja configurar [!DNL Experience Manager Guides].

1. Mude para a guia **[!UICONTROL Soluções e complementos]**.

1. Na tabela **[!UICONTROL Soluções e Complementos]**, clique em **[!UICONTROL Assets]**.

1. Selecione **[!UICONTROL Guias]** e **[!UICONTROL Salvar]**.

O programa foi configurado com êxito para provisionamento automático da solução da Experience Manager Guides.

![Configurando a solução Experience Manager Guides](assets/addon-configuration.png)

>[!NOTE]
>
>Para instalar o [!DNL Experience Manager Guides] em qualquer ambiente no programa integrado, você deve executar o pipeline associado ao ambiente. Nenhuma configuração adicional é necessária em sua base de código Git CM para instalar o [!DNL Experience Manager Guides].


## Configurar dispatcher

O Dispatcher é a ferramenta de balanceamento de carga e/ou cache do Adobe Experience Manager. Para obter mais detalhes, consulte [Dispatcher na nuvem](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/disp-overview.html?lang=en).

1. Para migrar a configuração do Dispatcher do AMS para o Cloud Service, consulte [Migração da configuração do Dispatcher do AMS para o AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/ams-aem.html?lang=en).
1. Para obter detalhes sobre como configurar o dispatcher, consulte [Configuração do Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=pt-BR).

>[!NOTE]
>
> O AEM as a Cloud Service não oferece suporte ao Dispatcher para instância de autor.
