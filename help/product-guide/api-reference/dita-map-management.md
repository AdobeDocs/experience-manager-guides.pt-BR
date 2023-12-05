---
title: API REST para trabalhar com mapas DITA
description: Saiba mais sobre a REST API para trabalhar com mapas DITA
exl-id: 6277e52d-1b05-4dd7-8d2b-4b94f329e2d7
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# API REST para trabalhar com mapas DITA {#id175UB30E05Z}

A API REST a seguir permite trabalhar com mapas DITA em guias AEM.

## Baixar mapa DITA com dependentes

Um método GET que baixa um mapa DITA com todos os seus dependentes, como tópicos, submapas, imagens e DTDs referenciados usados no mapa e nos tópicos.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/exportditamap

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`ditamap`|String|Sim|Caminho absoluto do arquivo de mapa DITA no repositório AEM.| |`baseline`|String|Sim|O título da linha de base que é usado para recuperar o conteúdo com versão. <br> **Nota:** O valor diferencia maiúsculas e minúsculas. |

**Valores de resposta**: um arquivo .zip cujo conteúdo é gravado no fluxo de saída da resposta.

## Iniciar exportação para mapa DITA com dependentes

Um método POST que inicia uma exportação para um mapa DITA com todos os seus dependentes, como tópicos referenciados, submapas, imagens e DTDs usados no mapa e nos tópicos. O status pode ser consultado posteriormente e o URL de download pode ser recuperado após a conclusão.

**URL de solicitação**: http:*//&lt;aem-guides-server>: &lt;port-number>/bin/dxml/async-export*

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`ditamap`|String|Sim|Caminho absoluto do arquivo de mapa DITA no repositório AEM.| |`baseline`|String|Não|O título da linha de base que é usado para recuperar o conteúdo com versão. <br> **Nota:** O valor diferencia maiúsculas e minúsculas.| |`flatFS`|Boolean|No|\(Optional\) Se definido como true, uma estrutura simples de arquivos é retornada no arquivo ZIP. Por exemplo, se o mapa DITA fizer referência ao conteúdo em várias pastas, todos os arquivos referenciados serão colocados em uma única pasta. Caso haja arquivos com o mesmo nome, eles serão renomeados adicionando um sufixo numérico. Todas as referências \(no mapa DITA e em tópicos\) são manipuladas automaticamente, pois são atualizadas com base no novo local dos arquivos na estrutura de pasta simples. Se definido como falso, a estrutura de pastas será mantida como está no arquivo ZIP. Se o mapa DITA se referir a arquivos de vários locais, todos esses locais também serão criados no arquivo ZIP. Ao restaurar o arquivo ZIP, a estrutura de pastas exata é criada no local de destino. <br> O valor padrão para esse parâmetro é false.|

**Valores de resposta**: |Elemento|Descrição| |—|—| |`status`|O status de retorno da operação executada. As opções possíveis são: STARTED, FAILED, INPROGRESS, SUCCEED, MISSING, DELETED| |`jobId`|A identificação exclusiva do trabalho. Pode ser usado posteriormente para consultar o status.| |errorMessage|A mensagem de erro do trabalho em caso de falha \(se o status for FAILED, MISSING ou DELETED\).| |`filePath`|O caminho de arquivo do ZIP. Ela estará presente somente quando o trabalho for concluído e o status for SUCCEED. Isso pode ser usado para baixar o arquivo ZIP.|

## Status do mapa DITA de exportação de consulta

Um método GET que recupera o status da exportação para um mapa DITA com todos os seus dependentes. Ele pode ser sondado em um intervalo se o status for STARTED ou INPROGRESS até que seja concluído \(com sucesso ou com erro\).

**URL de solicitação**: http:*//&lt;aem-guides-server>: &lt;port-number>/bin/dxml/async-export*

**Parâmetros**
|Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`jobId`|String|Sim|A ID do trabalho recuperada quando o trabalho de exportação é iniciado.|

**Valores de resposta**: |Elemento|Descrição| |—|—| |`status`|O status do trabalho de exportação. As opções possíveis são: STARTED, FAILED, INPROGRESS, SUCCEED, MISSING, DELETED| |`jobId`|A identificação exclusiva do trabalho. Pode ser usado posteriormente para consultar o status.| |`errorMessage`|A mensagem de erro do trabalho em caso de falha \(se o status for FAILED, MISSING ou DELETED\).| |`filePath`|O caminho de arquivo do ZIP. Ela estará presente somente quando o trabalho for concluído e o status for SUCCEED. Isso pode ser usado para baixar o arquivo ZIP.|
