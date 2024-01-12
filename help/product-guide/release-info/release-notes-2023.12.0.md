---
title: Notas de versão | Instruções de atualização e problemas corrigidos nos Guias da Adobe Experience Manager, versão de dezembro de 2023
description: Saiba mais sobre as correções de erros e como atualizar para a versão de dezembro de 2023 do Adobe Experience Manager Guides as a Cloud Service.
feature: Release Notes
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 0%

---

# Lançamento do Adobe Experience Manager Guides as a Cloud Service de dezembro de 2023

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão de dezembro de 2023 do Adobe Experience Manager Guides as a Cloud Service (mais tarde conhecido como *Guias do Experience Manager as a Cloud Service*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão de dezembro de 2023 do Experience Manager Guides as a Cloud Service](whats-new-2023.12.0.md).

## Atualização para a versão de dezembro de 2023

Atualize sua configuração as a Cloud Service do Experience Manager Guides executando as seguintes etapas:

1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
2. Atualizar `<dox.version>` propriedade no `/dox/dox.installer/pom.xml` arquivo do seu código Git Cloud Service para 2023.12.0.15.
3. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de dezembro de 2023 do as a Cloud Service Guias de Experience Manager.

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

     | PID | Chave de propriedade | Valor da propriedade |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 Valor padrão: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valor: 200000 Valor padrão: 100000 |

1. Execute uma solicitação POST no servidor (com a autenticação correta) - `http://<server>//bin/guides/reports/upgrade`.

1. A API retorna um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por exemplo: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Quando o trabalho for concluído, a solicitação do GET anterior responderá com êxito. Se a tarefa falhar por algum motivo, a falha poderá ser vista nos logs do servidor.

1. Reverter para o valor padrão ou existente anterior de `queryLimitReads` se você o alterou na etapa 1.

## Etapas para indexar o conteúdo existente para usar a nova localização e substituição e lista de tópicos na guia Relatórios:

(Somente se você estiver em uma versão anterior à versão de junho de 2023 do Experience Manager Guides as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa e da lista de tópicos na guia relatórios:

1. Execute uma solicitação POST no servidor (com a autenticação correta) - `http://<server:port>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados|| Por exemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. Você também pode passar uma pasta raiz para indexar os mapas DITA de uma pasta específica (e suas subpastas). Por exemplo, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Observe que se os parâmetros de caminhos e de raiz forem transmitidos, somente o parâmetro de caminhos será considerado.

1. A API retorna um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)


1. Quando o trabalho for concluído, a solicitação do GET anterior responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Etapas para lidar com o `'fmdita rewriter'` conflito

Os Guias do Experience Manager têm um [**reescrita personalizada do sling**](../cs-install-guide/conf-output-generation.md#custom-rewriter) módulo para tratamento de ligações geradas em caso de mapas cruzados (ligações entre os tópicos de dois mapas diferentes).

Se você tiver outra reescrita de sling personalizada em sua base de código, use uma `'order'` valor maior que 50, como o sling rewriter dos Guias do Experience Manager usa `'order'` 50.  Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de reescrita de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante essa atualização, desde que o `'order'` for alterado de 1000 para 50, será necessário mesclar o reescritor personalizado existente, se houver, com `'fmdita-rewriter'`.


## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com os Guias do Experience Manager as a Cloud Service na versão de dezembro de 2023.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.12.0 | Não compatível | 2022 ou superior |
| | | |


### Conector de oxigênio

| Versão do Experience Manager Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.12.0 | 3.3-uuid.5 | 3.3-uuid.5 | 2,3 | 2,3 |
|  |  |  |  |


### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| Experience Manager Guias Componentes Pacote de conteúdo para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:



### Criação  

- A variável **Título** na guia Editor da Web é truncado após um ponto (.) “?”. (14372)
- As mensagens de erro para nomes de mapa duplicados na interface do usuário do Assets não foram atualizadas. (14320)
- Ocorre um erro na lógica de criação de versão durante a ação de arrastar e soltar ativos. (14291)
- O conteúdo reutilizável ignora as IDs do elemento. (14213)
- O controle de configuração a ser ocultado **Variáveis de idioma** painel em **Output** guia ausente. (14194)
- O Editor da Web emite erros de aplicação ao adicionar uma nova referência ou tópico usando um esquema especializado na exibição de layout. (14094)
- Um link de âncora para `<dlentry>` ou `<dt>` falha do elemento ao exibir o texto do link. (13543)
- A variável **Favoritos** falha ao carregar a coleção no Editor da Web. (13495)
- As citações exibem links não clicáveis quando criadas com uma ID exclusiva com espaços. (13447)
- No **Layout** exibição para um Bookmap, uso **Mover para a direita** para tornar um capítulo selecionado um subelemento não funciona. (12567)
- A janela Visualização do editor XML está truncada nos navegadores Google Chrome e Microsoft Edge. (10755)
- O Editor da Web não tem a capacidade de envolver um elemento dentro dos possíveis elementos principais. (8791)

### Publicação

- Os componentes da Fmdita têm um caminho codificado de `delegator.jsp`, evitando a sobreposição de componentes do AEM Sites. (13993)
- A exibição marcada do reator de PDF na saída de publicação de PDF nativo não está funcionando como esperado. (13622)
- A publicação do site AEM encontra um problema ao confirmar para o armazenamento de dados de mapas grandes com links de mesmo nível de escopo. (13531)
- Não é possível ativar um site usando o painel Publicação em massa dos guias do Experience Manager. (13439)
- A localização dos rótulos dos elementos não está funcionando corretamente na saída do AEM Sites. (12144)
- Ausente **ditaval** opção em predefinições de saída em nível de perfil de pasta criadas pela interface do usuário do Editor da Web. (11903)

### Gerenciamento

- Ambientes de nuvem AEM encontram uma exceção MongoWrite devido a nós de grande porte. (13509)

### Tradução

- A variável **Aceitar/Rejeitar** Os botões são exibidos incorretamente para a tradução humana aprovada automaticamente. (14318)
- Problemas de internacionalização (i18n) ocorrem durante a transformação de arquivos DITA em outros idiomas para páginas AEM. (14286)
- O conteúdo traduzido não é sincronizado dos projetos de tradução temporários, e o assistente de tradução do editor XML DITA é exibido incorretamente **Em andamento** status para trabalhos aprovados. (9938)

### Acessibilidade

- Não é possível navegar pela interface do usuário da tela de criação, pois o foco fica preso no editor de tópicos. (13517)

## Problema conhecido

O Adobe identificou o seguinte problema conhecido para a versão de dezembro de 2023:
- &quot;Obter erro de DTD inválido&quot; ocorre intermitentemente na atualização para a versão de dezembro de 2023.