---
title: Notas de versão | Instruções de atualização e problemas corrigidos no Adobe Experience Manager Guides, versão de junho de 2023
description: Saiba mais sobre as correções de erros e como atualizar para a versão de junho de 2023 do Adobe Experience Manager Guides as a Cloud Service
exl-id: df17ee33-9f50-4223-ab9f-a57a31097d22
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/LIY9wVDmvusGD-K-kyjK-lmzpyxJELj0mWzn9YoP0vw
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1169
ht-degree: 3%

---

# Versão de junho de 2023 do Adobe Experience Manager Guides as a Cloud Service

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão de junho de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *AEM Guides as a Cloud Service*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão de junho de 2023 do AEM Guides as a Cloud Service](whats-new-2023-6-0.md).

## Atualização para a versão de junho de 2023

Atualize sua configuração atual do AEM Guides as a Cloud Service executando as seguintes etapas:

1. Confira o código Git do Cloud Services e alterne para a ramificação configurada no pipeline do Cloud Services correspondente ao ambiente que você deseja atualizar.
2. Atualize a propriedade `<dox.version>` no arquivo `/dox/dox.installer/pom.xml` do seu código Git do Cloud Services para 2023.6.297.
3. Confirme as alterações e execute o pipeline dos Serviços em nuvem para atualizar para a versão de junho de 2023 do AEM Guides as a Cloud Service.

## Etapas para ativar o acionador de um script por meio de um servlet

Após concluir a instalação, você pode optar por APRESENTAR o acionador para iniciar o trabalho de tradução:

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

Na resposta JSON anterior, a chave `lockNodePath` contém o caminho para o nó criado no repositório que aponta para o trabalho enviado. Ela será excluída automaticamente quando o trabalho for concluído. Até lá, é possível consultar esse nó para saber o status atual do trabalho.

Aguarde até que esse trabalho seja concluído antes de prosseguir para as próximas etapas.

>[!NOTE]
>
> Você deve verificar se o nó ainda está presente e o status do trabalho.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Etapas para pós-processar o conteúdo existente para usar o relatório de link corrompido

(Somente se você estiver em uma versão anterior à versão de junho de 2023 do AEM Guides as a Cloud Service)

Execute as seguintes etapas para o pós-processamento do conteúdo existente e uso do novo relatório de link desfeito:

1. (Opcional) Se houver mais de 100.000 arquivos dita no sistema, atualize o `queryLimitReads` em `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` para um valor maior (qualquer valor maior que o número de ativos presentes, por exemplo, 200.000) e reimplante.

   - Use as instruções fornecidas na seção *Substituições de configuração* em Instalar e configurar o Adobe Experience Manager Guides
as a Cloud Service, para criar o arquivo de configuração.
   - No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar a opção queryLimitReads:

     | PID | Chave de propriedade | Valor de propriedade |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 Valor padrão: 100000 |

1. Execute uma solicitação POST para o servidor (com autenticação correta) - `http://<server:port>//bin/guides/reports/upgrade`.

1. A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com a ID do trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Quando o trabalho for concluído, a solicitação anterior do GET responderá com sucesso. Se o trabalho falhar por algum motivo, a falha poderá ser vista nos logs do servidor.

1. Reverta para o valor padrão ou existente anterior de `queryLimitReads` se você o alterou na etapa 1.

## Etapas para indexar o conteúdo existente para usar a nova localização e substituição e lista de tópicos na guia Relatórios:

(Somente se você estiver em uma versão anterior à versão de setembro de 2022 do AEM Guides as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa e da lista de tópicos na guia relatórios:

1. Execute uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados \|\| Por exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Você também pode passar uma pasta raiz para indexar os mapas DITA de uma pasta específica (e suas subpastas). Por exemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observe que se os parâmetros de caminhos e de raiz forem transmitidos, somente o parâmetro de caminhos será considerado.

1. A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com ID do trabalho para o mesmo ponto de extremidade - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Quando o trabalho for concluído, a solicitação anterior do GET responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com a versão de junho de 2023 do AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.06.0 | Não compatível | 2022 ou superior |
| | | |


### Conector de oxigênio

| Versão do AEM Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.06.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |


## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Criação

- Navtitle é removido do content33 ao alternar da exibição de layout para a exibição de autor ou fonte. (12174)
- Às vezes, ocorre um erro de aplicativo ao clicar em um mapa DITA. (11842)
- Editor da Web | O espaço sem quebra é adicionado no Editor de XML ao editar um tópico. (11786)
- Interface do usuário do ativo | Na exibição em Lista, as colunas disponíveis sobrepostas não são mescláveis. (11528)
- Keyref não foi resolvido na exibição de mapa. (11490)
- O menu superior não é exibido ao navegar pelo editor XML. (10868)
- `conref` na marca ph | A caixa de diálogo de navegação exibida está incorreta. (9481)
- Links locais para outros elementos não são resolvidos no Editor da Web. (8790)
- A função Matches() não funciona no recurso schematron. (11224)


### Gerenciamento

- A guia Relatórios na interface do Editor da Web não exibe a lista de tópicos de mapas DITA antigos criados antes da atualização 4.2. (11708)

- A funcionalidade do botão Fazer upload de arquivos na interrupção da interface do usuário do Assets na versão 4.2. (11633)

### Publicação

- A publicação no site do AEM falha ao ler arquivos temporários do pod que podem ter sido atualizados ou reiniciados. (12113)
- PDF nativo | A publicação de conteúdo que tem uma classe de saída com colchetes() resulta em um congelamento da publicação. (11936)
- Saída JSON | Mapear metadados com o valor de propriedade como `"value in spaces and double quotes"` leva a um erro de publicação. (11933)
- Editor da Web | O caminho de saída e o modelo não podem ser selecionados na Predefinição do AEM. (11530)
- PDF nativo | Os atributos personalizados não são propagados para o mecanismo temporário do HTML ou PDF. (DXML-12005)
- PDF nativo | Java OutOfMemoryError ocorre ao publicar conteúdo grande. (11789)
- Saída JSON | A propriedade `fmUuid` no nó jcr:content do JSON é diferente da &quot;id&quot; dentro do JSON. (11564)
- Saída JSON | Se o mapa e o tópico com o mesmo nome de arquivo estiverem presentes, o JSON do mapa será removido. (11524)
- PDF nativo | Xref está imprimindo o conteúdo do título do tópico href em vez do rótulo Xref. (11322)
- PDF nativo | Não é possível salvar as configurações do modelo do PDF. (10751)
- PDF nativo | O texto se estende além da largura da coluna ao incluir vários xrefs. (10876)
- PDF nativo O elemento | `<note>` `</note>` não gera um título de extensão extra de seu tipo. (10549)
- PDF nativo | Os metadados de idioma não podem ser definidos no PDF gerado para estar em conformidade com a WCAG 2.0. (12296)



### Tradução

- Após a versão na nuvem de fevereiro (2302), todo o conteúdo da tradução é exibido Fora de sincronia ou sem cópia. (11834)

### Revisar

- Nova interface de revisão | As condições destacadas e mostrar ocultar funcionam de forma diferente em relação ao Editor da Web. (11628)
