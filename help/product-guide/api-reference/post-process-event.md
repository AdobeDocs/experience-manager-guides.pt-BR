---
title: Manipulador de eventos de pós-processamento
description: Saiba mais sobre o manipulador de eventos de pós-processamento
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 5%

---

# Manipulador de eventos de pós-processamento {#id175UB30E05Z}

O AEM Guides expõe o evento com/adobe/fmdita/postprocess/complete usado para executar qualquer operação de pós-processamento. Esse evento é acionado sempre que uma operação é executada em um arquivo DITA. As seguintes operações em um arquivo DITA acionam esse evento:

>[!NOTE]
>
> Esse evento não é acionado para a operação de exclusão no AEM 6.1.

- Upload
- Criação
- Modificação
- Exclusão

É necessário criar um manipulador de eventos do AEM para ler as propriedades disponíveis nesse evento e executar processamento adicional.

Os detalhes do evento são explicados abaixo:

**Nome do evento**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parâmetros**:

| Nome | Tipo | Descrição |
|----|----|-----------|
| `path` | String | O caminho do arquivo que acionou esse evento. Normalmente, esse é o arquivo no qual uma operação foi executada. |
| `status` | String | O status de retorno da operação executada. As opções possíveis são: - <br>- ÊXITO: a operação de pós-processamento foi concluída com êxito. <br>- CONCLUÍDO COM ERROS: a operação de pós-processamento foi concluída, mas com alguns erros. <br>- FALHA: a operação de pós-processamento falhou devido a algum erro fatal. |
| `message` | String | Caso o status seja COMPLETED WITH ERRORS ou FAILED, esse parâmetro contém os detalhes sobre o erro ou o motivo da falha. |
| `operation` | String | A operação de pós-processamento executada no arquivo. As opções possíveis são:<br>- Adição <br>- Atualização <br>- Exclusão |
