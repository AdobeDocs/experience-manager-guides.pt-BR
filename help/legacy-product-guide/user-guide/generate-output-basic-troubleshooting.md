---
title: Solução básica de problemas
description: Resolva problemas com a solução básica de problemas no AEM Guides. Saiba como exibir, copiar e verificar o arquivo de log em um editor de texto e resolver erros de compilação de JSP.
feature: Publishing, Troubleshooting
role: User
hide: true
exl-id: f85fee0f-30d1-453f-8700-781e0be8f616
TQID: https://experienceleague.adobe.com/jMAgPQGFPANQobS5s92KkGYc-rfhKy70Zda43TY-6VY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: f9dbea21-a714-40dd-bc90-080d8046c93fid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 690
ht-degree: 0%

---

# Solução básica de problemas {#id1821I0Y0G0A}

Ao trabalhar com o AEM Guides, você pode encontrar erros ao publicar ou abrir seu documento. Esses erros podem estar no mapa DITA, no tópico ou no próprio processo do AEM Guides. Esta seção fornece informações sobre como acessar e analisar informações no arquivo de log de geração de saída. Além disso, se o tópico DITA for muito grande, você poderá ver o erro de compilação de JSP. Esta seção também fornece informações sobre como resolver o erro de compilação de JSP.

## Exibir e verificar o arquivo de log {#id1822G0P0CHS}

Execute as seguintes etapas para exibir e verificar o arquivo de log de geração de saída:

1. Depois de iniciar o processo de geração de saída, clique em **Saídas** no console do mapa DITA.

   A coluna **Geral** de **Saídas Geradas** mostra os ícones para dar uma dica visual sobre o sucesso ou falha da geração de saída.

   ![](images/output-general-settings.png){width="300"}

   Na captura de tela acima, o primeiro e o terceiro ícones mostram a geração de saída com falha. O segundo ícone mostra uma geração de saída bem-sucedida, mas com mensagens. A última é uma geração de saída bem-sucedida sem nenhuma mensagem.

1. Clique no link na coluna **Gerado às** depois que o trabalho for concluído.

   O arquivo de log é aberto em uma nova guia.

   ![](images/log-file.png){width="800"}

1. Aplique os seguintes filtros para realçar o texto no arquivo de log:
   - Fatal: realça os erros fatais no arquivo de log com a cor rosa.
   - Erro: realça os erros no arquivo de log com a cor laranja.
   - Aviso: realça os avisos no arquivo de log com cor roxa.
   - Informações: destaca as mensagens de informações no arquivo de log com a cor azul.
   - Exceção: Realça as exceções no arquivo de log com a cor amarela.
1. Use os botões de navegação para cima e para baixo para ir até o texto destacado no arquivo de log.

   Como alternativa, role pelo arquivo de log e verifique as mensagens.


## Copiar e verificar o arquivo de log em um editor de texto

Execute as seguintes etapas para copiar e verificar o arquivo de log de geração de saída em um editor de texto:

1. Depois de iniciar o processo de geração de saída, clique em **Saídas** no console do mapa DITA.

1. Clique no link na coluna **Gerado às** depois que o trabalho for concluído.

   O arquivo de log é aberto em uma nova guia.

1. Clique no botão **Copiar Log**. O arquivo de log é copiado para a área de transferência.
1. Abra um editor de texto e cole o arquivo de log no editor.

1. Percorra o arquivo de log e verifique se há mensagens.

   As seguintes informações ajudarão você a determinar se há um erro no arquivo DITA ou no processo do AEM Guides:

   - *Erro relacionado ao arquivo de mapa DITA*: caso haja um erro encontrado no arquivo de mapa DITA ou em qualquer outro arquivo contido no mapa DITA, o arquivo de log conterá uma cadeia de caracteres, &quot;FALHA NA COMPILAÇÃO&quot;. Você pode verificar as informações fornecidas no arquivo de log para localizar o arquivo incorreto e corrigir o problema.

   No trecho de arquivo de log de exemplo a seguir, você pode ver a mensagem `BUILD FAILED` junto com o motivo do erro.

   ![](images/dita-error-in-log-file.png){width="650"}

   - *erro relacionado ao AEM Guides*: o outro tipo de erro que você pode identificar no arquivo de log está relacionado ao próprio processo do AEM Guides. Nesse caso, o arquivo de mapa DITA é analisado com sucesso, mas o processo de geração de saída falha devido a algum erro interno no AEM Guides. Para esse tipo de erro, você deve procurar ajuda da equipe de suporte técnico.

   No trecho de arquivo de log de exemplo a seguir, você pode ver a mensagem `BUILD SUCCESSFUL`, seguida de outro erro técnico.

   ![](images/process-error-in-log-file.png){width="650"}


## Resolver erro de compilação de JSP

Se o tópico DITA for muito grande, talvez você veja o erro de compilação JSP \(`org.apache.sling.api.request.TooManyCallsException`\) no navegador. Esse erro pode aparecer ao abrir um tópico para edição, revisão ou publicação.

Execute as seguintes etapas para resolver esse problema:

1. Na Navegação global, selecione Ferramentas e escolha Operações \> Console da Web.

   A página Adobe Experience Manager Web Console Configuration (Configuração do console da Web do) é exibida.

1. Procure e clique no componente *Apache Sling Main Servlet*.

   As opções configuráveis para o Apache Sling Main Servlet são exibidas.

1. Aumente o valor do parâmetro *Número de Chamadas por Solicitação* de acordo com suas necessidades.


**Tópico pai:**[ Geração de saída](generate-output.md)
