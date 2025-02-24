---
title: Manipulador de eventos de pós-processamento
description: Saiba mais sobre o manipulador de eventos de pós-processamento
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 8c992afc1cc56052e6c07ac3cea6e7d3412259b2
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 5%

---

# Manipulador de eventos de pós-processamento {#id175UB30E05Z}

## UUID e CLOUD SERVICE

O Adobe Experience Manager Guides expõe o evento `com/adobe/guides/postprocess/complete` usado para executar qualquer operação de pós-processamento. Esse evento é acionado sempre que uma operação é executada em um arquivo DITA. As seguintes operações em um arquivo DITA acionam esse evento:

- Upload
- Criar
- Modificar


É necessário criar um manipulador de eventos do Adobe Experience Manager para ler as propriedades disponíveis nesse evento e executar processamento adicional.

Os detalhes do evento são explicados abaixo:

**Nome do evento**:

```
com/adobe/guides/postprocess/complete 
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `path` | String | O caminho do arquivo que acionou esse evento. Normalmente, esse é o arquivo no qual uma operação foi executada. |
| `eventType` | String | O tipo de evento, ou seja, CRIAR ou MODIFICAR. |
| `status` | String | O status de retorno da operação executada. As opções possíveis são: - <br>- ÊXITO: a operação de pós-processamento foi concluída com êxito. <br>- FALHA: a operação de pós-processamento falhou devido a algum erro. |
| `errorMsg` | String | A mensagem de erro em caso de falha na operação de pós-processamento. |
| `uuid` | String | A UUID do arquivo que acionou esse evento. Normalmente, esse é o arquivo no qual uma operação foi executada. |

**Ouvinte de eventos de exemplo**


```
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/guides/postprocess/complete",
        })
public class PostProcessCompleteEventHandler implements EventHandler {

    protected final Logger log = LoggerFactory.getLogger(this.getClass());

    @Override
    public void handleEvent(final Event event) {
        Set<String> propertyNames = new HashSet<>(Arrays.asList(event.getPropertyNames()));
        Map<String, String> properties = new HashMap<>();
        properties.put("path", (String) event.getProperty("path"));
        properties.put("eventType", (String) event.getProperty("eventType"));
        properties.put("status", (String) event.getProperty("status"));
        if(propertyNames.contains("errorMsg")) {
            properties.put("errorMsg", (String) event.getProperty("errorMsg"));
        }
        if (propertyNames.contains("uuid")) {
            properties.put("uuid", (String) event.getProperty("uuid"));
        }
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
    }
}
```

## Não UUID


O Adobe Experience Manager Guides expõe o evento com/adobe/fmdita/postprocess/complete usado para executar qualquer operação de pós-processamento. Esse evento é acionado sempre que uma operação é executada em um arquivo DITA. As seguintes operações em um arquivo DITA acionam esse evento:

>[!NOTE]
>
> Esse evento não é acionado para a operação de exclusão no AEM 6.1.

- Upload
- Criação
- Modificação
- Exclusão

É necessário criar um manipulador de eventos do Adobe Experience Manager para ler as propriedades disponíveis nesse evento e executar processamento adicional.

Os detalhes do evento são explicados abaixo:

**Nome do evento**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `path` | String | O caminho do arquivo que acionou esse evento. Normalmente, esse é o arquivo no qual uma operação foi executada. |
| `status` | String | O status de retorno da operação executada. As opções possíveis são: - <br>- ÊXITO: a operação de pós-processamento foi concluída com êxito. <br>- CONCLUÍDO COM ERROS: a operação de pós-processamento foi concluída, mas com alguns erros. <br>- FALHA: a operação de pós-processamento falhou devido a algum erro. |
| `message` | String | Caso o status seja COMPLETED WITH ERRORS ou FAILED, esse parâmetro contém os detalhes sobre o erro ou o motivo da falha. |
| `operation` | String | A operação de pós-processamento executada no arquivo. As opções possíveis são:<br>- Adição <br>- Atualização <br>- Exclusão |
