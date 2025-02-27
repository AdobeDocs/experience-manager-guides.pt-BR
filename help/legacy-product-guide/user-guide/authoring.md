---
title: Gerenciar conteúdo
description: Gerencie o conteúdo e identifique suas funções e permissões no AEM Guides. Saiba mais sobre os principais conceitos de gerenciamento de conteúdo e trabalho com perfis globais ou de nível de pasta.
feature: Content Management
role: User
hide: true
exl-id: 54b960cf-fb00-4d4a-a836-9de4738c49a8
source-git-commit: 7286c3fb36695caa08157296fd6e0de722078c2b
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 10%

---

# Gerenciar conteúdo {#id164JBG0M0T1}

Antes de começar com a criação real do conteúdo, você deve se familiarizar com alguns conceitos básicos de gerenciamento de conteúdo no AEM Guides. Em seguida, comece criando diferentes grupos de usuários e organizando seus ativos.

## Principais conceitos

Alguns conceitos principais de gerenciamento de conteúdo no AEM são os seguintes:

**Gerenciamento de ativos**

O AEM Guides usa o gerenciamento de ativos digitais da AEM \(DAM\) para gerenciar seus arquivos DITA. Os arquivos carregados ou verificados no DAM são armazenados como ativos digitais. Você pode gerenciar e editar seus ativos no AEM Assets. Para obter mais informações sobre o gerenciamento de ativos, consulte [Gerenciar ativos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=en).

**Gerenciamento de links**

Mover ou renomear arquivos ou alterar a estrutura de pastas no repositório de conteúdo, sem se preocupar com referências corrompidas. Todas as referências de e para o conteúdo afetado são atualizadas automaticamente. Obtenha avisos ao excluir o conteúdo referenciado de outro lugar, para evitar interrupções não intencionais.

**Gerenciando versões**

O AEM Guides fornece gerenciamento de versão para seus ativos digitais. Você pode ativar facilmente essa funcionalidade em um aplicativo de criação DITA preferido. Permitir que seus escritores executem as funções de controle de versão padrão, como check-in e check-out.

Para obter mais informações sobre como criar versões ou reverter para uma versão específica, consulte [Ramificação, reverter e versões subsequentes](web-editor-preview-topics.md#id193PG0Y051X).

**Manuseio de DITA nativo**

Embora o AEM Guides mantenha a estrutura de seus arquivos DITA, ele também permite que o AEM manipule nativamente o DITA usando o mapeamento de elementos para mapear os elementos DITA para componentes do AEM. O tratamento DITA nativo é usado em recursos como visualização de tópico, publicação no AEM Sites e os workflows de revisão.

## Identificar sua função e permissões {#id181TF0K0MHT}

O AEM Guides fornece três grupos prontos para uso. Estes grupos são: *Autores*, *Revisores* e *Editores*. Dependendo do grupo ao qual você está associado, você tem permissões para executar tarefas específicas, conforme mencionado na tabela abaixo. Por exemplo, a tarefa de publicação pode ser executada somente por um editor, mas não por um autor ou um revisor. Da mesma forma, um autor pode criar um novo tópico e um revisor só pode revisar um tópico.

>[!TIP]
>
> Consulte a seção *Permissões* no guia de Práticas recomendadas para obter as práticas recomendadas sobre a definição de permissões de usuário.

A tabela a seguir lista várias tarefas e os grupos que podem executá-las:

| Tarefa | Autores | Revisores | Editores |
|----|-------|---------|----------|
| Criar tópico DITA | Sim |   | Sim |
| Criar mapa DITA | Sim |   | Sim |
| Mapear coleções | Sim |   | Sim |
| Criar tarefa de análise | Sim |   | Sim |
| Tópico de Revisão[1](#fntarg_1) | Sim | Sim | Sim |
| Resolução de chave | Sim |   | Sim |
| Check-out/Check-in | Sim |   | Sim |
| Editar tópico | Sim |   | Sim |
| Mover tópico | Sim |   | Sim |
| Editar Propriedades do Tópico | Sim |   | Sim |
| Copiar | Sim |   | Sim |
| Excluir | Sim |   | Sim |
| Compartilhar | Sim |   | Sim |
| **Estado do documento** |
| Criar/editar perfil de estado do documento |   |   | Sim |
| Alterar estado do documento[2](#fntarg_2) | Sim | Sim | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Predefinições de Saída\)** |
| Gerar |   |   | Sim |
| Editar |   |   | Sim |
| Duplicado |   |   | Sim |
| Criar |   |   | Sim |
| Excluir predefinição |   |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Saídas\)** |
| Exibir saída gerada | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Tópicos\)** |
| Criar tarefa de análise | Sim |   | Sim |
| Editar | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Linhas de Base\)** |
| Criar |   |   | Sim |
| Editar |   |   | Sim |
| Duplicado |   |   | Sim |
| Remover |   |   | Sim |
| Console do mapa DITA \(guia Relatórios\) | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(Predefinições de Condição\)** |
| Criar/editar predefinição de condição |   |   | Sim |

[1](#fnsrc_1) Se *Autores* e *Editores* forem convidados para uma revisão.

[2](#fnsrc_2) Dependendo dos direitos concedidos ao usuário no perfil de estado do documento.

## Pré-requisitos para a criação de conteúdo

**Trabalhar com perfis globais ou de nível de pasta**

Em uma empresa, diferentes grupos ou produtos podem usar diferentes modelos de criação, modelos de saída, perfis de atributo condicional \(ou esquemas de assunto\) e configurações do Editor da Web. Configurar esses apenas em nível corporativo \(ou global\) pode dificultar a experiência dos autores, pois eles verão modelos ou perfis que não são relevantes para eles.

O AEM Guides permite configurar a criação de modelos \(tópico ou mapa\), modelos de saída, atributo condicional e configurações do Editor da Web em nível corporativo \(global\), bem como em nível de pasta. Dessa forma, você pode separar as configurações de diferentes departamentos ou produtos em sua empresa.

Além disso, você pode delegar as configurações específicas da pasta a um departamento ou administradores de produtos para descentralizar a administração.

Para obter detalhes sobre como configurar perfis globais e de pastas, consulte *Configurar perfis globais ou de pastas* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.
