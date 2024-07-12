---
title: Notas de versão | Correção de problemas na versão 2024.4.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2024.04.0 do Adobe Experience Manager Guides as a Cloud Service.
exl-id: 35351d71-7739-4ad3-a063-67adf64906bf
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 0%

---

# Correção de problemas na versão 2024.04.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2024.04.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2024.04.0](whats-new-2024-04-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2024.04.0](upgrade-instructions-2024-04-0.md).

## Criação  

- A função **Copiar** não duplica as pastas vazias no Adobe Experience Manager as a Cloud Service. (15353)
- O Editor da Web não pode carregar arquivos .pptx. (14837)
- Ao localizar um texto no Editor da Web, o cursor retorna à primeira ocorrência do texto pesquisado, pressionando a tecla Enter. (14820)
- O salvamento automático causa vários problemas, reposiciona o cursor e requer cliques manuais no documento. (14253)
- Os resultados da pesquisa são desabilitados após a abertura de um arquivo encontrado por meio do **Localizar e Substituir** global. (12142)
- Na exibição de origem, `</conbody>` é ocasionalmente inserido em locais incorretos. (11305)
- No Editor XML, o recurso de dica de ferramenta falha ao atualizar o campo Source. (15847)
- O recurso **Compartilhar link de UUID** não está funcionando para as imagens no Adobe Experience Manager. (15598)
- Problemas de texto sobrepostos ocorrem nas marcas `<reltable>` e `<fig>`. (15238)
- Problemas de cintilação ocorrem no painel **Atributos**. (15237)
- Ao excluir um caractere ou palavra dentro do conteúdo, o cursor salta entre os elementos do bloco. (15224)
- O painel **Atributos** não é exibido no modo de exibição Source do Editor da Web. (14387)
- Espaços indesejados e não separáveis são adicionados durante a edição no final de uma tag no Editor da Web. (11786)
- O conteúdo é excluído ao corrigir os erros de ortografia em arquivos DITA. (11610)


## Publicação

- Falha na geração de saída do Site AEM quando a opção **Excluir Site Órfão** está habilitada. (15896)
- A funcionalidade de edição não funciona ao adicionar arquivos à Coleção de mapas. (15813)
- Na saída JSON, os metadados do mapa DITA ou dos tópicos não são propagados para os arquivos de saída JSON. (15713)
- Falha na publicação do PDF nativo ao renomear a predefinição. (15662)
- A propriedade **sourcePath** está incorreta na saída do site AEM publicada. (15502)
- A seleção e a personalização das variáveis de idioma não estão funcionando corretamente na Predefinição de saída de PDF nativo. (15399)
- A geração de PDF nativo falha ao usar um modelo com uma folha de estilos ou layout grande. (15344)
- O conteúdo não é renderizado corretamente na saída publicada se `<conref>` for usado com um caminho absoluto.
- A redução de URL do AEM Sites não está funcionando devido a conflitos entre `fmdita rewriter` e `ResourceResolver`. (14793)
- Os atributos **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** e **chunk=&quot;to-content&quot;** aparecem independentemente na saída do AEM Sites. (14442)
- Se uma pasta que contém mapas 2k estiver definida no caminho da pasta dentro de qualquer perfil de pasta, as alterações aplicadas à predefinição de saída falharão.(14852)

## Gerenciamento

- **Resolvedores de Recursos** não fechados causam um aumento na contagem de sessões e erros de PathNotFoundException após a versão de outubro de 2023 do Experience Manager Guides as a Cloud Service. (15604)
- O sinalizador de recurso **fmdita.useapproval** não está funcionando como esperado. (15310)
- A criação de uma linha de base usando a API do Java não funciona com a versão de junho de 2023 do Experience Manager Guides as a Cloud Service. (14787)
- A API `/bin/fmdita/import` permanece presa na solicitação pendente indefinidamente quando os ativos de carregamento excedem 500 MB. (14743)

## Revisar

- A exclusão de nós de revisão interrompe a capacidade de abrir e exibir comentários no Adobe Experience Manager Guides. (15366)
- No Editor da Web, o painel Revisão é carregado lentamente. (14680)

## Tradução

- **Aceitar tradução** falha ao concluir a tradução de arquivos temporários. (14665)
