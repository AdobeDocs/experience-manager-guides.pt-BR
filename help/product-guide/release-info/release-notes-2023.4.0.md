---
title: Notas de versão | Adobe Experience Manager Guides as a Cloud Service, versão de abril de 2023
description: Versão de abril de 2023 do Adobe Experience Manager Guides as a Cloud Service
exl-id: fa339eab-d3d0-4763-adbf-6411e39aa213
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# Versão de abril de 2023 do Adobe Experience Manager Guides as a Cloud Service

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão de abril de 2023 dos Guias do Adobe Experience Manager (mais tarde chamados de *Guias de AEM as a Cloud Service*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão de abril de 2023 do Guia do AEM as a Cloud Service](whats-new-2023.4.0.md).

## Atualização para a versão de abril de 2023

Atualize sua configuração as a Cloud Service dos Guias AEM atuais executando as seguintes etapas:

1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
2. Atualizar `<dox.version>` propriedade no `/dox/dox.installer/pom.xml` arquivo do seu código Git Cloud Service para 2023.4.249.
3. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de abril de 2023 do AEM Guides as a Cloud Service.

## Etapas para indexar o conteúdo existente (somente se você estiver em uma versão anterior à versão de setembro do AEM Guides as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa:

* Execute uma solicitação POST no servidor (com a autenticação correta) - `http://<server:port>/bin/guides/map-find/indexing`.
(Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados || Exemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Por exemplo: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com os Guias do AEM as a Cloud Service na versão de abril de 2023.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | Não compatível | 2022 ou superior |
| | | |


### Conector de oxigênio

| Versão do AEM Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |



## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

* PDF nativo | A publicação de conteúdo que tem uma classe de saída com colchetes() resulta em um congelamento da publicação. (11596)
* Ocorre um problema ao mover (arrastar e soltar) no lugar de um item de lista existente com o Controle de alterações ativado. (11570)
* Ocorre um problema ao mover (arrastar e soltar) como um novo item de lista com a opção Controlar alterações ativada. (11569)
* O recuo ou o recuo de itens de lista não funciona como esperado quando a opção Controlar alterações está ativada. (11568)
* Adicionar conteúdo em uma linha com a opção Controlar alterações ativada e desativar Controlar alterações não o desativa realmente. (11567)
* Dificuldade em arrastar e soltar um item de lista, o texto é movido no lugar do item de lista. (11566)
* A revisão concluída não abre no modo somente leitura. (11387)
* Problema ocorre na pesquisa do site AEM (não funciona além de 2-3 nós de nível). (11352)
* Ao criar no elemento exibido em verde (Controlar alterações), o novo conteúdo é exibido como rastrear alteração mesmo que a opção rastrear alteração esteja desativada. (7021)

### Problema conhecido com a solução alternativa

A Adobe identificou o seguinte problema conhecido para os Guias AEM as a Cloud Service na versão de abril de 2023.

* PDF nativo | Os metadados antigos não são preenchidos até que a predefinição de saída seja aberta explicitamente.
