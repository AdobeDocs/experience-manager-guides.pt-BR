---
title: Configurar o DITA-OT personalizado no [!DNL AEM Guides]
description: Saiba como configurar o DITA-OT personalizado no [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
feature: DITA-OT Configuration
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Configurar o DITA-OT personalizado no [!DNL AEM Guides] para AEM

As etapas para adicionar um DITA-OT personalizado estão documentadas na seção _Usar plug-ins personalizados do DITA-OT_ do _Guia de instalação e configuração_.

Em um alto nível, as etapas são:

+ Obtenha o DITA-OT básico
   + Se quiser obter uma cópia do DITA-OT pronto para uso em [!DNL AEM Guides], baixe-o do caminho `/etc/fmdita/dita_resources/DITA-OT.zip`
   + Se quiser obter uma versão diferente, baixe em [dita-to repo](https://www.dita-ot.org/download)
+ Faça alterações no DITA-OT como [adicionar novo plug-in](https://www.dita-ot.org/dev/topics/plugins-installing.html)ou personalizar plug-ins existentes (consulte o exemplo na seção links relacionados abaixo)
+ Carregar `DITA-OT.zip` recebido para `/apps/<project-folder>/dita_resources` (criar uma pasta de projeto personalizada é uma abordagem recomendada)
+ Adicionar perfil DITA por meio de **[!UICONTROL Ferramentas]** > **[!UICONTROL Guias]** > **[!UICONTROL Perfis DITA]** (use o caminho DITA-OT onde o DITA-OT personalizado é carregado; consulte a captura de tela abaixo)
  ![Perfis DITA](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Personalização de amostras de plug-in DITA-OT](https://www.dita-ot.org/dev/topics/pdf-customization.html)
