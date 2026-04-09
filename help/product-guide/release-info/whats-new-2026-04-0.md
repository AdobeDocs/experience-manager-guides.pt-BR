---
title: Notas de versão | Novidades na versão 2026.04.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2026.04.0 do Adobe Experience Manager Guides
role: Leader
source-git-commit: ce2c9da0d9beb05a15f7cefcf9483e0c93abbf37
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 0%

---

# Novidades da versão 2026.04.0 (abril de 2026)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2026.04.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2026.04.0](fixed-issues-2026-04-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.04.0](../release-info/upgrade-instructions-2026-04-0.md).

## Introdução ao treinamento de produtos e ao conteúdo de aprendizado no Experience Manager Guides

O recurso de conteúdo **Treinamento e Aprendizado de Produtos** no Experience Manager Guides permite que equipes de treinamento e designers de instrução criem cursos interativos de eLearning diretamente da interface do Experience Manager Guides.

![](assets/lc-overview.png)

Com a criação orientada por modelo, os componentes interativos do curso e o suporte a avaliações, as equipes podem desenvolver conteúdo de treinamento de alta qualidade alinhado aos objetivos organizacionais.

>[!NOTE]
> 
> O recurso de conteúdo de Treinamento e aprendizado do produto permanece desativado por padrão para todas as instâncias do Experience Manager Guides as a Cloud Service. Os administradores podem habilitar este recurso no nível do perfil da pasta em **Configurações do Workspace** > **Geral**.

Os principais recursos são os seguintes:

- Gerenciamento centralizado do conteúdo de aprendizagem
- Criação orientada por modelo
- Suporte para reutilização de conteúdo
- Criação e gerenciamento de avaliação
- Fluxos de trabalho de revisão baseados na Web
- Gerenciamento de tradução líder do setor
- Publicação em vários canais usando formatos de saída prontos para uso SCORM e PDF

Para obter mais detalhes, consulte [Guia de introdução](../learning-content/course-overview.md) e [Guia de configuração](../lc-config-guide/introduction.md).


## Aprimoramentos do editor

Os seguintes aprimoramentos do Editor foram feitos como parte desta versão:

### Melhorias no painel de validação do Schematron

Os seguintes aprimoramentos foram feitos na interface do usuário do Schematron para obter mais clareza, usabilidade e resultados de validação:

- No painel Validação, uma mensagem de estado vazio é exibida quando nenhum arquivo do Schematron é adicionado, fornecendo melhor clareza e direção para as próximas etapas.

  ![](assets/schematron-panel.png){width="350" align="left"}
- Quando vários arquivos do Schematron são adicionados, eles são organizados em uma opção consolidada, fornecendo melhor visibilidade dos arquivos do Schematron configurados.

  ![](assets/schematron-panel-error.png){width="350" align="left"}
- Com base no atributo de função definido no arquivo Schematron, os resultados da validação agora são categorizados como: `Fatal`, `Error`, `Warn` ou `Info`. Cada categoria inclui uma contagem visível juntamente com uma dica de ferramenta contextual para uma interpretação mais clara.

  ![](assets/schematron-validation-errors.png){width="350" align="left"}

Para obter mais detalhes sobre como usar arquivos Schematron no Experience Manager Guides, exiba [Suporte para arquivos Schematron](../user-guide/support-schematron-file.md).

### As cópias de idioma de tradução agora estão disponíveis no painel Direito da interface do editor

Uma nova seção **Traduções** está disponível no painel direito em *Propriedades do arquivo*, no Editor. Esta seção fornece acesso direto a todas as cópias de idioma disponíveis para o ativo aberto no momento (mapa, tópico, imagem etc.). Não é mais necessário navegar para a interface do usuário do Assets para exibir ou acessar essas cópias de idioma.

![](assets/translations-right-panel.png){width="350" align="left"}

Para cada cópia de idioma, é possível passar o mouse sobre o arquivo para localizar seu caminho no repositório ou simplesmente selecioná-lo para abri-lo no Editor. Além de abrir arquivos, você também pode executar muitas ações usando o menu **Opções**. Algumas das ações que você pode executar incluem Editar, Visualizar, Copiar UUID, Copiar caminho, Adicionar às coleções e Propriedades.

Para obter mais detalhes, consulte [Painel direito no Editor](../user-guide/web-editor-right-panel.md#file-properties).


### Pesquisar citações em todos os campos de diário

Agora você pode pesquisar citações em todos os campos do Diário, como *Título*, *Título do diário*, *Autor*, *Ano*, *Volume*, *Número* e *Páginas*, usando a opção **Qualquer campo** na caixa de diálogo **Adicionar citação**. A pesquisa retorna a citação mais próxima com base no texto inserido.

Para obter mais detalhes sobre como adicionar citações no Experience Manager Guides, exiba [Adicionar e gerenciar citações em seu conteúdo](../user-guide/web-editor-apply-citations.md).

![](assets/add-citations.png){width="350" align="left"}



## Revisar melhorias

Os seguintes aprimoramentos estão disponíveis para o recurso Revisão nesta versão:

- Atribuir um Revisor a uma tarefa de revisão agora depende de uma seleção de projeto ativa. O campo **Atribuir a** na página *Criar Tarefa de Revisão* permanece desabilitado até que um projeto ativo seja selecionado. Depois que um projeto é selecionado, o campo **Atribuir a** é habilitado e lista somente os usuários e grupos de usuários associados a esse projeto. Isso garante que as tarefas de revisão sejam atribuídas somente a membros válidos do projeto e impede a seleção não intencional do Revisor.

  ![](assets/create-review-task-023.png)

- O campo **Atribuir a** agora oferece suporte à pesquisa com digitação antecipada, permitindo que você localize usuários ou grupos de usuários rapidamente digitando texto.

Juntos, esses aprimoramentos tornam a seleção do Revisor mais precisa, eficiente e alinhada aos fluxos de trabalho de revisão específicos do projeto.

Para obter mais detalhes, exiba [Enviar tópicos para revisão](../user-guide/review-send-topics-for-review.md).

## Aprimoramentos no gerenciamento de ativos

Esta versão apresenta os seguintes aprimoramentos ao gerenciamento de ativos:

### Usar Nivelar hierarquia de arquivos para baixar mapas com nomes de arquivos originais e metadados associados

Agora, você pode usar a opção Nivelar hierarquia de arquivos para baixar um mapa com seu nome de arquivo original. Além disso, o pacote baixado inclui um arquivo `metadata.json`, tornando os metadados associados facilmente acessíveis e reutilizáveis fora do Experience Manager Guides.

Para obter mais detalhes sobre como baixar arquivos no Experience Manager Guides, consulte [Baixar arquivos](../user-guide/authoring-download-assets.md).

### Usar regex para ativar ou desativar o pós-processamento

Agora é possível usar o regex para ativar ou desativar o pós-processamento para pastas. Esse aprimoramento permite que os administradores definam regras de pós-processamento que se aplicam a várias pastas ou hierarquias de pastas inteiras usando uma única configuração, em vez de especificar caminhos de pastas individuais.

Para obter mais detalhes, exiba [Usar regex para habilitar ou desabilitar o pós-processamento](../cs-install-guide/conf-folder-post-processing.md#use-regex-to-enable-or-disable-post-processing).
