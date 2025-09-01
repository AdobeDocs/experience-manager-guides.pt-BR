---
title: Baixe e instale modelos do AEM Sites para Serviços no local
description: Saiba como Baixar e instalar modelos do AEM Sites para no Prem Services
feature: Installation
role: Admin
level: Experienced
source-git-commit: 20ba7f4582f1d155e555c9ff3ac58e1e3c400765
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# Baixar e instalar modelos do AEM Sites (serviços no local)

Este guia fornece instruções passo a passo para instalar e configurar o modelo mais recente do AEM Guides para gerar o AEM Sites. Siga estas etapas para instalar os pacotes necessários, criar e configurar predefinições e gerar o AEM Sites.

## Pré-requisitos

Antes de continuar com a configuração, verifique se os seguintes pré-requisitos foram atendidos:

- **Adobe Experience Manager (AEM):** Uma instância em execução do **AEM 6.5** com o **Service Pack** 21, 20 e 19 e o **AEM Guides 4.6.0**, ou versões posteriores instaladas.

- **Permissões necessárias**: certifique-se de ter as seguintes permissões:

   - Acesso ao **Portal de Distribuição de Software** para baixar os pacotes necessários
   - Acesso ao **Gerenciador de Pacotes do CRX** para instalar pacotes no AEM.
   - Permissões para criar e modificar predefinições no AEM Guides.

- **Baixar Pacotes**: baixe os seguintes pacotes do **Portal de Distribuição de Software**:

   - Pacote de componentes: no local-guides-components.all-1.x.0.zip
   - Pacote do Sites: aemg-docs.all-1.x.0.zip

## Instalação de pacote usando o Gerenciador de pacotes do CRX

1. **Instalar o Pacote de Componentes:**
   1. Navegue até [**CRX Package Manager**](http://<your-aem-instance>/crx/packmgr).
   2. Carregue e instale o pacote no local-guides-components.all-1.x.0.zip.

2. **Instalar o Pacote do Sites:** Carregue e instale o pacote aemg-docs.all-1.x.0.zip usando o Gerenciador de Pacotes do CRX.


## Criar e configurar a predefinição de site do AEM

1. **Criar uma nova predefinição:**
   1. Abra um mapa DITA no AEM Guides e navegue até o painel **Saída**.
   2. Selecione **Criar Predefinição**.
   3. Selecione o tipo como **AEM Sites**.
   4. Insira um nome para a predefinição.
   5. Desmarque a configuração **Usar mapeamento de componente herdado**.
   6. Selecione **Adicionar** para criar a predefinição.

      ![Nova caixa de diálogo de predefinição de saída](/help/product-guide/knowledge-base/kb-articles/assets/publishing/new-output-preset.png){width="350" align="left"}


2. **Configurar predefinição do site AEM:** Há duas opções para configurar o site pronto para uso (OOTB):

   **Opção 1: Usar a Lista Suspensa de Sites**

   1. Selecione **Site** como **Documentação do AEMG**.
   2. Verifique se o **Caminho de publicação** e o **Modelo de página de tópico** estão definidos automaticamente como:
      - Caminho de publicação: aemg-docs/en/docs/product1
      - Modelo da página de tópico: Página de tópico.

      ![Usar lista suspensa de sites](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown.png){width="350" align="left"}

   **Opção 2: Usar o Caminho do Site**

   1. Defina o **Caminho do site** manualmente como /content/aemg-docs/en/docs/product1.
   2. Verifique se o **modelo de página de Tópico** está automaticamente definido como Página de Tópico.

      ![Usar Caminho do Site](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path.png){width="350" align="left"}

3. **Salvar a predefinição:** Salve as alterações feitas na predefinição.

## Gerar AEM Sites

1. **Gerar Site:**
   1. Com a predefinição configurada, agora é possível gerar o site do AEM para o mapa DITA correspondente.
   2. O site gerado estará disponível no caminho: /content/aemg-docs/en/docs/product1.
2. **Alterar o Caminho de Geração Padrão (Opcional):** Se desejar alterar o caminho padrão para geração de site, execute as seguintes etapas:

   1. Navegue até **AEM Sites**.
   2. Crie uma nova página de produto na estrutura do site OOTB.
   3. Navegue até **Documentação do AEMG** > **Inglês** > **Documentação**.

      ![Criar página na estrutura de Site do AEM ](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-page.png){width="350" align="left"}

   4. Selecione o bloco **Página inicial** e selecione **Avançar**.

      ![Selecionar bloco da página inicial](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-page-tile.png){width="350" align="left"}

   5. Insira o **Título** e o **Nome** da página.
   6. Selecione **Criar**.

