---
title: Configurar DITA-OT personalizado em  [!DNL AEM Guides]
description: Saiba como configurar o DITA-OT personalizado no  [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
feature: DITA-OT Configuration
TQID: https://experienceleague.adobe.com/EaU6rkZL-RBkkYDhKxHNkizIVSqNzEDd-TtFlJAmREw
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 0%

---

# Configurar o DITA-OT personalizado no [!DNL AEM Guides] para AEM

As etapas para adicionar um DITA-OT personalizado estão documentadas na seção _Usar plug-ins DITA-OT personalizados_ do _Guia de Instalação e Configuração_.

Em um alto nível, as etapas são:

+ Obtenha o DITA-OT básico
   + Se você quiser obter uma cópia do DITA-OT pronto para uso de [!DNL AEM Guides], baixe-a do caminho `/etc/fmdita/dita_resources/DITA-OT.zip`
   + Se você quiser obter uma versão diferente, baixe do [dita-ot repo](https://www.dita-ot.org/download)
+ Faça alterações no DITA-OT, como [adicionar novo plug-in](https://www.dita-ot.org/dev/topics/plugins-installing.html) ou personalizar plug-ins existentes (consulte o exemplo na seção de links relacionados abaixo)
+ Carregar `DITA-OT.zip` recebido para `/apps/<project-folder>/dita_resources` (criar uma pasta de projeto personalizada é uma abordagem recomendada)
+ Adicionar Perfil DITA por meio de **[!UICONTROL Ferramentas]** > **[!UICONTROL Guias]** > **[!UICONTROL Perfis DITA]** (use o caminho DITA-OT para onde o DITA-OT personalizado é carregado; consulte a captura de tela abaixo)
  ![Perfis DITA](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Personalizando amostras de plug-in DITA-OT](https://www.dita-ot.org/dev/topics/pdf-customization.html)
