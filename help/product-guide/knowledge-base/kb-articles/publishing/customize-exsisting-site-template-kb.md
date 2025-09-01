---
title: Personalizar modelos existentes de sites do AEM para o AEM Guides
description: Saiba como personalizar modelos existentes de site do AEM para o AEM Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 1cec8975e8aad56184793a023d066aa467d8cec5
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 1%

---

# Personalizar modelos existentes de sites do AEM para o AEM Guides

Este guia fornece instruções passo a passo para personalizar modelos de site do AEM existentes para uso com o AEM Guides para gerar AEM Sites a partir de mapas e tópicos DITA.

Se estiver usando o modelo pronto para uso do AEM Guides (AEMG Docs), as configurações e os componentes já estarão em vigor e poderão ser usados como estão para publicar seu conteúdo do AEM Guides. No entanto, se você quiser usar seus modelos existentes do AEM Sites com marca personalizada para publicar conteúdo do AEM Guides, siga as etapas abaixo para alinhar seus modelos de sites aos requisitos de renderização do AEM Guides.


## Pré-requisitos

- Você tem permissões e acesso apropriados aos modelos do AEM.
- Você entende os modelos editáveis do AEM e a estrutura do AEM Site.
- Você tem uma hierarquia de site existente criada usando modelos editáveis.
- Você tem pelo menos dois modelos do seu projeto existente:

   - **Modelo de página de contêiner da documentação** usado para renderizar o mapa DITA como uma raiz de documentação.
   - **Modelo de Página de Tópico** usado para renderizar páginas de tópico DITA individuais.

## Considerações de nomenclatura do modelo

Os nomes dos modelos variam de acordo com a configuração do projeto. Por exemplo, na configuração OOTB AEMG Docs:

- Página do contêiner da documentação: /conf/AEMG-Docs-Site/settings/wcm/templates/kb-content

- Página de tópico: /conf/AEMG-Docs-Site/settings/wcm/templates/topic-content

**Personalização:** o processo de personalização envolve duas etapas principais:

1. Configuração do modelo: Identifique e configure os dois modelos (container e tópico).
2. Componentes dos Guias de renderização: incorpore componentes obrigatórios do AEM Guides para ativar recursos como índice, navegação e exibição de metadados.

## Configuração de modelo

Escolha e configure dois modelos editáveis no seu site do AEM.

### Modelo da página de contêiner da documentação

O modelo da Página de contêiner da documentação é usado para criar a Página de contêiner da documentação do produto que renderiza o conteúdo de um mapa DITA.

- Ele serve como ponto de entrada ou página inicial de um conjunto específico de documentação (por exemplo, um manual ou guia de produto).
- Adicione a propriedade id=&quot;category-page&quot; ao jcr:content do nó inicial do modelo. Isso garante que todas as páginas criadas com base nesse modelo sejam tratadas automaticamente como contêineres de documentação pelo AEM Guides.

  ![Adicionando id=&quot;category-page&quot;](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-id-category-page.png){width="650" align="left"}

- Adicione um componente de Texto com a propriedade obrigatória: text=&quot;$category.html$&quot;.

  ![Adicionando componente de texto](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component.png){width="650" align="left"}

- Normalmente inclui elementos de navegação, como links para seções ou tópicos na documentação.
- Ele pode ser personalizado para incluir marcas, cabeçalhos, rodapés e outros elementos de design.

**Exemplo de caso de uso:**
Se você tiver um mapa DITA para um manual de produto, o modelo de página do contêiner de documentação gerará a página inicial desse manual, exibindo uma visão geral e links para tópicos individuais.

### Modelo de página de tópico

- O **modelo de Página de Tópico** é usado para criar páginas para **tópicos DITA** individuais.
- Cada tópico em um mapa DITA é renderizado como uma página separada usando esse modelo.
- Contém um **componente de Texto** com a propriedade obrigatória: text=&quot;$topic.content$&quot;.

  ![Adicionando componente de texto com propriedade obrigatória](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component-mandatory-property.png){width="650" align="left"}

- Esse espaço reservado é substituído pelo conteúdo real do tópico DITA durante a geração do site.
   - O componente de texto normalmente é colocado dentro de um **Componente de contêiner** para garantir o layout e estilo adequados.
   - Pode ser personalizado para incluir cabeçalhos, rodapés e elementos de navegação consistentes em todas as páginas de tópico.

**Exemplo de caso de uso:**
Se você tiver um tópico DITA sobre &quot;Instruções de instalação&quot;, o modelo de página de tópico gerará uma página exibindo o conteúdo desse tópico.

**Componente de contêiner:**

![Adicionando componente de contêiner](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-component.png){width="650" align="left"}

>[!NOTE]
>
> Certifique-se de que os componentes que usam sling:resourceType em wcm/foundation/components sejam migrados para o core/wcm/components correspondente.

Adicione o mesmo (contêiner e componente de texto) na estrutura do mesmo modelo:

![Adicionando contêiner e componente de texto](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-and-text-component.png){width="650" align="left"}

## Renderizar guias Componentes em modelos personalizados

Para habilitar os recursos principais dos componentes do AEM Guides, como índice, redirecionamento de página, navegação e exibição de metadados, é necessário incluir componentes específicos do AEM Guides nos modelos personalizados. Esses componentes devem ser adicionados explicitamente aos modelos editáveis correspondentes (Página de contêiner da documentação ou Página de tópico) para garantir que a funcionalidade desejada esteja disponível durante a geração e o tempo de execução do site.

Consulte a tabela abaixo para obter a lista de componentes e seu uso:

| Destaque | Nome do componente | Descrição | Modelo recomendado |
|---|---|---|---|
| Índice | guidessidenavigation | Renderiza o índice completo do mapa DITA | Contêiner da documentação |
| Redirecionamento de página | filho direto | Redireciona para a primeira página de tópico do mapa | Contêiner da documentação |
| Mini TOC | minitoc | Exibe o índice do tópico atual | Página de tópico |
| Última atualização | pageproperty | Exibe a última data de modificação | Página de tópico |
| Pager | pager | Permite a navegação entre páginas de tópico anteriores e seguintes | Página de tópico |
| Navegação de idiomas | navegação por idiomas | Permite alternar entre diferentes versões de idioma | Qualquer modelo |


## Casos de uso de componentes

- **Componente de redirecionamento (direcionamento secundário):** adicione isso ao modelo de página de contêiner de documentação para que a página inicial do produto gerada pelo mapa DITA redirecione automaticamente para a página do primeiro tópico. Se a página do contêiner de documentação for projetada para atuar como uma página inicial independente com componentes e layout personalizados, esse componente não será necessário.

- **Sumário (guidessidenavigation):** Adicione isso ao modelo de página de tópico para renderizar um sumário navegável junto ao conteúdo do tópico. O índice é derivado do mapa DITA e ajuda os usuários a navegar entre tópicos semelhantes.


## Ativação de bibliotecas de clientes do Guides

Por padrão, as bibliotecas de clientes (clientlibs) fornecidas no pacote de componentes do AEM Guides não são aplicadas aos modelos personalizados. Para ativá-los:

1. **Editar o Modelo:**

   1. Abra a **Página do Produto** no **Modo Editor**.
   2. Selecione **Editar Modelo** (isso abrirá uma URL como conf/settings/wcm/templates/structure.html).

      ![Editar modelo](/help/product-guide/knowledge-base/kb-articles/assets/publishing/edit-template.png){width="650" align="left"}

2. **Atualizar Política de Página:**

   1. Vá para o botão **Informações da página** e selecione **Política da página**.
   2. Adicione as seguintes bibliotecas de clientes:
      - **Bibliotecas de Clientes**
      - **Cabeçalho da página JavaScript de bibliotecas do cliente**

3. **Salvar alterações:** Salve o modelo depois de adicionar as bibliotecas de clientes necessárias.

   ![Adicionar bibliotecas de clientes](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-client-libraries.png){width="650" align="left"}


>[!NOTE]
>
> Verifique se os modelos foram testados em um ambiente de não produção antes de implantar na produção.<br><br>Consulte a documentação oficial do [AEM Guides](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/overview) e do [AEM Sites](https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/get-started/authoring) para obter detalhes adicionais.
