---
title: Notas de versão | Instruções de atualização e problemas corrigidos no Adobe Experience Manager Guides, versão de setembro de 2023
description: Saiba mais sobre as correções de erros e como atualizar para a versão de setembro de 2023 do Adobe Experience Manager Guides as a Cloud Service
exl-id: 795b86a0-e763-404a-a4bb-35d3d2a42672
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 0%

---

# Versão de setembro de 2023 do Adobe Experience Manager Guides as a Cloud Service

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão de setembro de 2023 do Adobe Experience Manager Guides (mais tarde referido como *AEM Guides as a Cloud Service*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão de setembro de 2023 do AEM Guides as a Cloud Service](whats-new-2023-9-0.md).

## Atualização para a versão de setembro de 2023

Atualize sua configuração atual do AEM Guides as a Cloud Service executando as seguintes etapas:

1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
2. Atualize a propriedade `<dox.version>` no arquivo `/dox/dox.installer/pom.xml` do seu código Git Cloud Service para 2023.9.0.359.
3. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de setembro de 2023 do AEM Guides as a Cloud Service.

## Etapas para ativar o acionador de um script por meio de um servlet

(Somente se você estiver em uma versão anterior à versão de junho de 2023 do AEM Guides as a Cloud Service)

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

1. Execute uma solicitação POST no servidor (com autenticação correta) - `http://<server:port>//bin/guides/reports/upgrade`.

1. A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Quando a tarefa for concluída, a solicitação anterior do GET responderá com sucesso. Se o trabalho falhar por algum motivo, a falha poderá ser vista nos logs do servidor.

1. Reverta para o valor padrão ou existente anterior de `queryLimitReads` se você o alterou na etapa 1.

## Etapas para indexar o conteúdo existente para usar a nova localização e substituição e lista de tópicos na guia Relatórios:

(Somente se você estiver em uma versão anterior à versão de junho de 2023 do AEM Guides as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa e da lista de tópicos na guia relatórios:

1. Execute uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados \|\| Por exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Você também pode passar uma pasta raiz para indexar os mapas DITA de uma pasta específica (e suas subpastas). Por exemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observe que se os parâmetros de caminhos e de raiz forem transmitidos, somente o parâmetro de caminhos será considerado.

1. A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com ID de trabalho para o mesmo ponto de extremidade - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Quando o trabalho for concluído, a solicitação anterior do GET responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com a versão de setembro de 2023 do AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.09.0 | Não compatível | 2022 ou superior |
| | | |


### Conector de oxigênio

| Versão do AEM Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.09.0 | 3.1-uuid 17 | 3.1-uuid 17 | 2,3 | 2,3 |
|  |  |  |  |


### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| Pacote de conteúdo dos componentes do AEM Guides para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Criação  

- O arquivo de tópico não está desbloqueado no Editor da Web, embora as opções Desbloquear o arquivo e Não salvar estejam selecionadas. (12558)
- Não é possível fazer check-out de um arquivo no Editor da Web, apesar de escolher a opção NÃO para descartar as alterações antes do check-in. (12557)
- As dicas de ferramentas para os ícones Bloquear e Desbloquear arquivo na barra de ferramentas principal no Editor da Web não são consistentes com os ícones exibidos na Exibição do repositório.(12555)
- A opção Cancelar check-out e Desbloquear é exibida para um arquivo no Editor da Web que ainda não foi submetido a check-out na Exibição de mapa. (12556)
- Não é possível selecionar os ativos de PDF nos links &quot;topicref&quot; existentes. (12477).
- Na Exibição de repositório, os tópicos ou imagens não podem ser arrastados após o uso da funcionalidade Pesquisar/Filtrar. (12396)
- Os resultados da pesquisa são desativados no painel Localizar e substituir após abrir um arquivo pesquisado. (12142)
- A tecla numérica &quot;8&quot; no teclado lateral não está funcionando no editor do AEM Guides. (12106)

- O prefixo é duplicado no modo de visualização do Editor da Web. (13133)
- `Choicetable` linhas não são exibidas ou não podem ser selecionadas. (12616)
- O Editor da Web lança erros de validação em cenários específicos ao criar um tópico usando um esquema personalizado. (12576)
- As referências de modelo de tópico diferencial não criam uma cópia na pasta de conteúdo ao criar um mapa a partir do modelo de mapa. (12150)
- A caixa de pesquisa nos mapas DITA não tem um botão Fechar. (11867)
- Ao salvar arquivos longos no Editor da Web, `DirtyChecker` aciona uma exceção com um rastreamento de pilha longo e preenche os arquivos de log. (11860)
- A criação de tópicos DITA requer a permissão Excluir no nó de pasta correspondente, embora o mapa possa ser criado com a permissão Gravar. (11706)
- O Editor da Web mostra um título incorreto quando uma barra está presente. (10949)


### Gerenciamento

- O campo &quot;title&quot; nas propriedades de metadados do mapa DITA é substituído pelo elemento `<title>` para o mapa. (10702)
- A referência de conteúdo é quebrada ao copiar e colar arquivos DITA quando a ID do tópico não é a mesma que o GUID. (12614)
- Nas linhas de base dinâmicas, a lista de rótulos não é retirada das referências diretas da cópia de trabalho de um mapa DITA. (1917)

### Publicação

- Falha na publicação ao renomear uma predefinição de PDF nativa. (12564)
- A duplicação de um modelo de PDF nativo duplica para o local do modelo padrão em vez do local do modelo personalizado fornecido. (12563)

- PDF nativo | A inclusão de várias referências cruzadas estende o texto além da largura da coluna. (13004)
- PDF nativo | Quando o tópico e o título têm a mesma ID, isso resulta em uma geração mal formada da saída em PDF. (12644)
- PDF nativo | Ao adicionar uma classe de saída a um elemento pai `<topicref>` em um mapa DITA e aplicar um estilo personalizado à classe de saída, o estilo é aplicado aos elementos no corpo do tópico, incluindo títulos de seção.(12166)
- A publicação incremental não funciona se um mapa DITA tiver várias ditavalrefs. (12117)
- Site AEM | Ao criar um mapa com keydef apontando para um tópico como uma variável e adicionar processing-role=resource-only, você cria algumas páginas inesperadas. (12099)
- Se quaisquer ativos do DAM do AEM forem usados em qualquer saída diferente do site AEM, os metadados &quot;jcr:createdBy&quot; não refletirão o nome do editor ou o nome do usuário que modificou o mapa ou tópico DITA por último. (12090)
- AEM Sites | O mapa DITA com cabeçalho de tópico no navtitle (com caracteres não compatíveis) resulta em URLs de página inválidos. (1978)
- PDF nativo | Problemas ocorrem no suporte a topichead / topicmeta / navtitle no Frontmatter e Backmatter. (1969)
- PDF nativo | Gerar PDF para documentos grandes é um processo demorado. (1955)
- PDF nativo | Renomear uma predefinição gera uma NullPointerException ao gerar uma saída de PDF. (11889)
- O conteúdo `<conref>` não é mostrado na saída do PDF. (11131)
- Um espaço extra é adicionado dentro dos elementos `<div>` ao alternar entre as exibições Autor e Source no editor de layout de página. (10750)
- O conteúdo replicado no gerenciador de nuvem AEM não está visível na instância do Publish. (9564)

### Tradução

- O processo para exportar uma linha de base renomeada para uma tradução falha. (12993)
- O título do arquivo traduzido é exibido no lugar do título do arquivo de origem. (11630)
