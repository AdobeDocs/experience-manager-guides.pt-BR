---
title: Gerenciar conteúdo
description: Gerencie o conteúdo e identifique suas funções e permissões no AEM Guides. Saiba mais sobre os principais conceitos de gerenciamento de conteúdo e trabalho com perfis globais ou de nível de pasta.
feature: Content Management
role: User
hide: true
exl-id: 54b960cf-fb00-4d4a-a836-9de4738c49a8
TQID: https://experienceleague.adobe.com/Rko9tfse1l5d-ZKeidb8hCqs1L2RcMlc9o581Xiakk4
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: d90290ec-3e61-4ebd-8649-bcafe0836803id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: b0521e56-a0b2-40b6-bf47-ebc98751f9baid: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: b88be3fe-792c-484d-8262-9f667de75c8did: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: f7774ebe-aec9-42b6-97e4-5002acdc712eid: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: da3860b0-d637-47df-bef0-273751180266id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 741
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
| **Estado do documento** |  |  |  |
| Criar/editar perfil de estado do documento |   |   | Sim |
| Alterar estado do documento[2](#fntarg_2) | Sim | Sim | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Predefinições de Saída\)** |  |  |  |
| Gerar |   |   | Sim |
| Editar |   |   | Sim |
| Duplicado |   |   | Sim |
| Criar |   |   | Sim |
| Excluir predefinição |   |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Saídas\)** |  |  |  |
| Exibir saída gerada | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Tópicos\)** |  |  |  |
| Criar tarefa de análise | Sim |   | Sim |
| Editar | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Linhas de Base\)** |  |  |  |
| Criar |   |   | Sim |
| Editar |   |   | Sim |
| Duplicado |   |   | Sim |
| Remover |   |   | Sim |
| Console do mapa DITA \(guia Relatórios\) | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(Predefinições de Condição\)** |  |  |  |
| Criar/editar predefinição de condição |   |   | Sim |

[1](#fnsrc_1) Se *Autores* e *Editores* forem convidados para uma revisão.

[2](#fnsrc_2) Dependendo dos direitos concedidos ao usuário no perfil de estado do documento.

## Pré-requisitos para a criação de conteúdo

**Trabalhar com perfis globais ou de nível de pasta**

Em uma empresa, diferentes grupos ou produtos podem usar diferentes modelos de criação, modelos de saída, perfis de atributo condicional \(ou esquemas de assunto\) e configurações do Editor da Web. Configurar esses apenas em nível corporativo \(ou global\) pode dificultar a experiência dos autores, pois eles verão modelos ou perfis que não são relevantes para eles.

O AEM Guides permite configurar a criação de modelos \(tópico ou mapa\), modelos de saída, atributo condicional e configurações do Editor da Web em nível corporativo \(global\), bem como em nível de pasta. Dessa forma, você pode separar as configurações de diferentes departamentos ou produtos em sua empresa.

Além disso, você pode delegar as configurações específicas da pasta a um departamento ou administradores de produtos para descentralizar a administração.

Para obter detalhes sobre como configurar perfis globais e de pastas, consulte *Configurar perfis globais ou de pastas* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.
