---
title: Como adicionar [!DNL Experience Manager Guides] ao seu [!DNL Experience Manager as a Cloud Service] ambiente
description: Saiba como adicionar [!DNL AEM Guides] ao seu [!DNL AEM as a Cloud Service] ambiente
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] implantação as a Cloud Service

Saiba como adicionar [!DNL Experience Manager Guides] ao seu [!DNL Experience Manager as a Cloud Service] ambiente.


>[!NOTE]
>
> A partir da versão 2024.2.0, os Guias do Experience Manager estarão disponíveis apenas como um complemento automatizado para o Experience Manager as a Cloud Service. Se você usar implantações manuais para os Guias do Experience Manager, remova a linha `<module>dox.installer</module> from file dox/pom.xml` na nuvem, gerencie a base de código do git antes de habilitar os Guias do Experience Manager para o seu programa.

1. Fazer logon em [!UICONTROL Cloud Manager].

1. Edite o programa para o qual deseja configurar [!DNL Experience Manager Guides].

1. Alternar para **[!UICONTROL Soluções e complementos]** guia.

1. No **[!UICONTROL Soluções e complementos]** tabela, clique em **[!UICONTROL Assets]**.

1. Selecionar **[!UICONTROL Guias]** e selecione **[!UICONTROL Salvar]**.

O programa foi configurado com êxito para provisionamento automático da solução de Guias do Experience Manager.

![Configuração da solução Experience Manager Guides](assets/addon-configuration.png)

>[!NOTE]
>
>Para instalar [!DNL Experience Manager Guides] em qualquer ambiente no programa integrado, você deve executar o pipeline associado ao ambiente. Nenhuma configuração adicional é necessária na base de código Git do CM para instalar o [!DNL Experience Manager Guides].
