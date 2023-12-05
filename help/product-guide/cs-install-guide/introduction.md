---
title: Sobre este guia
description: Saiba mais sobre este guia
exl-id: cdd40267-3f0c-40d2-acbc-2ebe43633c2f
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 2%

---

# Sobre este guia {#id175MC0P0S5Z}

Guias do Adobe Experience Manager \(mais tarde referidos como *Guias do AEM* O é uma poderosa solução corporativa de gerenciamento de conteúdo de componentes baseada em nuvem \(CCMS\). Ela permite o suporte ao DITA nativo no Adobe Experience Manager, permitindo que o AEM lide forma a lidar com a criação e a entrega de conteúdo baseado em DITA. Ele permite que os autores criem conteúdo usando o Editor da Web integrado fácil de usar e o publiquem em vários formatos de saída.

Este guia fornece as instruções para baixar, instalar e configurar os Guias do AEM. Neste guia, você encontrará instruções detalhadas para configurar Guias do AEM de acordo com suas necessidades organizacionais de criação e publicação.

Este guia destina-se aos seguintes tipos de público-alvo:

- Administradores, que instalariam e gerenciariam os Guias do AEM.

- Editores, que executariam a tarefa de publicação para gerar saída em vários formatos.


## Estrutura de conteúdo

As informações neste guia estão organizadas da seguinte maneira:

- [Sobre este guia](#id175MC0P0S5Z): este tópico fornece uma introdução a este guia, público-alvo desejado e como as informações são organizadas neste guia.

- [Baixar e instalar](download-install.md#): este tópico descreve como baixar, instalar ou atualizar os Guias do AEM.

- [Administração e segurança do usuário](user-admin-sec.md#): este tópico descreve o conceito principal de usuários e autenticação no AEM e os grupos de usuários padrão criados pelos Guias do AEM.

- [Usar a especialização personalizada do DITA-OT e do DITA](dita-ot-specialization.md#): este tópico explica como configurar plug-ins DITA-OT personalizados e usar a especialização DITA.

- [Configurar estados dos documentos](customize-doc-state.md#): este tópico explica como configurar estados personalizados para seus documentos DITA.

- [Migrar conteúdo existente](migrate-content.md#): este tópico descreve como integrar seu conteúdo existente no repositório AEM.

- [Configurar nomes de arquivo](conf-file-names.md#): este tópico explica como definir as configurações para atribuir nomes de arquivo automaticamente e definir um regex para caracteres válidos de nomes de arquivo.

- [Configurar tópico e modelos de mapa](conf-template-tags.md#): este tópico descreve como configurar tópicos e mapear modelos para atender às suas necessidades de criação. Saiba mais sobre como marcar o sistema no AEM e como configurar tags para funcionar com o AEM Guides.

- [Personalizar editor da Web](conf-web-editor.md#): este tópico explica as várias personalizações que você pode fazer no Editor da Web para aprimorar sua funcionalidade.

- [Incluir atributo @navtitle por padrão](auto-add-navtitle.md#): Este tópico explica como adicionar a variável `@navtitle` atributo para um arquivo de referência em um mapa por padrão.

- [Configurar perfis globais ou de nível de pasta](conf-folder-level.md#): este tópico explica o processo de criação de perfis de pastas e de concessão de permissões a usuários específicos.

- [Gerenciamento de versão](version-management.md#): este tópico descreve como configurar o check-out automático de arquivos para arquivos abertos para edição no Editor da Web.

- [Definir configurações de geração de saída](conf-output-generation.md#): este tópico descreve as várias configurações que você pode fazer para personalizar o processo de geração de saída padrão.

- [Configurar e personalizar workflows](customize-workflows.md#): este tópico descreve várias configurações para personalizar os workflows padrão enviados nos Guias do AEM.

- [Traduzir conteúdo](translation.md#): este tópico fornece links para os artigos de Ajuda relevantes na documentação do AEM para ajudar você a entender e configurar a estrutura de tradução. Além disso, saiba como ativar o fluxo de trabalho de tradução baseado em componentes.

- [Configurar pesquisa para a interface do usuário do AEM Assets](conf-dita-search.md#): este tópico descreve como configurar a pesquisa de conteúdo DITA na interface do usuário do Assets e adicionar atributos personalizados na pesquisa.


## Visão geral do Adobe Experience Manager \(AEM\)

[Adobe Experience Manager\( AEM\)](https://business.adobe.com/products/experience-manager/adobe-experience-manager.html) O é uma solução abrangente de gerenciamento de conteúdo para a criação de sites, aplicativos móveis e formulários. O AEM ajuda você a gerenciar o conteúdo e os ativos de marketing. O AEM está disponível as a Cloud Service. O AEM as a Cloud Service ajuda você a fornecer experiências personalizadas e orientadas por conteúdo aos seus clientes, combinando o poder do Sistema de Gerenciamento de Conteúdo do AEM com o Gerenciamento de Ativos Digitais do AEM AEM as a Cloud Service.Alguns dos principais recursos que podem ajudar você a começar e implantar o são os seguintes:

- [Visão geral do Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=en)
- [Introdução à Jornada de migração para o AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/migration-journey/getting-started.html?lang=en)
- [Iniciar integração com o Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/home.html?lang=enhttps://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/home.html?lang=en)
- [Implementação de aplicativos do AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/home.html?lang=en)
- [Implantação do AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/overview.html?lang=en)
- [Guia as a Cloud Service do Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/home.html?lang=pt-BR)

## Recursos adicionais

Veja a seguir uma lista de outros recursos úteis dos Guias do AEM, que estão disponíveis no [Aprendizagem e suporte](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) página:

- Guia do usuário
- Guia de referência de API
