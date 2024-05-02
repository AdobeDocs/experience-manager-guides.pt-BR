---
title: Notas de versão | Instruções de atualização e problemas corrigidos nos Guias da Adobe Experience Manager, versão 2024.04.0
description: Saiba mais sobre a matriz de compatibilidade e como atualizar para a versão 2024.04.0 dos Guias do Adobe Experience Manager as a Cloud Service.
exl-id: deca46e5-12cc-497f-84af-61ee02da3d65
source-git-commit: 989f1628adf417167525a068845203380573b077
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---

# Instruções de atualização para a versão 2024.04.0

Este artigo aborda as instruções de atualização e a matriz de compatibilidade da versão 2024.04.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão 2024.04.0](whats-new-2024-04-0.md).

Para obter a lista de problemas corrigidos nessa versão, consulte [Correção de problemas na versão 2024.04.0](fixed-issues-2024-04-0.md).

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade para os aplicativos de software compatíveis com a versão 2024.04.0 dos Guias do Experience Manager as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.04.0 | Não compatível | 2022 ou superior |
| | | |


### Conector de oxigênio

| Versão do Experience Manager Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2024.04.0 | 3.5-uuid 1 | 3.5-uuid 1 | 2,3 | 2,3 |
|  |  |  |  |


### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| Experience Manager Guias Componentes Pacote de conteúdo para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Atualização para a versão 2024.04.0

O Experience Manager Guides é atualizado automaticamente após o upgrade da versão atual (mais recente) do Experience Manager as a Cloud Service.

>[!NOTE]
>
> Depois de começar a usar a versão atual (mais recente), compare todas as configurações substituídas com as mais recentes para obter os recursos mais recentes:
>- ui_config.json (pode ter sido definido em perfis de pasta)



Execute as seguintes etapas para os Guias do Experience Manager as a Cloud Service se ainda não tiver feito isso antes na sua versão existente:

### Etapas para ativar o acionador de um script por meio de um servlet

(Somente se você estiver em uma versão anterior à versão de junho de 2023 do Experience Manager Guides as a Cloud Service)

Após concluir a instalação, você pode optar por APRESENTAR o acionador para iniciar o trabalho de tradução:

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Resposta:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

Na resposta anterior, JSON, a chave `lockNodePath` mantém o caminho para o nó criado no repositório que aponta para a tarefa enviada. Ela é automaticamente excluída quando o trabalho é concluído e, em seguida, você pode consultar esse nó para obter o status do trabalho.

Aguarde até que esse trabalho seja concluído antes de prosseguir para as próximas etapas.

>[!NOTE]
>
> Você deve verificar se o nó ainda está presente e o status do trabalho.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

### Etapas para pós-processar o conteúdo existente para usar o relatório de link corrompido

(Somente se você estiver em uma versão anterior à versão de junho de 2023 do Experience Manager Guides as a Cloud Service)

Execute as seguintes etapas para pós-processar o conteúdo existente e usar o novo relatório de link desfeito:

1. (Opcional) Se houver mais de 100.000 arquivos DITA no sistema, atualize o `queryLimitReads` e `queryLimitInMemory` em `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` para um valor maior (qualquer valor maior que o número de ativos presentes, por exemplo, 200.000) e reimplante.

   - Use as instruções fornecidas no *Substituições de configuração* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service, para criar o arquivo de configuração.
   - No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar o `queryLimitReads` e `queryLimitInMemory` opção:

     | PID | Chave de propriedade | Valor de propriedade |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 Valor padrão: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valor: 200000 Valor padrão: 100000 |

1. Execute uma solicitação POST no servidor (com a autenticação correta) - `http://<server>//bin/guides/reports/upgrade`.

1. A API retorna um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por exemplo: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Quando o trabalho for concluído, a solicitação do GET anterior responderá com êxito. Se a tarefa falhar por algum motivo, a falha poderá ser vista nos logs do servidor.

1. Reverter de volta para o valor padrão ou existente anterior de `queryLimitReads` se você o alterou na etapa 1.

### Etapas para indexar o conteúdo existente para usar a nova localização e substituição e lista de tópicos na guia Relatórios:

(Somente se você estiver em uma versão anterior à versão de junho de 2023 do Experience Manager Guides as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa e da lista de tópicos na guia relatórios:

1. Execute uma solicitação POST no servidor (com a autenticação correta) - `http://<server:port>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas são indexados|| Por exemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Você também pode passar uma pasta raiz para indexar os mapas DITA de uma pasta específica (e suas subpastas). Por exemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observe que se os parâmetros de caminhos e de raiz forem transmitidos, somente o parâmetro de caminhos será considerado.

1. A API retorna um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Por exemplo: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Quando o trabalho for concluído, a solicitação do GET anterior responderá com êxito. Se o trabalho falhar por algum motivo, a falha poderá ser vista nos logs do servidor.

### Etapas para lidar com o `'fmdita rewriter'` conflito

Os Guias do Experience Manager têm um [**reescrita personalizada do sling**](../cs-install-guide/conf-output-generation.md#custom-rewriter) módulo para tratamento de ligações geradas em caso de mapas cruzados (ligações entre os tópicos de dois mapas diferentes).

Se você tiver outra reescrita de sling personalizada em sua base de código, use uma `'order'` valor maior que 50, como o sling rewriter dos Guias do Experience Manager usa `'order'` 50. Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de reescrita de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante essa atualização, desde que o `'order'` for alterado de 1000 para 50, será necessário mesclar o reescritor personalizado existente, se houver, com `fmdita-rewriter`.
