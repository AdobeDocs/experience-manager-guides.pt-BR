---
title: Manipulador de eventos de pós-processamento
description: Saiba mais sobre o manipulador de eventos de pós-processamento
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/ixD-jFpXxkdmPbOWtCDxPgjtxu-FfJkzGCdUHNeA1CY'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: e0bef973-8c57-4760-9b12-ec950a3c7247
    internal-label: Post processing event handler
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 4%
---
# Manipulador de eventos de pós-processamento {#id175UB30E05Z}

## UUID e CLOUD SERVICE

O Adobe Experience Manager Guides expõe o evento `com/adobe/guides/postprocess/complete` usado para executar qualquer operação de pós-processamento. Esse evento é acionado sempre que uma operação é executada em um arquivo DITA. As seguintes operações em um arquivo DITA acionam esse evento:

- Upload
- Criar
- Modificar

>[!NOTE]
>
> O evento de pós-processamento é disparado ao habilitar o sinalizador `fire.processing.events`, que é um parâmetro de configuração no `fmdita config manager`. Quando definido como true, ele aciona eventos (com/adobe/guides/postprocess/complete) para rastrear a conclusão do pós-processamento. Por padrão, é definido como falso (desativado).

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
| `status` | String | O status de retorno da operação executada. As opções possíveis são: <br>- ÊXITO: a operação de pós-processamento foi concluída com êxito. <br>- FALHA: a operação de pós-processamento falhou devido a algum erro. |
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
| `status` | String | O status de retorno da operação executada. As opções possíveis são: <br>- ÊXITO: a operação de pós-processamento foi concluída com êxito. <br>- CONCLUÍDO COM ERROS: a operação de pós-processamento foi concluída, mas com alguns erros. <br>- FALHA: a operação de pós-processamento falhou devido a algum erro. |
| `message` | String | Caso o status seja COMPLETED WITH ERRORS ou FAILED, esse parâmetro contém os detalhes sobre o erro ou o motivo da falha. |
| `operation` | String | A operação de pós-processamento executada no arquivo. As opções possíveis são:<br>- Adição <br>- Atualização <br>- Exclusão |
