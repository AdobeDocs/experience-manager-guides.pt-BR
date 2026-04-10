---
title: Configuração adicional para atualizar o serviço em nuvem
description: Saiba mais sobre a configuração adicional para atualizar o serviço em nuvem
exl-id: 3d60d06b-ce50-4948-b50d-bd373051d055
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Configuração adicional para atualizar o AEM Guides as Cloud Service

>[!INFO]
>
>Este artigo se aplica se você tiver definido as configurações personalizadas do perfil de pasta (`ui_config.json`). Após cada atualização, revise e modifique as configurações conforme necessário para garantir a compatibilidade com as alterações mais recentes.

Dependendo da versão da qual você está atualizando, etapas de configuração adicionais podem ser necessárias para integrar as alterações introduzidas nas versões mais recentes do Cloud Service.

Algumas configurações se aplicam somente a versões específicas. Consulte as seções de configuração abaixo e aplique as configurações necessárias aplicáveis à sua configuração.

## Etapas para aplicar filtros de pesquisa em arquivos DITAVAL para todas as predefinições de saída

Para garantir que os filtros funcionem corretamente, atualize o ui_config.json. Altere as propriedades listadas em **browseFilters** > **Arquivos não DITA** > **Arquivos Ditaval** conforme mostrado abaixo:

```
{
  "title": "Ditaval Files",
  "property": "LOWER_NAME",
  "operation": "like",
  "value": ".ditaval"
}
```

## Etapas para executar a migração em árvore B para fragmentos de conteúdo

Se as referências não forem exibidas para fragmentos de conteúdo, você poderá optar por executar o trabalho de migração:

PUBLICAÇÃO:

```
http://localhost:4503/bin/guides/script/start?jobType=cf-reference-store-btree-migration
```


Resposta:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886",
"status": "SCHEDULED"
}
```

Na resposta anterior, JSON, a chave `lockNodePath` contém o caminho para o nó criado no repositório, que aponta para o trabalho enviado. Ele será excluído automaticamente quando o trabalho for concluído. Você pode consultar esse nó para obter o status do job.

Aguarde até que esse trabalho seja concluído antes de prosseguir para as próximas etapas.

>[!NOTE]
>
>Você deve verificar se o nó ainda está presente e o status do trabalho.

GET:

```
http://<aem_domain>/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886.json
```

## Etapas para lidar com o conflito `'fmdita rewriter'`

O Experience Manager Guides tem um módulo [**personalizado de reescrita do sling**](../cs-install-guide/conf-output-generation.md#custom-rewriter) para manipular os links gerados no caso de mapas cruzados (links entre os tópicos de dois mapas diferentes).

Se você tiver outro reescritor sling personalizado em sua base de código, use um valor de `'order'` maior que 50, pois o reescritor Experience Manager Guides sling usa `'order'` 50. Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de regravação de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta atualização, como o valor de `'order'` é alterado de 1000 para 50, você precisa mesclar o reescritor personalizado existente, se houver, com `fmdita-rewriter`.

## Configurações aplicáveis às versões anteriores a junho de 2023

As seguintes configurações são necessárias somente se estiver usando uma versão do Experience Manager Guides as a Cloud Service lançada antes de junho de 2023. Expanda as seções relevantes abaixo para aplicar as configurações necessárias e garantir a compatibilidade com as atualizações necessárias.

+++Etapas para indexar o conteúdo existente para usar a nova localização e substituição e lista de tópicos na guia Relatórios
Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa e da lista de tópicos na guia relatórios:

1. Execute uma solicitação POST para o servidor (com autenticação correta) - `http://<server:port>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los, por padrão, todos os mapas são indexados|| Exemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Você também pode passar uma pasta raiz para indexar os mapas DITA de uma pasta específica (e suas subpastas). Por exemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observe que se os parâmetros de caminhos e de raiz forem transmitidos, somente o parâmetro de caminhos será considerado.

1. A API retorna um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com a ID do trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Por exemplo: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Quando o trabalho for concluído, a solicitação anterior do GET responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

+++

+++Etapas para pós-processar o conteúdo existente para usar o relatório de link corrompido 
Execute as seguintes etapas para pós-processar o conteúdo existente e usar o novo relatório de link desfeito:

1. (Opcional) Se houver mais de 100.000 arquivos DITA no sistema, atualize o `queryLimitReads` e o `queryLimitInMemory` em `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` para um valor maior (qualquer valor maior que o número de ativos presentes, por exemplo, 200.000) e reimplante.

   - Use as instruções fornecidas na seção *Substituições de configuração* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service para criar o arquivo de configuração.
   - No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar a opção `queryLimitReads` e `queryLimitInMemory`:

     | PID | Chave de propriedade | Valor de propriedade |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 Valor padrão: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valor: 200000 Valor padrão: 100000 |

1. Execute uma solicitação POST para o servidor (com autenticação correta) - `http://<server>//bin/guides/reports/upgrade`.

1. A API retorna um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação GET com a ID do trabalho para o mesmo ponto de extremidade - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por exemplo: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Quando o trabalho for concluído, a solicitação anterior do GET responderá com êxito. Se a tarefa falhar por algum motivo, a falha poderá ser vista nos logs do servidor.

1. Reverta para o valor padrão ou existente anterior de `queryLimitReads` se você o alterou na etapa 1.

+++

+++Etapas para ativar o acionador de um script por meio de um servlet
Após concluir a instalação, é possível optar por iniciar o trabalho de tradução:

PUBLICAÇÃO:

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

Na resposta JSON anterior, a chave `lockNodePath` contém o caminho para o nó criado no repositório que aponta para o trabalho enviado. Ela é automaticamente excluída quando o trabalho é concluído e, em seguida, você pode consultar esse nó para obter o status do trabalho.

Aguarde até que esse trabalho seja concluído antes de prosseguir para as próximas etapas.

>[!NOTE]
>
> Você deve verificar se o nó ainda está presente e o status do trabalho.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

+++
