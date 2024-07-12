---
title: Notas de versão | Correção de problemas na versão 2024.2.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2024.2.0 do Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Correção de problemas na versão 2024.2.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2024.2.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2024.2.0](whats-new-2024-2-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2024.2.0](upgrade-instructions-2024-2-0.md).



## Criação  

- A verificação ortográfica no Editor não permite a seleção de sugestões. (15045)
- O botão de navegação global não está funcionando e o painel não é carregado. (14968)
- No Editor da Web, o recurso de mapa de download não aciona uma notificação pop-up quando está pronto para download. (14626)
- No Editor da Web, o recurso de download de mapa falha ao baixar um mapa com linha de base. (14622)
- Erro de DTD inválido na versão de outubro de 2023 do Experience Manager Guides as a Cloud Service. (14482)
- Arrastar um tópico de glossário do repositório para um mapa de glossário cria `topicref`. (10767)
- A tela de visualização de trechos está congelada. (14840)
- Os rótulos do arquivo `labels.json` aparecem em ordem aleatória no Editor da Web. (10508)

## Publicação

- Na publicação de PDF nativo, os atributos personalizados nas predefinições de condição não funcionam na publicação de PDF nativo. (14943)
- Na publicação de PDF nativo, as referências principais não estão sendo resolvidas na versão de dezembro de 2023 do Adobe Experience Manager Guides. (15085)
- A publicação do AEM Sites falha e causa erros de escopo para arquivos com `xref` para o arquivo DITA que começam com &quot;HTTP&quot;. (15154)
- Não é possível adicionar um modelo personalizado da guia **Saídas** no Editor. (14846)
- A predefinição **Site AEM** não está funcionando devido a um caminho de modelo vazio. (14804)
- A regeneração do site AEM falha para mapas DITA com tópicos que contêm equações MathML. (14790)
- Na publicação de PDF nativo, a geração de PDF gera erros ao obter dependências para a publicação `Node.js`. (14445)
- A predefinição de AEM não permite a seleção de um modelo fora da hierarquia `/content` no Editor da Web. (14260)
- Na saída do AEM Sites, o estilo ou as quebras de linha foram perdidas para o elemento `<lines>` que tem subelementos. (12542)
- Os metadados personalizados não estão disponíveis na saída final. (12116)
- Na publicação de PDF nativo, as propriedades de metadados do mapa DITA não podem ser usadas para preencher os metadados da saída do arquivo PDF. (15159)



## Gerenciamento

- Os arquivos do **Filtro de Linha de Base** não estão funcionando com o Nome de Arquivo no Editor da Web. (13486)
- Desativar a indexação do mapa DITA principal para obter um melhor desempenho pode afetar a funcionalidade de determinados recursos.(12213)


## Revisar

- O menu de contexto de clique com o botão direito do mouse não funciona para **Aceitar** ou **Rejeitar** alterações de controle. (14607)
- Alternar para fechar tópicos DITA na tela Revisar não funciona na versão de dezembro de 2023 do Adobe Experience Manager Guides. (14537)
- A personalização de modelos de email para fluxo de trabalho de revisão não funciona com sobreposição. (13954)

## Problema conhecido

A Adobe identificou o seguinte problema conhecido para a versão 2024.2.0:

- A versão 1.0 não é exibida na interface do usuário do arquivo DITA duplicado.
- A propagação de metadados de ativos não funciona para a versão 2024.2.0 com o microsserviço ativado para qualquer predefinição.
