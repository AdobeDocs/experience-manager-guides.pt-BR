---
title: Como adicionar [!DNL Experience Manager Guides] ao seu [!DNL Experience Manager as a Cloud Service] ambiente
description: Saiba como adicionar [!DNL AEM Guides] ao seu [!DNL AEM as a Cloud Service] ambiente
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
TQID: https://experienceleague.adobe.com/lb5mjLR6M3pdFlsdQpwGXotEhbPeyetJ4zVwKV-J-Yg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 153
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] implantação do as a Cloud Service

Saiba como adicionar [!DNL Experience Manager Guides] ao seu ambiente [!DNL Experience Manager as a Cloud Service].


>[!NOTE]
>
> A partir da versão 2024.2.0, o Experience Manager Guides só estará disponível como um complemento automatizado para o Experience Manager as a Cloud Service. Se você usa implantações manuais para o Experience Manager Guides, remova a linha `<module>dox.installer</module> from file dox/pom.xml` da sua base de código do git gerenciado na nuvem antes de habilitar o Experience Manager Guides para o seu programa.

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
