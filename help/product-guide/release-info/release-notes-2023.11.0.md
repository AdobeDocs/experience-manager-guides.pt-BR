---
title: Notas de versão | Instruções de atualização e problemas corrigidos nos Guias da Adobe Experience Manager, versão de novembro de 2023
description: Saiba mais sobre as correções de erros e como atualizar para a versão de novembro de 2023 do Adobe Experience Manager Guides as a Cloud Service
exl-id: 80839890-075f-4187-a167-444c73215496
feature: Release Notes
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1673'
ht-degree: 0%

---

# Versão de novembro de 2023 do Adobe Experience Manager Guides as a Cloud Service

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão de novembro de 2023 do Adobe Experience Manager Guides as a Cloud Service (mais tarde conhecido como *Guias do Experience Manager as a Cloud Service*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão de novembro de 2023 do Experience Manager Guides as a Cloud Service](whats-new-2023.11.0.md).

## Atualização para a versão de novembro de 2023

Atualize sua configuração as a Cloud Service do Experience Manager Guides executando as seguintes etapas:

1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
2. Atualizar `<dox.version>` propriedade no `/dox/dox.installer/pom.xml` arquivo do seu código Git Cloud Service para 2023.11.0.406.
3. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de novembro de 2023 do Experience Manager Guides as a Cloud Service.

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

1. Execute uma solicitação POST no servidor (com a autenticação correta) - `http://<server:port>//bin/guides/reports/upgrade`.

1. A API retorna um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Quando o trabalho for concluído, a solicitação do GET anterior responderá com êxito. Se a tarefa falhar por algum motivo, a falha poderá ser vista nos logs do servidor.

1. Reverter para o valor padrão ou existente anterior de `queryLimitReads` se você o alterou na etapa 1.

## Etapas para indexar o conteúdo existente para usar a nova localização e substituição e lista de tópicos na guia Relatórios:

(Somente se você estiver em uma versão anterior à versão de junho de 2023 do Experience Manager Guides as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa e da lista de tópicos na guia relatórios:

1. Execute uma solicitação POST no servidor (com a autenticação correta) - `http://<server:port>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados || Por exemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. Você também pode passar uma pasta raiz para indexar os mapas DITA de uma pasta específica (e suas subpastas). Por exemplo, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Observe que se os parâmetros de caminhos e de raiz forem transmitidos, somente o parâmetro de caminhos será considerado.

1. A API retorna um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação de GET com id de trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`)


1. Quando o trabalho for concluído, a solicitação do GET anterior responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Etapas para lidar com o `'fmdita rewriter'` conflito

Os Guias do Experience Manager têm um [**reescrita personalizada do sling**](../cs-install-guide/conf-output-generation.md#custom-rewriter) módulo para tratamento de ligações geradas em caso de mapas cruzados (ligações entre os tópicos de dois mapas diferentes).

Se você tiver outra reescrita de sling personalizada em sua base de código, use uma `'order'` valor maior que 50, como o sling rewriter dos Guias do Experience Manager usa `'order'` 50.  Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de reescrita de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante essa atualização, desde que o `'order'` for alterado de 1000 para 50, será necessário mesclar o reescritor personalizado existente, se houver, com `'fmdita-rewriter'`.


## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com a versão as a Cloud Service de novembro de 2023 dos Guias do Experience Manager.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.11.0 | Não compatível | 2022 ou superior |
| | | |


### Conector de oxigênio

| Versão do Experience Manager Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.11.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |


### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| Experience Manager Guias Componentes Pacote de conteúdo para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:



### Criação  

- Espaço após conref `<ph>` O elemento desaparece ao salvar o tópico. (13642)
- Erro de aplicativo ao tentar salvar arquivos DITA antes que o pós-processamento seja concluído. (13571)
- Se o título de um tópico contiver uma barra `/`, a guia no editor mostra apenas as letras que vêm após ela. (13455)
- A visualização da imagem não desaparece após ser exibida no Editor. (13454)
- O pop-up Inserir palavra-chave não é exibido ao usar chaves definidas pelo mapa raiz em outros tópicos. 12950)
- Os ícones de fechamento não ficam visíveis quando gráficos muito altos são visualizados no painel Histórico de versões. (12867)
- Não é possível modificar o fuso horário de **Versão criada em** para as Linhas de Base. (12711)
- A variável **Histórico da versão** O painel na interface do usuário do Assets mostra um carimbo de data e hora incorreto para o **Atual** campo. (12624)
- Criar um arquivo DITA a partir de um modelo com um nome de arquivo começando com caracteres numéricos resulta em um erro de namespace. (12188)
- No Editor da Web, a variável **Referências principais** é aberta ao inserir a variável `varname` tag. (10940)
- Os arquivos Zip não são reconhecidos no Editor da Web, e você não pode arrastá-los e soltá-los. (12709)
- O conteúdo com alguns atributos aplicados nele não está sendo realçado no modo Autor ou Visualização. (11063)
- Ao fechar um tópico após editá-lo, você é redirecionado para a página inicial do AEM em vez de retornar à visualização de pastas. (13306)
- Ocorre atraso no pós-processamento de arquivos que foram copiados e colados nos serviços de nuvem. (12457)
- A configuração de mapa de raiz persiste no Editor da Web mesmo se o usuário não a tiver definido explicitamente nas Preferências do usuário. (11551)


### Publicação

- A funcionalidade Publicar como fragmento de conteúdo não funciona para os arquivos listados nos resultados da pesquisa. (14090)
- Na publicação de PDF nativo, a seleção da cor do plano de fundo no layout do modelo requer um recarregamento de página ao reverter para `None`. (13621)
- Problema ao confirmar o armazenamento de dados de um mapa DITA grande com links de pares de escopo na publicação do Site AEM. (13530)
- Na publicação de PDF nativo, a acessibilidade é comprometida, pois as imagens no cabeçalho e no rodapé não exibem texto alternativo. (12829)
- A duplicação do layout de página no PDF nativo não funciona com nenhuma extensão adicionada automaticamente. (12534)
- Ao gerar a saída de PDF com a publicação de PDF nativo, o nome do arquivo é truncado após um ponto. (13620)
- Ícone e dica de ferramenta incorretos são exibidos para  **Editar conteúdo** na barra de ferramentas Layouts de página dos Modelos usados na publicação de PDF nativo. (13492)
- Os metadados personalizados não estão disponíveis na saída final. (12116)
- A reescrita fmdita entra em conflito com a configuração de reescrita do usuário e leva à exibição de URLs longos em vez dos links. (12076)
- Na predefinição do site AEM, a opção de **Gerar PDF separado para cada tópico** não está funcionando. (11555)
- A publicação de PDF nativo não tem suporte para a conversão de espaço de cores CMYK. (10754)
- As chamadas de linha de base dinâmicas estão usando o nome em vez do título, o que resulta na falha da opção Exportar API de mapa DITA. (14268)

### Gerenciamento

- A referência de conteúdo é quebrada ao copiar e colar os arquivos DITA com links de autorreferência sem GUID. (13540)
- No Editor da Web, a linha de base mostra o título da versão anterior em vez da versão selecionada do arquivo DITA. (13444)
- A variável **Relatórios** A guia na interface do Editor da Web não mostra a lista de tópicos para mapas DITA antigos criados antes da atualização de julho de 2023 do Experience Manager Guides as a Cloud Service. (11852)
- As predefinições de condição para um mapa DITA grande não estão sendo criadas. (10936)
- Um link de autorreferência é exibido abaixo da lista de Links quebrados nos relatórios. (13539)

### Análise

- Os painéis de revisão lado a lado das versões anterior e atual no Editor da Web não estão corretos na versão de outubro de 2023 do Experience Manager Guides as a Cloud Service. (14156)
- Personalização de modelo de email para **Revisão** O fluxo de trabalho do não funciona com a sobreposição de nós. (13954)
- A variável **Fechar** botão na página Revisar nos Guias do Experience Manager leva os usuários para a Página inicial do AEM. (13535)
- Os caracteres quebrados aparecem ao criar os trechos em coreano. (13489)
- Os anexos coreanos na tela de Revisão dos Guias de Experience Manager não são clicáveis. (13436)
- O título do mapa é cortado na tela de revisão e colaboração, sem a opção de visualizar o título completo. (13012)

### Tradução

- A aprovação automática às vezes não funciona e ocorrem exceções se um valor incorreto estiver definido em **Status da tradução**. (13607)
- A linha de base exportada do painel Tradução falha e não abre no idioma de destino. (12993)

## Problema conhecido

A Adobe identificou o seguinte problema conhecido para a versão de novembro de 2023.

- A regeneração seletiva de tópico para saída do AEM falha.
