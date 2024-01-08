---
title: Manipulador de eventos de ativação em massa concluída
description: Saiba mais sobre o manipulador de eventos de ativação em massa concluída
source-git-commit: 8f1bb12a92ab9a63aef1765e51159644242683a0
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# Manipulador de eventos de ativação em massa concluída

As guias de Experience Manager expõem `com/adobe/fmdita/replication/complete` evento usado para executar quaisquer operações após a conclusão de um processo de ativação em massa. Esse evento é acionado sempre que um processo de ativação em massa é concluído. Por exemplo, se você executar a ativação em massa de uma predefinição de site AEM de um mapa, esse evento será chamado após o término do processo de ativação.

É necessário criar um manipulador de eventos do AEM para ler as propriedades disponíveis nesse evento e executar processamento adicional.

Os detalhes do evento são explicados abaixo:

**Nome do evento**:

```
com/adobe/fmdita/replication/complete 
```

**Parâmetros**: |Nome|Tipo|Descrição| |—|—|—| |`path`|Cadeia de caracteres|O caminho do arquivo que acionou esse evento. <br> Por exemplo, `/content/output/sites/ditamap1-ditamap`. <br> É uma lista de caminhos serializados como uma matriz JSON.| |`messageType`|String|O tipo de uma mensagem. <br>Opção possível: `REPLICATION`| |`action`|Cadeia de caracteres|Esta é a ação executada. <br>Opção possível: `BulkReplicate`| |`user`|String|O usuário que iniciou a operação.| |`result`|Cadeia de caracteres|O resultado da Ativação em massa. É um objeto JSON serializado: <br>`{"success":boolean,"code":integer,"message":"" }`| |`agentId`|String|O agentId usado na replicação. Por exemplo, `"publish"`.| |`importMode`|String|Modo de importação usado na ativação. As opções possíveis são: <br>`REPLACE, MERGE, UPDATE`.|


**Exemplo de ouvinte de eventos**:

```XML
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/fmdita/replication/complete",
        })
 
public class SampleEventHandler implements EventHandler {
 
    protected final Logger log = LoggerFactory.getLogger(this.getClass());
 
    @Override
    public void handleEvent(final Event event) {
        Map<String, String> properties = new HashMap<>();
        properties.put("paths", (String) event.getProperty("paths"));
        properties.put("messageType", (String) event.getProperty("messageType"));
        properties.put("action", (String) event.getProperty("action"));
        properties.put("result", (String) event.getProperty("result"));
        properties.put("user", (String) event.getProperty("user"));
        properties.put("agentId", (String) event.getProperty("agentId"));
        properties.put("importMode", (String) event.getProperty("importMode"));
 
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
 
    }
}
```
