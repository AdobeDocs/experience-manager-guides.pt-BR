---
title: Recommendations para otimização de desempenho
description: Conheça a Recommendations para otimizar o desempenho
exl-id: b2a836a0-de82-4d89-aae3-43276997da74
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: b28b7d96cce69f677b0bcf891b94d7ac84eb1eb0
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 0%

---

# Recommendations para otimização de desempenho {#id213BD0JG0XA}

## Configurar armazenamento de dados \(Obrigatório\)

**Qual é a alteração?**
Defina a propriedade `minRecordLength` com um valor de `100` na configuração `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.`. Para obter mais informações sobre o armazenamento de dados do arquivo e o armazenamento de dados S3, consulte o artigo [Configurando armazenamentos de nós e armazenamentos de dados no AEM 6](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html).

>[!NOTE]
>
> Para o armazenamento de dados S3, o custo de manutenção do conteúdo no armazenamento de dados também depende do número de solicitações. Portanto, ao fazer essa configuração com S3, o custo de configuração por solicitação e o tamanho do cache também devem ser considerados.

**Quando configurar?**
Após a configuração inicial, mas antes da migração de qualquer conteúdo. Você deve executar essa alteração mesmo em um sistema existente, o que garante que todo o novo conteúdo seja armazenado no armazenamento de dados em vez do armazenamento de segmentos.

**Resultado desta alteração**
Os arquivos DITA são salvos no armazenamento de dados em vez do armazenamento de segmentos. Isso mantém o tamanho do armazenamento de segmentos abaixo dos limites recomendados, o que melhora a capacidade de resposta do sistema.

## Atualizar índice Lucene \(Obrigatório\)

**Qual é a alteração?**
Excluir /var/dxml de oak:index/lucene.

>[!NOTE]
>
> O AEM Guides nunca usa índices Lucene para pesquisar conteúdo no nó /var/dxml.

**Quando configurar?**
Se você estiver fazendo essa alteração em um novo sistema antes de migrar o conteúdo, será necessário apenas atualizar oak:index/lucene. Caso contrário, em um sistema existente em que o conteúdo já foi migrado, depois de fazer a alteração em oak:index/lucene, recrie os índices para Lucene \(*que pode levar algumas horas para ser concluído*\).

**Resultado desta alteração**
Essa alteração impede que o nó /var/dxml seja indexado e armazenado no armazenamento de segmentos.

## Otimização da memória Java \(Obrigatório\)

**Qual é a alteração?**
Os parâmetros de inicialização da JVM devem ser cuidadosamente ajustados com base na infraestrutura e no tamanho do disco. É recomendável que você consulte o Suporte para Adobe para obter ajuda para acessar a configuração ideal. No entanto, você mesmo pode experimentar as seguintes configurações:

- Defina o tamanho do heap de JVM para um mínimo de 1/4 do total de memória disponível. Use o parâmetro `-Xmx<size>` para definir o tamanho da memória de heap. Defina o valor de -`Xms` igual a `-Xmx`.

- Habilitar `-XX:+HeapDumpOnOutOfMemoryError` e definir o caminho para `-XX:HeapDumpPath=</path/to/folder` `>`.

- Habilitar log do Java GC como:

`* -XX:+PrintGCDateStamps`

`* -verbose:gc`

`* -XX:+PrintGCDetails`

`* -XX:+PrintTenuringDistribution`

`* -Xloggc:</path/to/gc.log>`

- Em geral, para o Java 11, use G1GC \(`-XX:+UseG1GC`\) e, para o Java 8, use CMS \(-`XX:+UseConcMarkSweepGC`\).

- Use `-XX:NewRatio` para controlar o tamanho da memória da geração jovem. O valor padrão é 2, o que significa que 1/3 da memória é usada para a geração jovem. Como há muitos objetos sendo rapidamente criados e destruídos, usando um valor de 1 alocará 1/2 da memória para a geração jovem.

- Controle o número de objetos que estão sendo promovidos para a geração antiga usando `-XX:MaxTenuringThreshold`. Use o valor 15 \(default\) para atrasar quando os objetos são promovidos para a geração antiga.

**Quando configurar?**
Se você estiver fazendo essa alteração em um sistema existente, será necessário reiniciar o sistema. No caso de uma nova instalação, essa alteração deve ser feita no arquivo de script de inicialização \(.bat ou .sh\) antes que o sistema seja iniciado.

**Resultado desta alteração**
Isso resulta em tamanho de heap ideal e execução regulada de GC.

## Minificação da biblioteca do cliente na instância do autor \(Opcional\)

**Qual é a alteração?**
As bibliotecas de clientes devem ser definidas para minificar nas instâncias de Criação. Isso garante que haja menos bytes para baixar quando um usuário estiver navegando no sistema de locais diferentes. Para fazer essa alteração, defina a configuração no **Gerenciador de biblioteca de HTML** a partir do console Felix.

**Quando configurar?**
Isso pode ser feito em tempo de execução por meio do console Felix ou por meio da implantação de código.

**Resultado desta alteração**
Essa alteração melhora o tempo de carregamento das páginas na instância do autor, pois menos bytes são transferidos para carregar as bibliotecas do cliente.

## Configurar threads de publicação simultâneas \(Obrigatório, dependendo do caso de uso\)

**Qual é a alteração?**
Essa alteração será necessária se você estiver usando o DITA-OT para publicar a saída, e vários threads de publicação simultâneos também forem definidos.

Por padrão, o AEM Guides define os threads de publicação para o número de CPUs+1. No entanto, é recomendável definir esse valor como metade \(1/2\) ou um terço \(1/3\) do número total de CPUs. Para fazer isso, defina a propriedade **Tamanho do Pool de Geração** na configuração `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` de acordo com as recomendações.

**Quando configurar?**
Isso pode ser feito em tempo de execução por meio do console Felix ou por meio da implantação de código.

**Resultado desta alteração**
Essa alteração garante que, em uma instância do Autor em execução, todos os recursos não sejam alocados para as operações de publicação. Isso também mantém os recursos do sistema disponíveis para os autores, o que resulta em uma melhor experiência do usuário.

## Configurar o tamanho do lote dos nós para a geração de saída do site AEM \(Obrigatório, dependendo do caso de uso\)

**qual é a alteração?**
Essa alteração será necessária se você estiver gerando uma saída do AEM Sites.

Defina a propriedade **Limitar páginas do site AEM na Pilha** em `com.adobe.fmdita.config.ConfigManager` como um número com base na configuração do seu sistema. Essa propriedade define o tamanho do lote dos nós que serão confirmados quando as páginas do site forem geradas. Por exemplo, em um sistema com um número maior de CPUs e um tamanho de heap, você pode aumentar o valor padrão de `500` para um número maior. Você precisa testar a execução com o valor alterado para chegar a um valor ideal para essa propriedade.

**Quando configurar?**
Isso pode ser feito em tempo de execução por meio do console Felix ou por meio da implantação de código.

**Resultado desta alteração**
Um aumento no número de **Limitar Páginas do Site AEM na propriedade Heap** otimiza o processo de geração de saída do Site AEM.


**Tópico pai:**&#x200B;[ Baixar e instalar](download-install.md)
