---
title: Configurar e personalizar workflows
description: Saiba como configurar e personalizar workflows
exl-id: a5742082-cc0b-49d9-9921-d0da1b272ea5
feature: Workflow Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 1%

---

# Configurar e personalizar workflows {#id181AI0OJ0RO}

Os workflows permitem automatizar as atividades do Adobe Experience Manager \(AEM\). Um fluxo de trabalho consiste em uma série de etapas executadas em uma ordem específica. Você pode definir uma atividade distinta para executar em cada etapa. Por exemplo, você pode enviar uma notificação por email a todos os revisores em um grupo quando uma revisão de tópico é criada. Ou envie uma notificação para o editor quando uma tarefa de geração de saída for concluída.

Para obter mais informações sobre workflows no AEM, consulte:

- [Administração de instâncias de fluxo de trabalho](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html)

- Aplicar e participar de fluxos de trabalho: [Trabalhar com fluxos de trabalho de projeto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/projects/workflows.html).


As seções neste tópico guiarão você pelas várias personalizações que podem ser feitas nos fluxos de trabalho padrão enviados nos Guias do AEM.

## Personalizar fluxo de trabalho de revisão {#id176NE0C00HS}

A equipe de criação de conteúdo de cada organização trabalha de maneira específica para atender às suas necessidades de negócios. Em algumas organizações há um editor dedicado, enquanto outras poderiam ter um sistema automatizado de revisão editorial em vigor. Por exemplo, em uma organização, um fluxo de trabalho típico de criação e publicação pode incluir tarefas como: sempre que um autor é concluído com a criação de conteúdo, ele vai automaticamente para os revisores e, quando a revisão é concluída, vai para o editor para gerar a saída final. No AEM, as atividades que você realiza em seu conteúdo e ativos podem ser combinadas no formato de um processo e mapeadas para um fluxo de trabalho de AEM. Para obter mais informações sobre fluxos de trabalho no AEM, consulte [Administração de workflows](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html) na documentação do AEM.

O AEM Guides permite personalizar o fluxo de trabalho de revisão padrão. Você pode usar os quatro processos personalizados relacionados à revisão a seguir com outros fluxos de trabalho de criação ou publicação.

- **Criar revisão**: esse processo prepara os metadados necessários para criar uma tarefa de revisão. Por exemplo, atribuirá permissão de revisão aos revisores, definirá o status dos tópicos como em revisão, definirá as linhas do tempo de revisão e muito mais. Dos quatro processos, esse é o único processo obrigatório que deve ser incluído no fluxo de trabalho personalizado. No seu workflow, você pode optar por incluir ou excluir os outros três processos.

- **Atribuir tarefa de análise**: esse processo cria a tarefa de revisão e envia a notificação da tarefa para o iniciador e os revisores.

- **Enviar email de revisão**: esse processo envia o email de revisão para o iniciador e os revisores.

- **Programar Job para Fechar Revisão**: esse processo garante que o processo de revisão seja concluído ao atingir o prazo final.


Quando você está criando um fluxo de trabalho de revisão personalizado, a primeira tarefa é definir os metadados necessários para o processo Criar revisão. Para fazer isso, você pode criar um script ECMA. Uma amostra do script ECMA que atribui os metadados é fornecida abaixo:

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
```

Você pode criar esse script no `/etc/workflows/scripts` nó. A tabela a seguir descreve as propriedades que estão sendo atribuídas por esse script ECMA:

| Propriedade | Tipo | Descrição |
|--------|----|-----------|
| `initiator` | String | ID do usuário que inicia a tarefa de revisão. |
| `operation` | String | Um valor estático definido como `AEM_REVIEW`. |
| `orgTopics` | String | Caminho dos tópicos que estão sendo compartilhados para revisão. Especifique vários tópicos separados por vírgula. |
| `payloadJson` | objeto JSON | Especifique os seguintes valores: -   `base`: caminho da pasta principal que contém o tópico enviado para revisão. <br> -   `asset`: caminho do tópico enviado para revisão. <br> -   `referrer`: deixe em branco. |
| `deadline` | String | Especificar a hora em `yyyy-MM-dd'T'HH:mm:ss.SSSXXX` formato. |
| `title` | String | Insira um título para a tarefa de revisão. |
| `description` | String | Informe uma descrição para a tarefa de revisão. |
| `assignee` | String | ID de usuário dos usuários para os quais você deseja enviar o tópico\(s\) para revisão. |
| `status` | Número inteiro | Um valor estático definido como 1. |
| `startTime` | Longo | Use o `System.currentTimeMillis()` para obter a hora atual do sistema. |

Depois de criar o script, chame-o antes de chamar o processo Criar revisão no workflow. Em seguida, dependendo das suas necessidades, você poderá chamar os outros processos de workflow de revisão.

### Remover o fluxo de trabalho de revisão da configuração de limpeza

Para melhorar o desempenho do mecanismo de fluxo de trabalho, você pode remover regularmente do repositório AEM as instâncias concluídas do fluxo de trabalho. Se você estiver usando as configurações padrão do AEM, todas as instâncias de fluxo de trabalho concluídas serão excluídas após um período específico. Isso também resulta em todos os workflows de revisão para serem removidos do repositório AEM.

Você pode impedir a limpeza automática dos fluxos de trabalho de revisão removendo o modelo de fluxo de trabalho de revisão \(information\) da configuração de limpeza automática. Você precisa usar o **Configuração de limpeza de fluxo de trabalho do Adobe Granite** para remover os modelos de fluxo de trabalho de revisão da lista de limpeza automática.

No **Configuração de limpeza de fluxo de trabalho do Adobe Granite**, certifique-se de listar pelo menos um workflow que possa ser removido com segurança. Por exemplo, você pode usar qualquer um dos seguintes fluxos de trabalho criados pelos Guias do AEM:

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

Adicionar um workflow na **Configuração de limpeza de fluxo de trabalho do Adobe Granite** A garante que o AEM remova apenas os workflows listados na configuração. Isso impede que o AEM remova as informações do fluxo de trabalho de revisão.

Para obter mais detalhes sobre a configuração da variável **Configuração de limpeza de fluxo de trabalho do Adobe Granite**, consulte *Administração de instâncias de fluxo de trabalho* na documentação do AEM.

### Personalizar modelos de email

Vários workflows de Guias do AEM usam notificações por email. Por exemplo, se você iniciar uma tarefa de revisão, uma notificação por email será enviada aos revisores. No entanto, para garantir que a notificação por email seja enviada, é necessário habilitar essa funcionalidade no AEM. Para ativar a notificação por email no AEM, consulte o artigo [Envio de email](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#sending-email) na documentação do AEM.

Os Guias do AEM contêm um conjunto de modelos de email que podem ser personalizados. Execute as seguintes etapas para personalizar esses modelos:

1. Use o Gerenciador de pacotes para baixar `/libs/fmdita/mail` arquivo.

   >[!NOTE]
   >
   > Não faça nenhuma personalização nos arquivos de configuração padrão disponíveis no ``libs`` nó. É necessário criar uma sobreposição do ``libs`` no nó ``apps`` e atualize os arquivos necessários no ``apps`` somente nó.

1. A pasta de e-mail contém os seguintes modelos personalizáveis:

   | Nome do arquivo de modelo | Descrição |
   |-----------------|-----------|
   | closereview.html | Esse template de email é usado quando uma tarefa de revisão é fechada. |
   | createreview.html | Esse template de email é usado quando uma nova tarefa de revisão é criada. |
   | reviewapproval.css | Esse arquivo CSS contém o estilo dos modelos de email. |


## Personalizar fluxo de trabalho de geração de pós-saída {#id17A6GI004Y4}

O Guias do AEM oferece a flexibilidade de especificar um fluxo de trabalho de geração de pós-saída. Você pode executar algumas tarefas de pós-processamento na saída que é gerada usando os Guias do AEM. Por exemplo, você pode querer aplicar algumas tags CQ na saída de AEM Site gerada, ou definir determinadas propriedades na saída de PDF, ou pode querer enviar um email para um conjunto de usuários depois que a saída for gerada.

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
> Você pode criar esse script no ``/etc/workflows/scripts`` nó.

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

Depois de criar o script, chame o script personalizado no fluxo de trabalho. Em seguida, dependendo das suas necessidades, você poderá chamar os outros processos de workflow. Depois de criar o fluxo de trabalho personalizado, chame o *Finalizar pós-geração* como a última etapa do processo de fluxo de trabalho. A variável *Finalizar pós-geração* garante que o status da tarefa de geração de saída seja atualizado para *Concluído* após a conclusão do processo de geração de saída. Depois de criar um fluxo de trabalho personalizado de geração pós-saída, você pode configurá-lo com qualquer uma das predefinições de geração de saída. Selecione o fluxo de trabalho necessário na *Executar fluxo de trabalho de pós-geração* da predefinição necessária. Quando você executa uma tarefa de geração de saída usando a predefinição de saída configurada, o status da tarefa \(na guia Saída\) muda para *Pós-processamento*.
