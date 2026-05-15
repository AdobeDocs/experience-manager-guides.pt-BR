---
title: Notas de versão | Novidades na versão 2025.08.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2025.08.0 do Adobe Experience Manager Guides
role: Leader
exl-id: c3461d0a-6394-4275-9d54-b2b1545d7c18
TQID: https://experienceleague.adobe.com/-joxRCHZVxxs58BRUt7gN5mEGP9txRzf0Ofgu-OXP38
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: f6b497f1-f8e0-42ce-8e95-56c28d94026e
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 844
ht-degree: 0%

---

# Novidades da versão 2025.08.0 (agosto de 2025)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2025.08.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2025.08.0](fixed-issues-2025-08-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.08.0](../release-info/upgrade-instructions-2025-08-0.md).


## Fluxo de trabalho de revisão aprimorado

Com esta versão, o fluxo de trabalho de revisão foi significativamente aprimorado para oferecer melhor suporte à comunicação contínua entre autores e revisores. As principais atualizações incluem:

- Fluxos de trabalho de gerenciamento de tarefas com notificações acionáveis
- Capacidade de marcar usuários para buscar atenção imediata
- Acesso aos detalhes do projeto e da tarefa no painel de revisão para facilitar o uso

Com esses aprimoramentos, os usuários agora podem esperar:

- Ciclos de revisão eficientes e oportunos
- Esforço manual reduzido durante trocas de feedback

Para obter mais detalhes, exiba [Introdução à revisão](../user-guide/review.md)

## Ações configuráveis do Assistente de IA nas configurações do Editor

A última atualização apresenta uma configuração aprimorada para **Ações rápidas de criação** no Assistente de IA, permitindo que os administradores personalizem o ambiente de criação de acordo com fluxos de trabalho e preferências específicos.

Depois que a opção de alternância **Assistente de IA** estiver habilitada, os administradores poderão escolher seletivamente quais ações rápidas estarão visíveis na guia **Criação**, ajudando a simplificar as interações do autor. Essas configurações de visibilidade são específicas para cada perfil de pasta.

Saiba mais sobre o [assistente de IA nas configurações do Editor](../cs-install-guide/workspace-settings.md#general) no Experience Manager Guides.

![](assets/authoring-quick-actions.png){width="350"}


## Experiência aprimorada para criar e usar arquivos DITAVAL

Esta atualização apresenta vários aprimoramentos que simplificam a criação, o gerenciamento e a aplicação de arquivos DITAVAL, permitindo um melhor controle sobre o conteúdo condicional e o estilo em todas as saídas.

Os principais destaques são os seguintes:

- **Suporte aprimorado para sinalização na criação de arquivos DITAVAL:** o Experience Manager Guides oferece novos recursos para personalizar a publicação de conteúdo por meio do suporte aprimorado à sinalização em arquivos DITAVAL. Agora é possível aplicar sinalizadores de início e término ao redor de um conteúdo específico, incluindo imagens, e enriquecer as seções sinalizadas com opções de formatação como negrito, itálico e muito mais. Para lidar com sobreposições de condição, o **conflito de estilo** pode ser configurado, o que inclui a definição de uma cor de fundo e texto padrão, garantindo clareza e consistência na saída. Esses sinalizadores são totalmente compatíveis na geração do PDF nativo, e a saída resultante reflete de forma precisa e abrangente todos os elementos de estilo aplicados.
Para obter mais detalhes, consulte [Usar o Editor DITAVAL](../user-guide/ditaval-editor.md).

  ![](assets/ditaval-flag-style-new.png){width="350"}

- **Suporte a vários arquivos DITAVAL para PDF Nativo:** Agora, vários arquivos DITAVAL podem ser adicionados para que cada um seja exibido como uma entrada marcada, facilitando a identificação e a remoção, oferecendo maior flexibilidade e controle sobre o conteúdo condicional nas saídas do PDF

  Além disso, essa atualização melhora a criação de predefinições de saída, permitindo campos DITAVAL editáveis em todos os formatos, permitindo que os usuários especifiquem manualmente os caminhos DITAVAL.

  Para obter mais detalhes, consulte [Entender as predefinições de saída](../user-guide/generate-output-understand-presets.md) no Experience Manager Guides.

## Filtragem de log de geração de saída aprimorada

Essa versão traz melhorias na interface do usuário para o recurso de filtragem de log de geração de saída. Agora você pode filtrar melhor os logs de geração de saída para todos os quatro níveis distintos; **Info**, **Warn**, **Error** (incluindo erros e exceções) e **Fatal**; com indicadores de código de cores aprimorados e intuitivos que simplificam a análise e tornam mais nítida a visibilidade em todo o fluxo de log. Essa melhoria permite que você navegue pelos registros com mais eficiência e localize os problemas críticos com precisão.

Para obter mais detalhes, consulte [Solução de problemas básica](../user-guide/generate-output-basic-troubleshooting.md).

![](./assets/log-file-new.png)


## Os arquivos temporários para saída publicada agora incluem Autor e URLs de publicação em um novo arquivo de configuração

Os últimos aprimoramentos de publicação no Experience Manager Guides agora adicionam um novo arquivo `system_config.xml` aos arquivos temporários gerados ao publicar saídas do HTML, PDF e JSON usando DITA-OT, bem como saída do PDF nativo. Este arquivo é incluído automaticamente no trabalho de publicação e também pode ser acessado por meio de arquivos temporários quando você habilita a opção **Reter arquivos temporários** para as predefinições e gera a saída.

O arquivo `system_config.xml` contém detalhes da instância do AEM, incluindo a URL do Autor, a URL Local e a URL de Publicação, que fornecem um contexto mais claro e melhoram a rastreabilidade das URLs baixadas.

Para obter mais detalhes, consulte [Compreender as predefinições de saída](../user-guide/generate-output-understand-presets.md).

## Novo suporte à variável de caminho de saída para geração de saída

Esta atualização apresenta a configuração `output path` dinâmica para predefinições de saída como PDF Nativo, DITA-OT PDF, JSON, HTML5 e Personalizado. Em vez de usar um caminho fixo, os usuários agora podem definir o local de saída usando a variável `${base_output_path}` durante a instalação, oferecendo maior flexibilidade. O caminho padrão anterior `/content/dam/fmdita-outputs` não é mais obrigatório.

Todos os caminhos de saída associados às predefinições de perfil de pasta global serão migrados automaticamente para utilizar a nova variável de caminho de saída base. No entanto, para perfis de pastas personalizados, a migração não é automática; aconselhamos entrar em contato com a equipe de Sucesso do cliente para obter assistência.

Para obter mais detalhes, consulte [Compreender as predefinições de saída](../user-guide/generate-output-understand-presets.md).

## Melhorias na interface na barra de ferramentas do Editor e preferências do usuário

Com esta versão, as configurações em **Preferências do usuário** na página inicial das guias Geral e Aparência foram reestruturadas. Inclui renomear o rótulo **Abrir preferências para Mapas** e mover a opção Espaços não separáveis para a barra de ferramentas do Editor.

Além disso, na barra de ferramentas do Editor, alguns alternadores de acesso rápido para habilitar ou desabilitar o Controle de Alterações, Marcas e Espaços Não Separáveis agora estão agrupados na opção **Mostrar** na lista suspensa Menu para melhor usabilidade.

Para obter mais detalhes, exiba [Barra de ferramentas no Editor](../user-guide/web-editor-toolbar.md#menu-dropdown).
