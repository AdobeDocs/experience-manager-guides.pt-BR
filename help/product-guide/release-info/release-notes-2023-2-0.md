---
title: Notas de versão | Adobe Experience Manager Guides as a Cloud Service, versão de fevereiro de 2023
description: Versão de fevereiro do Adobe Experience Manager Guides as a Cloud Service
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 0%

---

# Versão de fevereiro de 2023 do Adobe Experience Manager Guides as a Cloud Service

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão de fevereiro de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *AEM Guides as a Cloud Service*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão de fevereiro de 2023 do AEM Guides as a Cloud Service](whats-new-2023-2-0.md).

## Atualização para a versão de fevereiro de 2023

Atualize sua configuração atual do AEM Guides as a Cloud Service executando as seguintes etapas:
1. Confira o código Git do Cloud Services e alterne para a ramificação configurada no pipeline do Cloud Services correspondente ao ambiente que você deseja atualizar.
2. Atualize a propriedade `<dox.version>` no arquivo `/dox/dox.installer/pom.xml` do seu código Git do Cloud Services para 2023.2.235.
3. Confirme as alterações e execute o pipeline dos Serviços em nuvem para atualizar para a versão de fevereiro de 2023 do AEM Guides as a Cloud Service.

## Etapas para indexar o conteúdo existente (somente se você estiver em uma versão anterior à versão de setembro do AEM Guides as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa:

* Execute uma solicitação POST para o servidor (com autenticação correta) - `http://<server:port>/bin/guides/map-find/indexing`.
(Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados || Exemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação GET com a ID do trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Por exemplo: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com a versão de fevereiro de 2023 do AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | Não compatível | 2022 ou superior |
| | | |

*A linha de base e as condições criadas no AEM são compatíveis com as versões do FMPS a partir de 2020.2.

### Conector de oxigênio

| Versão do AEM Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |  |  |  |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Criação

* As alterações no html do Editor da Web causam problemas com `<dl>` e `<dlentry>`. (11024)
* Alguns atributos não estão sendo tratados como condicionais e estão causando problemas. (10895)
* Três níveis ou mais aninhados `<indexterm>` não estão aninhados na exportação nativa do PDF. (10799)
* O conteúdo desaparece no corpo de uma tarefa ao alternar da exibição Autor para Source. (10735)
* Comentários de revisão são colocados fora do lugar em uma tarefa de revisão. (10625)
* **Desfazer** ou **Refazer** não está funcionando corretamente em alguns arquivos. (10373)
* Os metadados personalizados não são mantidos na ação de copiar e colar. (10367)
* A opção Desfazer no Editor de XML leva o usuário para a parte superior da página. (10091)
* As propriedades do nó são removidas após a operação de copiar e colar de um ativo. (10053)
* O mimeType é codificado para criação e atualização de ativos DITA. (8979)
* O nome do criador de versão no Histórico de versão é &quot;fmdita-serviceuser&quot; para os arquivos carregados pela interface do usuário do Assets. (8910)
* Os fragmentos de conteúdo não podem ser copiados e colados quando o AEM Guides está instalado na nuvem. (11315)
* O navegador (Editor da Web) congela ao carregar conteúdo com um esquema personalizado. (11211)

### Gerenciamento

* Copiar um ativo de mapa DITA (da interface do usuário do Assets ) causa linhas de base incorretas no ativo copiado. (11218)
* A mensagem de aviso não é exibida no upload de um arquivo maior do que o limite permitido no AEM (2 GB por padrão). (10817)
* Editor da Web - Linha de base | O comportamento da coluna Mais recente é diferente no novo painel da linha de base no Editor da Web. (10808)
* Tradução | A tarefa de tradução não é iniciada devido a /libs/fmdita/i18n/ja.json inválido. (10543)
* Tradução | Ocorre um erro em um projeto de tradução de escopo criado a partir do painel de tradução (Tradução humana). (10526)
* Tradução | O pós-processamento está bloqueado para toda a pasta de idioma cujos ativos estão presentes em um projeto de tradução ativo. (10332)
* Vários pop-ups são exibidos para qualquer ativo se a versão for alterada e salva no editor de linha de base. (10399)
* Vazamento da Sessão ocorre em `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### Publicação

* A regeneração de tópico não está funcionando para alguns cenários. (10635)
* O Publishlistener não exibe os dados solicitados em logs de informações e também contém alguns logs de lixo eletrônico.(10567)
* PDF nativo | Ao criar uma predefinição de saída com a opção &quot;Adicionar ao perfil de pasta&quot;, a geração de PDF falha com uma exceção de ponteiro nulo. (10950)
* PDF nativo | Ocorrem problemas ao girar o cabeçalho da tabela. (10555)
* PDF nativo | `<indexterm>` aninhados não estão aninhados na exportação nativa do PDF. (10521)
* PDF nativo | Os tópicos aninhados ref nos apêndices são todos transformados em h1 no HTML temporário. (10454)
* Falha na publicação da linha de base para o PDF gerado usando o FrameMaker Publishing Server 2020. (10551)
* PDF nativo | Adicionar `xref` a uma imagem não renderiza a imagem no PDF gerado. (11346)
* PDF nativo | A tag de imagem adiciona o atributo display-inline a todas as imagens. (10653)
* PDF nativo | Comentários de rascunho são ocultos por padrão na saída gerada. (10560)
* PDF nativo | navtitle não é homenageado por topichead. (10509)
