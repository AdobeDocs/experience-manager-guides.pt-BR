---
title: Notas de versão | Instruções de atualização e problemas corrigidos nos Guias da Adobe Experience Manager, versão de outubro de 2023
description: Saiba mais sobre as correções de erros e como atualizar para a versão de outubro de 2023 do Adobe Experience Manager Guides as a Cloud Service
exl-id: 536d2ec2-31a0-4533-9c29-16a27525acca
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 1%

---

# Versão de outubro de 2023 do Adobe Experience Manager Guides as a Cloud Service

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão de outubro de 2023 dos Guias da Adobe Experience Manager (mais tarde chamados de *Guias de AEM as a Cloud Service*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão de outubro de 2023 do AEM Guides as a Cloud Service](whats-new-2023.10.0.md).

## Atualização para a versão de outubro de 2023

Atualize sua configuração as a Cloud Service dos Guias AEM atuais executando as seguintes etapas:

1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
2. Atualizar `<dox.version>` propriedade no `/dox/dox.installer/pom.xml` arquivo do seu código Git Cloud Service para 2023.10.0.373.
3. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de outubro de 2023 do AEM Guides as a Cloud Service.

## Etapas para ativar o acionador de um script por meio de um servlet

(Somente se você estiver em uma versão anterior à versão de junho de 2023 dos Guias do AEM as a Cloud Service)

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

Na resposta anterior, JSON, a chave `lockNodePath` mantém o caminho para o nó criado no repositório que aponta para a tarefa enviada. Ela será excluída automaticamente quando o trabalho for concluído. Até lá, é possível consultar esse nó para saber o status atual do trabalho.

Aguarde até que esse trabalho seja concluído antes de prosseguir para as próximas etapas.

>[!NOTE]
>
> Você deve verificar se o nó ainda está presente e o status do trabalho.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Etapas para pós-processar o conteúdo existente para usar o relatório de link corrompido

(Somente se você estiver em uma versão anterior à versão de junho de 2023 dos Guias do AEM as a Cloud Service)

Execute as seguintes etapas para pós-processar o conteúdo existente e usar o novo relatório de link desfeito:

1. (Opcional) Se houver mais de 100.000 arquivos DITA no sistema, atualize o `queryLimitReads` em `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` para um valor maior (qualquer valor maior que o número de ativos presentes, por exemplo, 200.000) e reimplante.

   - Use as instruções fornecidas no *Substituições de configuração* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service, para criar o arquivo de configuração.
   - No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar a opção queryLimitReads:

     | PID | Chave de propriedade | Valor da propriedade |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 Valor padrão: 100000 |

1. Execute uma solicitação POST no servidor (com a autenticação correta) - `http://<server:port>//bin/guides/reports/upgrade`.

1. A API retorna um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Quando o trabalho for concluído, a solicitação do GET anterior responderá com êxito. Se a tarefa falhar por algum motivo, a falha poderá ser vista nos logs do servidor.

1. Reverter para o valor padrão ou existente anterior de `queryLimitReads` se você o alterou na etapa 1.

## Etapas para indexar o conteúdo existente para usar a nova localização e substituição e lista de tópicos na guia Relatórios:

(Somente se você estiver em uma versão anterior à versão de junho de 2023 dos Guias do AEM as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa e da lista de tópicos na guia relatórios:

1. Executar uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los. Por padrão, todos os mapas serão indexados \|\| Por exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Você também pode passar uma pasta raiz para indexar os mapas DITA de uma pasta específica (e suas subpastas). Por exemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observe que se os parâmetros de caminhos e de raiz forem transmitidos, somente o parâmetro de caminhos será considerado.

1. A API retorna um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Quando o trabalho for concluído, a solicitação do GET anterior responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com os Guias do AEM as a Cloud Service na versão de outubro de 2023.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.10.0 | Não compatível | 2022 ou superior |
| | | |


### Conector de oxigênio

| Versão do AEM Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.10.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |


### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| O AEM guia o pacote de conteúdo dos componentes para o Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Criação  

- As horas da tarde não estão definidas no **Data** para criar linhas de base. (12712)
- Não é possível colar o código JSON no `<codeblock>` elemento do Editor da Web. (12326)
- Alterações de versão não salvas e os indicadores para elas não são exibidos para arquivos grandes. (11784)
- Ao editar no idioma coreano, o primeiro caractere é alterado para o padrão. (10049)


### Publicação

- PDF nativo | A ordem dos tópicos não é corrigida quando a saída de PDF é gerada. (13157)
- PDF nativo| Nenhuma tag de estilo padrão disponível para `<p>`elemento. (12559)
- PDF nativo | Os estilos em linha aplicados à região de conteúdo não se aplicam aos tópicos em primeiro e segundo plano. (13510)
- A variável `DeliveryTarget` O atributo não é propagado ao gerar a saída do site AEM.  (13132)
- A variável **Publish** O fluxo de trabalho fica travado ao gerar a saída do site AEM para conteúdo com determinados erros. (12000)

### Gerenciamento

- O Histórico de versões não é exibido mesmo se a variável `dc:format` A propriedade não está presente para um ativo. (10463)


### Análise

- A opção Revisar um tópico mostra comentários incorretos. (13453)



### Tradução

- A linha de base exportada do **Tradução** O painel falha e não abre no idioma de destino. (13466)

- Novos projetos de tradução são criados em vez de adicionar novos trabalhos aos projetos de tradução existentes selecionados.  (10214)

## Problema conhecido

O Adobe identificou o seguinte problema conhecido para a versão de outubro de 2023.

- Falha na republicação do fragmento de conteúdo.
