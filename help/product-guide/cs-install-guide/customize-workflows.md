---
title: Configurar e personalizar workflows
description: Saiba como configurar e personalizar workflows
exl-id: a5742082-cc0b-49d9-9921-d0da1b272ea5
feature: Workflow Configuration
role: Admin
level: Experienced
source-git-commit: 01efb1f17b39fcbc48d78dd1ae818ece167f4fe5
workflow-type: tm+mt
source-wordcount: '1762'
ht-degree: 2%

---

# Configurar e personalizar workflows {#id181AI0OJ0RO}

Os workflows permitem automatizar as atividades do Adobe Experience Manager \(AEM\). Um fluxo de trabalho consiste em uma série de etapas executadas em uma ordem específica. Você pode definir uma atividade distinta para executar em cada etapa. Por exemplo, você pode enviar uma notificação por email a todos os revisores em um grupo quando uma revisão de tópico é criada. Ou envie uma notificação para o editor quando uma tarefa de geração de saída for concluída.

Para obter mais informações sobre fluxos de trabalho no AEM, consulte:

- [Administrando Instâncias de Fluxo de Trabalho](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html?lang=pt-BR)

- Aplicando e participando de fluxos de trabalho: [Trabalhando com fluxos de trabalho de projeto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/projects/workflows.html?lang=pt-BR).


As seções neste tópico guiarão você pelas várias personalizações que podem ser feitas nos fluxos de trabalho padrão enviados no AEM Guides.

## Personalizar fluxo de trabalho de revisão {#id176NE0C00HS}

A equipe de criação de conteúdo de cada organização trabalha de maneira específica para atender às suas necessidades de negócios. Em algumas organizações há um editor dedicado, enquanto outras poderiam ter um sistema automatizado de revisão editorial em vigor. Por exemplo, em uma organização, um fluxo de trabalho típico de criação e publicação pode incluir tarefas como: sempre que um autor é concluído com a criação de conteúdo, ele vai automaticamente para os revisores e, quando a revisão é concluída, vai para o editor para gerar a saída final. No AEM, as atividades que você faz no conteúdo e nos ativos podem ser combinadas no formato de um processo e mapeadas para um fluxo de trabalho do AEM. Para obter mais informações sobre fluxos de trabalho no AEM, consulte [Administração de fluxos de trabalho](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html?lang=pt-BR) na documentação do AEM.

O AEM Guides permite personalizar o workflow de revisão padrão. Você pode usar os quatro processos personalizados relacionados à revisão a seguir com outros fluxos de trabalho de criação ou publicação.

- **Criar Revisão**: esse processo prepara os metadados necessários para criar uma tarefa de revisão. Por exemplo, atribuirá permissão de revisão aos revisores, definirá o status dos tópicos como em revisão, definirá as linhas do tempo de revisão e muito mais. Dos quatro processos, esse é o único processo obrigatório que deve ser incluído no fluxo de trabalho personalizado. No seu workflow, você pode optar por incluir ou excluir os outros três processos.

- **Atribuir Tarefa de Revisão**: esse processo cria a tarefa de revisão e envia a notificação da tarefa para o iniciador e os revisores.

- **Enviar Email de Revisão**: esse processo envia o email de revisão para o iniciador e os revisores.

- **Agendar Trabalho para Fechar Revisão**: esse processo garante que o processo de revisão seja concluído ao atingir o prazo final.


Quando você está criando um fluxo de trabalho de revisão personalizado, a primeira tarefa é definir os metadados necessários para o processo Criar revisão. Para fazer isso, você pode criar um script ECMA. Uma amostra do script ECMA que atribui os metadados é fornecida abaixo para o tópico e para o mapa.

**Para tópico**

```javascript
var workflowdata=workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator","admin");
workflowdata.getMetaDataMap().put("operation","AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics","/content/dam/xml-solution/review.xml");
workflowdata.getMetaDataMap().put("payloadJson","{\"base\":\"/content/dam/xml-solution\",\"asset\":[\"/content/dam/xml-solution/review.xml\"],\"referrer\":\""}");
workflowdata.getMetaDataMap().put("deadline","2017-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title","Review through custom workflow");
workflowdata.getMetaDataMap().put("description","Initiate this review process using the AEM workflow");
workflowdata.getMetaDataMap().put("assignee","user-one", "user-two");
workflowdata.getMetaDataMap().put("status","1");
workflowdata.getMetaDataMap().put("projectPath","/content/projects/review");
workflowdata.getMetaDataMap().put("startTime", System.currentTimeMillis());
workflowdata.getMetaDataMap().put("reviewType", "AEM");
workflowdata.getMetaDataMap().put("versionJson", "[{\"path\":\"GUID-ca6ae229-889a-4d98-a1c6-60b08a820bb3.dita\",\"review\":true,\"version\":\"1.0\",\"reviewers\":[\"projects-samplereviewproject-owner\"]}]");
workflowdata.getMetaDataMap().put("isDitamap","false");
workflowdata.getMetaDataMap().put("reviewVersion","3.0");
```

**Para o mapa**

```javascript
var workflowdata = workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator", "admin");
workflowdata.getMetaDataMap().put("operation", "AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics", "GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita|GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita|GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita|");
var payloadJson = "{\"referrer\":\"\",\"rootMap\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"asset\":[\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\"],\"base\":\"/content/dam\"}";
workflowdata.getMetaDataMap().put("payloadJson", payloadJson);
workflowdata.getMetaDataMap().put("deadline", "2047-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title", "Review task via workflow with map");
workflowdata.getMetaDataMap().put("description", "Review task via workflow with map Description");
workflowdata.getMetaDataMap().put("assignee", "user-one");
workflowdata.getMetaDataMap().put("status", "1");
workflowdata.getMetaDataMap().put("projectPath", "/content/projects/review_project_via_workflow");
workflowdata.getMetaDataMap().put("startTime", new Date().getTime());
var versionJson = "[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]}]";
workflowdata.getMetaDataMap().put("versionJson", versionJson);
workflowdata.getMetaDataMap().put("notifyViaEmail", "true");
workflowdata.getMetaDataMap().put("allowAllReviewers", "false");
workflowdata.getMetaDataMap().put("isDitamap", "true");
workflowdata.getMetaDataMap().put("ditamap", "GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap");
var ditamapHierarchy = "[{\"path\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"items\":[{\"path\":\"GUID-db5787bb-5467-4dc3-b3e5-cfde562ee745.ditamap\",\"items\":[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"items\":[],\"title\":\"\"},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"items\":[],\"title\":\"\"}],\"title\":\"\"},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"items\":[],\"title\":\"\"}]}]";
workflowdata.getMetaDataMap().put("ditamapHierarchy", ditamapHierarchy);
workflowdata.getMetaDataMap().put("reviewVersion","3.0");
```

Você pode criar esses scripts no nó `/etc/workflows/scripts`. A tabela a seguir descreve as propriedades que estão sendo atribuídas por ambos os scripts ECMA mencionados anteriormente.

| Propriedade | Tipo | Descrição |
|--------|----|-----------|
| `initiator` | String | ID do usuário que inicia a tarefa de revisão. |
| `operation` | String | Um valor estático definido como `AEM_REVIEW`. |
| `orgTopics` | String | Caminho dos tópicos que estão sendo compartilhados para revisão. Especifique vários tópicos separados por vírgula. |
| `payloadJson` | Objeto JSON | Especifique os seguintes valores: -   `base`: caminho da pasta pai contendo o tópico enviado para revisão. <br> -   `asset`: caminho do tópico enviado para revisão. <br> -   `referrer`: deixe em branco. |
| `deadline` | String | Especifique a hora no formato `yyyy-MM-dd'T'HH:mm:ss.SSSXXX`. |
| `title` | String | Insira um título para a tarefa de revisão. |
| `description` | String | Informe uma descrição para a tarefa de revisão. |
| `assignee` | String | ID de usuário dos usuários para os quais você deseja enviar o tópico\(s\) para revisão. |
| `status` | Número inteiro | Um valor estático definido como 1. |
| `startTime` | Longo | Use a função `System.currentTimeMillis()` para obter a hora atual do sistema. |
| `projectPath` | String | Caminho do projeto de revisão ao qual a tarefa de revisão será atribuída, por exemplo: /content/projects/samplereviewproject. |
| `reviewType` | String | Valor estático &quot;AEM&quot;. |
| `versionJson` | Objeto JSON | versionJson é uma lista de tópicos que entram na revisão, em que cada objeto de tópico tem a seguinte estrutura [ { &quot;path&quot;: &quot;/content/dam/1-topic.dita&quot;, &quot;version&quot;: &quot;1.1&quot;, &quot;review&quot;: true, &quot;revisores&quot;: [&quot;projects-we_retail-editor&quot;] } ] |
| `isDitamap` | Booleano | falso/verdadeiro |
| `ditamapHierarchy` | Objeto JSON | Caso o mapa seja enviado para revisão, o valor aqui deve ser como:[ { &quot;path&quot;: &quot;GUID-f0df1513-fe07-473f-9960-477d4df29c87.ditamap&quot;, &quot;items&quot;: [ { &quot;path&quot;: &quot;GUID-9747e8ab-8cf1-45dd-9e20-d47d482f667d.dita&quot;, &quot;title&quot;: &quot;&quot;, &quot;items&quot;: [] } ] } ]. |
| `ditamap` | String | Especificar o caminho do ditamap da tarefa de revisão |
| `allowAllReviewers` | Booleano | falso/verdadeiro |
| `notifyViaEmail` | Booleano | falso/verdadeiro |
| `reviewVersion` | String | Especifica a versão atual do fluxo de trabalho de Revisão. O valor padrão está definido como `3.0`.<br> Para habilitar os novos recursos de fluxo de trabalho de revisão para [Autores](../user-guide/review-close-review-task.md) e [Revisores](../user-guide/review-complete-review-tasks.md), verifique se `reviewVersion` está definido como `3.0`. |


Depois de criar o script, chame-o antes de chamar o processo Criar revisão no workflow. Em seguida, dependendo das suas necessidades, você poderá chamar os outros processos de workflow de revisão.

### Remover o fluxo de trabalho de revisão da configuração de limpeza

Para melhorar o desempenho do mecanismo de fluxo de trabalho, você pode remover regularmente do repositório do AEM as instâncias de fluxo de trabalho concluídas. Se estiver usando as configurações padrão do AEM, todas as instâncias de fluxo de trabalho concluídas serão excluídas após um período específico. Isso também resulta na remoção de todos os workflows de revisão do repositório do AEM.

Você pode impedir a limpeza automática dos fluxos de trabalho de revisão removendo o modelo de fluxo de trabalho de revisão \(information\) da configuração de limpeza automática. Você precisa usar a **Configuração de limpeza de fluxos de trabalho do Adobe Granite** para remover os modelos de fluxos de trabalho de revisão da lista de limpeza automática.

Na **Configuração de limpeza de fluxos de trabalho do Adobe Granite**, certifique-se de listar pelo menos um fluxo de trabalho que possa ser limpo com segurança. Por exemplo, você pode usar qualquer um dos workflows a seguir criados pelo AEM Guides:

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

A adição de um fluxo de trabalho na **Configuração de limpeza de fluxos de trabalho do Adobe Granite** garante que o AEM limpe apenas os fluxos de trabalho listados na configuração. Isso impede que o AEM remova as informações do fluxo de trabalho de revisão.

Para obter mais detalhes sobre como configurar a **Configuração de limpeza de fluxos de trabalho do Adobe Granite**, consulte *Administração de instâncias de fluxos de trabalho* na documentação do AEM.

### Personalizar emails e notificações do AEM

Vários workflows do AEM Guides usam notificações por email. Por exemplo, se você iniciar uma tarefa de revisão, uma notificação por email será enviada aos revisores. No entanto, para garantir que a notificação por email seja enviada, é necessário habilitar essa funcionalidade no AEM. Para habilitar a notificação por email no AEM, consulte o artigo [Envio de email](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=pt-BR#sending-email) na documentação do AEM.

O AEM Guides contém um conjunto de notificações por email e do AEM usadas no fluxo de trabalho de revisão que você pode personalizar. Execute as seguintes etapas para personalizar essas notificações:

1. Use o Gerenciador de Pacote para baixar a pasta `/libs/fmdita/mail/review`.

   >[!NOTE]
   >
   > Não faça nenhuma personalização nos arquivos de configuração padrão disponíveis no nó ``libs``. Você deve criar uma sobreposição do nó ``libs`` no nó ``apps`` e atualizar os arquivos necessários somente no nó ``apps``.

1. A pasta `review` contém as seguintes subpastas:

   - `aem-notification`
   - `CSS`
   - `email-notification`

   A descrição detalhada dessas subpastas é explicada abaixo:

   | Revisar subpastas | Descrição |
   |-----------------|-----------|
   | `aem-notification` | Contém diferentes tipos de notificação do AEM disponíveis para personalização. <br> `closed` <br> `content-updated` <br> `feedback-addressed` <br> `feedback-provided` <br> `requested` <br> `reviewer-removed` <br> `tag-mention` <br> Nessas subpastas, `primary.vm` e `secondary.vm` arquivos estão localizados e permitem personalizar o título e a descrição da notificação do AEM, respectivamente. |
   | `CSS` | Contém o arquivo `email-notification.css` para personalizar o estilo das notificações por email. |
   | `email-notification` | Contém diferentes tipos de notificação por email disponíveis para personalização. <br> `closed` <br> `content-updated` <br> `feedback-addressed` <br> `feedback-provided` <br> `requested` <br> `reviewer-removed` <br> `tag-mention` <br> Nessas subpastas, `primary.vm` e `secondary.vm` arquivos estão localizados e permitem personalizar o assunto e o corpo da notificação de email, respectivamente. |

A definição de cada tipo de notificação é apresentada abaixo:

- `closed`: acionado quando uma tarefa de revisão é fechada.
- `content-updated`: acionado quando um Autor ou iniciador atualiza o conteúdo.
- `feedback-addressed`: acionado quando Autor ou iniciador endereça os comentários e solicita uma revisão do Revisor.
- `feedback-provided` acionado quando o Revisor marca a tarefa como concluída fornecendo comentários no nível da tarefa ao Autor ou iniciador da tarefa de revisão.
- `requested`: acionado quando um Autor ou iniciador cria uma tarefa de revisão.
- `reviewer-removed`: acionado quando um Revisor não está atribuído à tarefa de revisão.
- `tag-mention`: acionado quando um usuário é mencionado ou marcado em comentários de revisão.

Ao personalizar um email ou uma notificação do AEM, certifique-se de usar apenas o seguinte conjunto predefinido de variáveis que são usadas em arquivos `primary.vm` e `secondary.vm`.


| **Nome da variável** | **Descrição** | **Tipo de dados** |
|-------------------------|---------------------------------------------------------------|---------------|
| `projectPath` | Caminho para o projeto que contém a tarefa de revisão | String |
| `reviewTitle` | Título da tarefa de revisão | String |
| `projectName` | Nome do projeto | String |
| `commentator` | Nome do usuário que adicionou um comentário | String |
| `commentExcerpt` | Trecho do comentário adicionado | String |
| `taskLink` | Link direto para a tarefa de revisão | URL |
| `authorName` | Nome do autor que criou ou atualizou a tarefa de revisão | String |
| `dueDate` | Data final da tarefa de revisão | Data |
| `reviewerName` | Nome do revisor atribuído à tarefa | String |
| `user` | Usuário envolvido na tarefa de revisão, como Autor, Revisor ou até mesmo Administrador. | String |
| `recipient` | Usuário específico que recebe a notificação | String |


## Personalizar fluxo de trabalho de geração de pós-saída {#id17A6GI004Y4}

O AEM Guides oferece a flexibilidade de especificar um fluxo de trabalho de geração de pós-saída. Você pode executar algumas tarefas de pós-processamento na saída gerada usando o AEM Guides. Por exemplo, talvez você queira aplicar algumas tags CQ à saída de site do AEM gerada ou definir determinadas propriedades na saída de PDF, ou enviar um email a um conjunto de usuários depois que a saída for gerada.

Você pode criar um novo modelo de fluxo de trabalho para usar como um fluxo de trabalho de geração pós-saída. Quando um workflow de geração pós-saída é acionado, o workflow de geração de saída compartilha informações contextuais por meio do mapa de metadados do workflow, que você pode usar para executar o processamento na saída gerada. A tabela a seguir descreve as informações contextuais compartilhadas como metadados:

| Propriedade | Tipo | Descrição |
|--------|----|-----------|
| ``outputName`` | String | Nome da predefinição de saída usada para gerar a saída. |
| `generatedPath` | String | Caminho no DAM em que a saída gerada está armazenada. |
| `outputType` | com.adobe.fmdita.output.OutputType | Tipo de predefinição de saída. |
| `outputTitle` | String | Título da predefinição de saída. |
| `outputHistoryPath` | String | Caminho do repositório do nó do histórico. |
| `isSuccess` | Booleano | Um sinalizador que descreve o status final do processo de geração de saída: sucesso ou falha. |
| `logPath` | String | Caminho no DAM em que os logs de geração de saída são salvos. |
| `generatedTime` | Longo | Hora em que o processo de geração de saída foi acionado. |
| `initiator` | String | A ID do usuário que acionou o fluxo de trabalho de geração de saída. |

Para usar os metadados de geração de saída, você pode criar um script ECMA ou um pacote OSGi. Uma amostra do script ECMA que usa os metadados é fornecida abaixo:

>[!NOTE]
>
> Você pode criar esse script no nó ``/etc/workflows/scripts``.

```javascript
var session = workflowSession.getSession(); // Obtain session object to read/write the repository.
var payload = workItem.getWorkflowData().getPayload().toString(); // Get the workflow payload (the ditamap file on which the generation was triggered)
var metadata = workItem.getWorkflowData().getMetaDataMap(); // Get the workflow metadata object
var generatedPath = metadata.get("generatedPath"); // supplied by AEM Guides
var username = metadata.get("initiator"); // supplied by AEM Guides
var successful = metadata.get("isSuccess"); // supplied by AEM Guides
var title = metadata.get("outputTitle"); // supplied by AEM Guides
var subject = "Output Generation Finished";
var message = "Generation of output " + title + " just finished " + 
(successful ? "successfully. " : "unsuccessfully. ");
    message += "It was triggered by " + username;    
if (successful) {
    message += "<br/><br/>The path to the generated output is " + 
generatedPath;
}
/*
    MailerAPI.sendMail("dl-docs-authors", subject, message);
*/
```

Depois de criar o script, chame o script personalizado no fluxo de trabalho. Em seguida, dependendo das suas necessidades, você poderá chamar os outros processos de workflow. Depois de criar o fluxo de trabalho personalizado, chame *Finalizar pós-geração* como a última etapa do processo de fluxo de trabalho. A etapa *Finalizar Pós-Geração* garante que o status da tarefa de geração de saída seja atualizado para *Concluído* na conclusão do processo de geração de saída. Depois de criar um fluxo de trabalho personalizado de geração pós-saída, você pode configurá-lo com qualquer uma das predefinições de geração de saída. Selecione o fluxo de trabalho necessário na propriedade *Executar Fluxo de Trabalho de Pós-Geração* da predefinição necessária. Quando você executa uma tarefa de geração de saída usando a predefinição de saída configurada, o status da tarefa \(na guia Saída\) muda para *Pós-processamento*.
