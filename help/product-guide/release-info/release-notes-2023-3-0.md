---
title: Notas de versão | Adobe Experience Manager Guides as a Cloud Service, versão de março de 2023
description: Versão de março do Adobe Experience Manager Guides as a Cloud Service
exl-id: 6a0bba92-7d7d-4b20-ad46-0eacc91268da
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Versão de março de 2023 do Adobe Experience Manager Guides as a Cloud Service

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão de março de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *AEM Guides as a Cloud Service*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão de março de 2023 do AEM Guides as a Cloud Service](whats-new-2023-3-0.md).

## Atualização para a versão de março de 2023

Atualize sua configuração atual do AEM Guides as a Cloud Service executando as seguintes etapas:

1. Confira o código Git do Cloud Services e alterne para a ramificação configurada no pipeline do Cloud Services correspondente ao ambiente que você deseja atualizar.
1. Atualize a propriedade `<dox.version>` no arquivo `/dox/dox.installer/pom.xml` do seu código Git do Cloud Services para 2023.3.242.
1. Confirme as alterações e execute o pipeline dos Serviços em nuvem para atualizar para a versão de março de 2023 do AEM Guides as a Cloud Service.

## Etapas para indexar o conteúdo existente (somente se você estiver em uma versão anterior à versão de setembro do AEM Guides as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa:

* Execute uma solicitação POST para o servidor (com autenticação correta) - `http://<server:port>/bin/guides/map-find/indexing`.
(Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados || Exemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação GET com a ID do trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Por exemplo: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com a versão de março de 2023 do AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | Não compatível | 2022 ou superior |
| | | |


### Conector de oxigênio

| Versão do AEM Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.03.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

* O processo de download do PDF não está funcionando adequadamente no Editor da Web. (11496)
* Saída JSON | Mapear metadados com o valor de propriedade como `"value in spaces and double quotes"` leva a um erro de publicação. (11438)
* A inserção de arquivos multimídia de áudio e vídeo falha no formato YouTube sob o ícone **Inserir multimídia**. (11320)
* O erro de validação ocorre quando um mapa é criado usando o modelo que tem um elemento de título especializado. (11212)
* PDF nativo | a nota de rodapé presente no cabeçalho da tabela leva a negrito e texto alinhado ao centro no rodapé da página correspondente na saída do PDF. (10610)
>[!NOTE]
>
>Para refletir a alteração do PDF nativo, exclua a pasta do PDF localizada em /content/dam/dita-templates e atualize para a build mais recente. (10610)

### Problema conhecido com a solução alternativa

A Adobe identificou o seguinte problema conhecido para a versão de março de 2023 do AEM Guides as a Cloud Service.

* Os usuários não podem salvar ou criar a versão de um ativo duplicado.

**Solução alternativa**: antes de fazer qualquer alteração no ativo duplicado, reprocesse-o da interface do usuário do Assets.
