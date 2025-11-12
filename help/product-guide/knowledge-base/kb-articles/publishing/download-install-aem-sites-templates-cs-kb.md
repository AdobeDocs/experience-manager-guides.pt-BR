---
title: Baixe e instale modelos do AEM Sites para serviços em nuvem
description: Saiba como Baixar e instalar modelos do AEM Sites para serviços em nuvem
feature: Installation
role: Admin
level: Experienced
exl-id: 67f7ff26-fbc7-426c-aa7d-9bf4debf05d8
source-git-commit: 4c564a0ffaa8f287bcaf012634d49dbf1e0682b4
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 1%

---

# Baixar e instalar modelos do AEM Sites (serviços em nuvem)

Este guia fornece instruções passo a passo para configurar o modelo mais recente do AEM Guides para gerar páginas do AEM Sites em um ambiente de nuvem. Siga estas etapas para instalar os pacotes necessários, criar e configurar predefinições e gerar o AEM Sites.

## Pré-requisitos

Antes de continuar com a configuração, verifique se os seguintes pré-requisitos foram atendidos:

- **Nuvem do Adobe Experience Manager (AEM)**: uma instância em execução do **AEM as a Cloud Service** com o **AEM Guides 2502 ou versões posteriores**.

- **Permissões necessárias**: você deve ter as seguintes permissões:

   - Acesso ao **Cloud Manager** para implantar pacotes.
   - Acesso ao **Repositório Git** associado ao seu ambiente.
   - Permissões para criar e modificar predefinições no AEM Guides.

- **Baixar Pacotes**: baixe os seguintes pacotes do Portal de Distribuição de Software:

   - Pacote de componentes: guides-components.all-1.x.0.zip
   - Modelo de sites: aemg-docs-1.x.0.zip

## Instalação de pacote por meio da implantação na nuvem

Instale o **Pacote de Componentes (guides-components.all-1.x.x.zip)** e execute as seguintes etapas

1. **Clonar repositório Git:**
   1. Navegue até **Repositórios** no painel esquerdo do Cloud Manager.
   2. Selecione **Acessar informações do repositório** e copie o comando git clone.

      ![Selecionar informações do Repositório de Acesso](/help/product-guide/knowledge-base/kb-articles/assets/publishing/access-repo.png){width="350" align="left"}

   3. Clonar o repositório no sistema local usando o nome de usuário e a senha fornecidos (gerar senha, se necessário).
2. **Adicionar Pacote ao Pacote Maven:**
   1. No repositório clonado localmente, crie um novo pacote Maven ou adicione a um existente.
   2. Verifique se a estrutura `/jcr_root/apps/fmdita/` instalada existe no projeto Maven.

      ![Estrutura em projeto Maven](/help/product-guide/knowledge-base/kb-articles/assets/publishing/maven-structure.png){width="650" align="left"}


   3. Coloque o arquivo guides-components.all-1.x.x.zip baixado na pasta de instalação.

3. **Atualizar filters.xml:**

   1. Abra o arquivo filters.xml localizado na pasta META-INF do diretório de conteúdo principal.
   2. Adicionar o filtro a seguir: raiz do filtro=`/apps/fmdita` modo=`merge`/


      ![Adicionar filtro](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-filter-xml.png){width="650" align="left"}


4. **Configurar pom.xml:** Atualize o arquivo pom.xml de acordo com os requisitos de ambiente.
5. **Enviar alterações e executar o pipeline:**
   1. Envie as alterações para o repositório Git principal.
   2. Navegue até **Pipelines** no Cloud Manager e execute o pipeline para o ambiente desejado.
6. **Verificar instalação:** depois que a implantação for concluída, o pacote de componentes será instalado no ambiente da AEM Cloud.

## Criar site usando modelos instalados

1. **Importar Modelo de Sites:**
   1. Acesse a página do AEM Sites (servername/sites.html/content).
   2. Selecione **Criar** > **Site** do Modelo.
   3. Importe o modelo de sites aemg-docs-1.x.x.zip usando a opção **Importar**.
2. **Selecionar Modelo:** Selecione **AEMG Docs 1.x.x** e **Avançar**.
3. **Inserir Detalhes do Site:** Insira o **Título do Site** e o **Nome do Site**.

   ![Criar Site](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-site.png){width="350" align="left"}

4. Selecione **Criar**.

## Criar predefinição de site do AEM

1. **Criar uma nova predefinição:**
   1. Abra um mapa DITA no AEM Guides e navegue até o painel **Saída**.
   2. Selecione **Criar Predefinição**.
   3. Selecione o tipo como **AEM Sites**.
   4. Insira um nome para a predefinição.
   5. Desmarque a configuração **Usar mapeamento de componente herdado**.

      ![Criar nova predefinição de site do AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-output-preset.png){width="350" align="left"}

   6. Selecione **Adicionar** para criar a predefinição.
2. **Configurar predefinição do site AEM:** Há duas opções para configurar o site pronto para uso (OOTB):

   **Opção 1: Usar a Lista Suspensa de Sites**

   1. Selecione **Site** como o criado acima (por exemplo, Site AEMG Docs).
   2. Verifique se o **Caminho de publicação** e o modelo de **Página de tópico** estão definidos automaticamente como:
      - Caminho de publicação: `/content/AEMG-Docs-Site/en/docs/product`
      - Modelo da página de tópico: Página de tópico

      ![Usar a lista suspensa de sites para configurar o Site do AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown-cs.png){width="350" align="left"}

   **Opção 2: Usar o Caminho do Site**

   1. Defina o **caminho do site** manualmente como `/content/AEMG-Docs-Site/en/docs/product`.
   2. Verifique se o modelo de **Página de Tópico** está automaticamente definido como Página de Tópico.

      ![Usar o caminho do site para configurar o Site do AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path-cs.png){width="650" align="left"}

3. **Salvar a predefinição:** Salve as alterações feitas na predefinição.

## Gerar AEM Sites

1. **Gerar Site:**
   1. Com a predefinição configurada, gere o site do AEM para o mapa DITA correspondente.
   2. O site gerado estará disponível no caminho: `/content/AEMG-Docs-Site/en/docs/product`.
2. **Alterar o Caminho de Geração Padrão (Opcional):** Se desejar alterar o caminho padrão para geração de site, execute as seguintes etapas:
   1. Navegue até **AEM Sites**.
   2. Crie uma nova página de produto na estrutura do site OOTB.
   3. Navegue até **Documentação do AEMG** > **Inglês** > **Documentação**.

      ![Criar página](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-page-cs.png){width="650" align="left"}

   4. Selecione o bloco **Página inicial** e selecione **Avançar**.

      ![Selecionar bloco da Página Inicial](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-tile-cs.png){width="650" align="left"}

   5. Insira o **Título** e o **Nome** da página.
   6. Selecione **Criar**.

>[!NOTE]
>
> Verifique se todas as configurações foram testadas em um ambiente de não produção antes de implantar na produção. <br><br> Consulte a [documentação oficial de Implantação do AEM as a Cloud Service](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-service/content/implementing/deploying/overview) para obter mais detalhes.
