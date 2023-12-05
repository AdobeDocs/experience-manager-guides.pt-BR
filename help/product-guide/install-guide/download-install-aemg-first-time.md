---
title: Baixe e instale os Guias do AEM pela primeira vez
description: Saiba como baixar e instalar guias do AEM pela primeira vez
exl-id: 830a4381-303c-419c-b87f-9563352a7eeb
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Baixe e instale os Guias do AEM pela primeira vez {#id213BCL00KEV}

Execute as seguintes etapas para baixar e instalar guias de AEM pela primeira vez em um computador:

>[!IMPORTANT]
>
> Se você quiser usar o Livefyre juntamente com os Guias do AEM, instale as versões do Livefyre anteriores à versão 3.0 antes de instalar os Guias do AEM. Se você estiver usando o Livefyre versão 3.0 ou superior, essa restrição não existe.

1. Baixe os Guias do AEM no Portal de distribuição de software Adobe.

1. Faça logon na instância do AEM e navegue até o Gerenciador de pacotes do CRX. O URL padrão para acessar o gerenciador de pacotes é:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   O Gerenciador de pacotes gerencia os pacotes na sua instalação local do AEM. Para obter mais informações sobre como trabalhar com o Gerenciador de pacotes, consulte [Como trabalhar com pacotes](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html) na documentação do AEM.

   ![](assets/package-manager.png){width="650" align="left"}

1. Para fazer upload do pacote de Guias do AEM, clique em **Fazer upload do pacote**.

1. Na caixa de diálogo Fazer upload do pacote, navegue até o arquivo Guias do AEM que você baixou na Etapa 1 e clique em **OK**.

   O pacote é carregado para a instância do AEM.

1. Para instalar o pacote, clique em **Instalar**.

   ![](assets/install-package.png){width="650" align="left"}

1. Na caixa de diálogo Instalar pacote, clique em **Instalar**.

1. Para começar a usar os Guias do AEM, clique no botão Início ![](assets/home-button.png) no canto superior esquerdo do Gerenciador de pacotes do CRX.


>[!NOTE]
>
> Execute o procedimento de instalação em todas as instâncias de servidores AEM em sua configuração.

**Tópico pai:**[ Baixar e instalar](download-install.md)
