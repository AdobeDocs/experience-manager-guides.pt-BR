---
title: Notas de versão | Instruções de atualização e problemas corrigidos nos Guias da Adobe Experience Manager, versão de fevereiro de 2024
description: Saiba mais sobre as correções de erros e como atualizar para a versão de fevereiro de 2024 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: a04b1aa28bda0c0da1770eaff8b385721e20654d
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 0%

---

# Lançamento do Adobe Experience Manager Guides as a Cloud Service de fevereiro de 2024

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão de fevereiro de 2024 do Adobe Experience Manager Guides as a Cloud Service (mais tarde conhecido como *Guias do Experience Manager as a Cloud Service*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão de fevereiro de 2024 do Experience Manager Guides as a Cloud Service](whats-new-2024.02.0.md).

## Atualização para a versão de fevereiro de 2024

Atualize sua configuração as a Cloud Service do Experience Manager Guides executando as seguintes etapas:

1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
2. Atualizar `<dox.version>` propriedade no `/dox/dox.installer/pom.xml` arquivo do seu código Git Cloud Service para 2024.02.0.15.
3. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de fevereiro de 2024 do as a Cloud Service Guias de Experience Manager.

## Etapas para ativar o acionador de um script por meio de um servlet

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

Na resposta anterior, JSON, a chave `lockNodePath` mantém o caminho para o nó criado no repositório que aponta para a tarefa enviada. Ela será excluída automaticamente quando o trabalho for concluído e, em seguida, você poderá consultar esse nó para saber o status do trabalho.

Aguarde até que esse trabalho seja concluído antes de prosseguir para as próximas etapas.

>[!NOTE]
>
> Você deve verificar se o nó ainda está presente e o status do trabalho.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Etapas para pós-processar o conteúdo existente para usar o relatório de link corrompido

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

## Etapas para indexar o conteúdo existente para usar a nova localização e substituição e lista de tópicos na guia Relatórios:

(Somente se você estiver em uma versão anterior à versão de junho de 2023 do Experience Manager Guides as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa e da lista de tópicos na guia relatórios:

1. Execute uma solicitação POST no servidor (com a autenticação correta) - `http://<server:port>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados|| Por exemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Por exemplo: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Quando o trabalho for concluído, a solicitação do GET anterior responderá com êxito. Se o trabalho falhar por algum motivo, a falha poderá ser vista nos logs do servidor.

1. Reverta para o valor padrão ou existente anterior de queryLimitReads, se você o alterou na etapa 1.

## Etapas para lidar com o `'fmdita rewriter'` conflito

Os Guias do Experience Manager têm um [**reescrita personalizada do sling**](../cs-install-guide/conf-output-generation.md#custom-rewriter) módulo para tratamento de ligações geradas em caso de mapas cruzados (ligações entre os tópicos de dois mapas diferentes).

Se você tiver outra reescrita de sling personalizada em sua base de código, use uma `'order'` valor maior que 50, como o sling rewriter dos Guias do Experience Manager usa `'order'` 50.  Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de reescrita de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante essa atualização, desde que o `'order'` for alterado de 1000 para 50, será necessário mesclar o reescritor personalizado existente, se houver, com `'fmdita-rewriter'`.


## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade para os aplicativos de software compatíveis com a versão as a Cloud Service dos Guias do Experience Manager de fevereiro de 2024.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.02.0 | Não compatível | 2022 ou superior |
| | | |


### Conector de oxigênio

| Versão do Experience Manager Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2024.02.0 | 3.1-uuid.17 | 3.1-uuid.17 | 2,3 | 2,3 |
|  |  |  |  |


### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| Experience Manager Guias Componentes Pacote de conteúdo para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Criação  

- A verificação ortográfica no Editor não permite a seleção de sugestões. (15045)
- O botão de navegação global não está funcionando e o painel não é carregado. (14968)
- No Editor da Web, o recurso de mapa de download não aciona uma notificação pop-up quando está pronto para download. (14626)
- No Editor da Web, o recurso de download de mapa falha ao baixar um mapa com linha de base. (14622)
- Erro de DTD inválido no Experience Manager Guides as a Cloud Service versão 2310. (14482)
- Arrastar um tópico de glossário do repositório para um mapa de glossário cria `topicref`. (10767)
- O Editor da Web é desinstalado após a reinstalação do Adobe Experience Manager Guides versão 4.3.1. (14519)
- O instalador da versão 4.3.1 encontra um conflito de filtro, resultando na substituição de `apps/cq/core/content/projects/properties`. (14517)
- A tela de visualização de trechos está congelada. (14840)

### Publicação

- Na publicação de PDF nativo, os atributos personalizados nas predefinições de condição não funcionam na publicação de PDF nativo. (14943)
- Não é possível adicionar um modelo personalizado do **Saídas** no Editor. (14846)
- **Site AEM** A predefinição não está funcionando devido a um caminho de modelo vazio. (14804)
- A regeneração do site AEM falha para mapas DITA com tópicos que contêm equações MathML. (14790)
- Na publicação de PDF nativo, a geração de PDF gera erros na obtenção de dependências para `Node.js` publicação. (14445)
- A predefinição de AEM não permite a seleção de um modelo fora do `/content` hierarquia no Editor da Web. (14260)
- Na saída do AEM Sites, o estilo ou as quebras de linha foram perdidas para o `<lines>` elemento com subelementos .(12542)
- Os metadados personalizados não estão disponíveis na saída final. (12116)
- Ao atualizar para a versão 4.3.1, ocorrem algumas exceções no nó PDF nativo. (14492)


### Gerenciamento

- **Filtro de Linha de Base** Os arquivos não estão funcionando com o Nome do arquivo no Editor da Web. (13486)
- Desativar a indexação do mapa DITA principal para obter um melhor desempenho pode afetar a funcionalidade de determinados recursos.(12213)
- Rótulos do `labels.json` arquivos aparecem em ordem aleatória no Editor da Web. (10508)

### Revisar

- O menu de contexto de clique com o botão direito do mouse não funciona para **Aceitar** ou **Rejeitar** rastrear alterações. (14607)
- Alternar para fechar tópicos DITA na Tela de revisão não funciona na versão 4.3.1 dos Guias do Adobe Experience Manager. (14537)
- A personalização de modelos de email para fluxo de trabalho de revisão não funciona com sobreposição. (13954)

## Problema conhecido

A Adobe identificou o seguinte problema conhecido para a versão de fevereiro de 2024:

- A versão 1.0 não é exibida na interface do usuário do arquivo DITA duplicado.
