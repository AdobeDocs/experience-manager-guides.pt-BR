---
title: API REST para trabalhar com mapas DITA
description: Saiba mais sobre a REST API para trabalhar com mapas DITA
exl-id: 6277e52d-1b05-4dd7-8d2b-4b94f329e2d7
feature: Rest API DITA Map
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/GT4JRw1nFV7M18tJX-0t0Gx-g0I9tA8XfXLGnnhvif0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2: id: b7cb7f25-3b6d-4e58-beab-fe9279275fe4
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 626
ht-degree: 4%

---

# API REST para trabalhar com mapas DITA {#id175UB30E05Z}

A API REST a seguir permite trabalhar com mapas DITA no AEM Guides.

## Baixar mapa DITA com dependentes

Um método do GET que baixa um mapa DITA com todos os seus dependentes, como tópicos referenciados, submapas, imagens e DTDs usados no mapa e nos tópicos.

**Solicitar URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/exportditamap

**Parâmetros**:

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `ditamap` | String | Sim | Caminho absoluto do arquivo de mapa DITA no repositório do AEM. |
| `baseline` | String | Não | O título da linha de base usada para recuperar o conteúdo com versão. <br> **Observação:** o valor diferencia maiúsculas de minúsculas. |

**Valores de resposta**:
Um arquivo .zip cujo conteúdo é gravado no fluxo de saída da resposta.

## Iniciar exportação para mapa DITA com dependentes

Um método POST que inicia uma exportação para um mapa DITA com todos os seus dependentes, como tópicos referenciados, submapas, imagens e DTDs usados no mapa e nos tópicos. O status pode ser consultado posteriormente e o URL de download pode ser recuperado após a conclusão.

**Solicitar URL**:
http:*//&lt;aem-guides-server\>: &lt;número-porta\>/bin/dxml/async-export*

**Parâmetros**:

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `ditamap` | String | Sim | Caminho absoluto do arquivo de mapa DITA no repositório do AEM. |
| `baseline` | String | Não | O título da linha de base usada para recuperar o conteúdo com versão. <br> **Observação:** o valor diferencia maiúsculas de minúsculas. |
| `flatFS` | Booleano | Não | \(Opcional\) Se definido como verdadeiro, então uma estrutura simples de arquivos é retornada no arquivo ZIP. Por exemplo, se o mapa DITA fizer referência ao conteúdo em várias pastas, todos os arquivos referenciados serão colocados em uma única pasta. Caso haja arquivos com o mesmo nome, eles serão renomeados adicionando um sufixo numérico. Todas as referências \(no mapa DITA e em tópicos\) são manipuladas automaticamente, pois são atualizadas com base no novo local dos arquivos na estrutura de pasta simples. Se definido como falso, a estrutura de pastas será mantida como está no arquivo ZIP. Se o mapa DITA se referir a arquivos de vários locais, todos esses locais também serão criados no arquivo ZIP. Ao restaurar o arquivo ZIP, a estrutura de pastas exata é criada no local de destino. <br> O valor padrão desse parâmetro é false. |

**Valores de resposta**:

| Elemento | Descrição |
|-------|-----------|
| `status` | O status de retorno da operação executada. As opções possíveis são: STARTED, FAILED, INPROGRESS, SUCCEED, MISSING, DELETED |
| `jobId` | O identificador exclusivo do trabalho. Pode ser usado posteriormente para consultar o status. |
| errorMessage | A mensagem de erro do processo em caso de falha \(se o status for FAILED, MISSING ou DELETED\). |
| `filePath` | O caminho de arquivo do ZIP. Ela estará presente somente quando o trabalho for concluído e o status for SUCCEED. Isso pode ser usado para baixar o arquivo ZIP. |

## Status do mapa DITA de exportação de consulta

Um método GET que recupera o status da exportação para um mapa DITA com todos os seus dependentes. Ele pode ser sondado em um intervalo se o status for STARTED ou INPROGRESS até que seja concluído \(com sucesso ou com erro\).

**Solicitar URL**:
http:*//&lt;aem-guides-server\>: &lt;número-porta\>/bin/dxml/async-export*

**Parâmetros**:

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `jobId` | String | Sim | A ID do trabalho recuperada quando o trabalho de exportação é iniciado. |

**Valores de resposta**:

| Elemento | Descrição |
|-------|-----------|
| `status` | O status do trabalho de exportação. As opções possíveis são: STARTED, FAILED, INPROGRESS, SUCCEED, MISSING, DELETED |
| `jobId` | O identificador exclusivo do trabalho. Pode ser usado posteriormente para consultar o status. |
| `errorMessage` | A mensagem de erro do processo em caso de falha \(se o status for FAILED, MISSING ou DELETED\). |
| `filePath` | O caminho de arquivo do ZIP. Ela estará presente somente quando o trabalho for concluído e o status for SUCCEED. Isso pode ser usado para baixar o arquivo ZIP. |
