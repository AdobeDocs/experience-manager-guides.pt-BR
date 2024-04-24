---
title: Notas de versão | Correção de problemas nos Guias da Adobe Experience Manager, versão 2024.4.0
description: Saiba mais sobre as correções de erros na versão 2024.04.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 4c7421391922d276ef82515fb4b1cbdc2397e4ce
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 0%

---


# Correção de problemas na versão 2024.04.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2024.04.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão 2024.04.0](whats-new-2024-04-0.md).

Saiba mais sobre [instruções de atualização da versão 2024.04.0](upgrade-instructions-2024-04-0.md).

## Criação  

- A variável **Copiar** falha ao duplicar as pastas vazias no Adobe Experience Manager as a Cloud Service. (15353)
- O Editor da Web não pode carregar arquivos .pptx. (14837)
- Ao localizar um texto no Editor da Web, o cursor retorna à primeira ocorrência do texto pesquisado, pressionando a tecla Enter. (14820)
- O salvamento automático causa vários problemas, reposiciona o cursor e requer cliques manuais no documento. (14253)
- Os resultados da pesquisa são desativados após a abertura de um arquivo encontrado por meio de **Localizar e substituir**. (12142)
- Na exibição de código-fonte, `</conbody>` é ocasionalmente inserido em locais incorretos. (11305)
- No Editor de XML, o recurso de dica de ferramenta falha ao atualizar o campo Origem. (15847)
- A variável **Compartilhar link UUID** O recurso não funciona para imagens no Adobe Experience Manager. (15598)
- Problemas de texto sobrepostos ocorrem em `<reltable>` e `<fig>` específicos. (15238)
- Problemas de cintilação ocorrem no **Atributos** painel. (15237)
- Ao excluir um caractere ou palavra dentro do conteúdo, o cursor salta entre os elementos do bloco. (15224)
- A variável **Atributos** painel não é exibido na exibição Código-fonte do Editor da Web. (14387)
- Espaços indesejados e não separáveis são adicionados durante a edição no final de uma tag no Editor da Web. (11786)
- O conteúdo é excluído ao corrigir os erros de ortografia em arquivos DITA. (11610)


## Publicação

- A geração de saída do site AEM falha quando a variável **Excluir site órfão** está ativada. (15896)
- A funcionalidade de edição não funciona ao adicionar arquivos à Coleção de mapas. (15813)
- Na saída JSON, os metadados do mapa DITA ou dos tópicos não são propagados para os arquivos de saída JSON. (15713)
- Falha na publicação do PDF nativo ao renomear a predefinição. (15662)
- A variável **sourcePath** propriedade está incorreta na saída do site AEM publicada. (15502)
- A seleção e a personalização das variáveis de idioma não estão funcionando corretamente na Predefinição de saída de PDF nativo. (15399)
- A geração de PDF nativo falha ao usar um modelo com uma folha de estilos ou layout grande. (15344)
- O conteúdo não é renderizado corretamente na saída publicada se `<conref>` é usado com um caminho absoluto.
- A redução de URL do AEM Sites não está funcionando devido a conflitos entre as `fmdita rewriter` e `ResourceResolver`. (14793)
- A variável **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;**, e **chunk=&quot;to-content&quot;** Os atributos aparecem independentemente na saída do AEM Sites. (14442)
- Se uma pasta que contém mapas 2k estiver definida no caminho da pasta dentro de qualquer perfil de pasta, as alterações aplicadas à predefinição de saída falharão.(14852)

## Gerenciamento

- Não Fechado **Resolvedores de Recursos** causar o aumento da contagem de sessões e os erros PathNotFoundException após a versão de outubro de 2023 do Experience Manager Guides as a Cloud Service. (15604)
- O sinalizador de recurso **fmdita.useapproval** não está funcionando como esperado. (15310)
- A criação de uma linha de base usando a API do Java não funciona com a versão de junho de 2023 do Experience Manager Guides as a Cloud Service. (14787)
- A variável `/bin/fmdita/import` A API permanece presa na solicitação pendente indefinidamente quando os ativos de upload excedem 500 MB. (14743)

## Revisar

- A exclusão de nós de revisão interrompe a capacidade de abrir e exibir comentários no Adobe Experience Manager Guides. (15366)
- No Editor da Web, o painel Revisão é carregado lentamente. (14680)

## Tradução

- **Aceitar tradução** falha ao concluir a tradução de arquivos temporários. (14665)


