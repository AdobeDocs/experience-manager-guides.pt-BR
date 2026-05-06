---
title: Perguntas frequentes sobre desempenho de publicação e escalabilidade no Adobe Experience Manager Guides
description: Saiba mais sobre as perguntas frequentes sobre desempenho de publicação e escalabilidade no Adobe Experience Manager Guides.
source-git-commit: f188c2827a9e27249d0162c9f9913e090b29672d
workflow-type: tm+mt
source-wordcount: '1666'
ht-degree: 1%

---


# Processamento de ativos

O processamento de ativos é um fluxo de trabalho essencial responsável por garantir que os ativos de conteúdo sejam estruturados, validados, indexados e disponibilizados na plataforma. Com as crescentes demandas de escalabilidade e os requisitos nativos em nuvem, a arquitetura passou por uma transformação significativa, de um modelo de processamento hierárquico de uma única operação para um sistema distribuído, habilitado para gráficos e de várias operações.

## Fluxo de trabalho de processamento de ativos atual

### Visão geral do processamento

Quando um ativo é importado para o Experience Manager Guides, as seguintes etapas de processamento sequencial são executadas:

- Atribuição de chave exclusiva: cada documento recebe um identificador exclusivo para garantir a rastreabilidade e a integridade da referência.
- Análise: o conteúdo (por exemplo, XML DITA) é analisado em componentes estruturados para compreender o nível do sistema.
- Validação: a validação estrutural e do esquema garante a conformidade com os padrões do documento.
- Resolução de referência: as referências cruzadas (links, imagens, dependências) são resolvidas entre ativos.
- Extração de metadados: metadados como título, autor e atributos personalizados são extraídos para indexação e pesquisa.
- Reprocessamento na modificação: o reprocessamento incremental garante a consistência após as atualizações de conteúdo.

### Características arquitetônicas

- **Processamento de thread único**: impede a corrupção das estruturas JCR (Java Content Repository), que dependem de implementações de árvore B.Isso garante a integridade dos dados, mas introduz gargalos de processamento durante a assimilação em massa.

- **Dependência de Mapa Pai**: mantém relações hierárquicas entre ativos usando traversal gráfica. Trata-se de operações intensivas com alta latência durante o processamento em larga escala com aumento da sobrecarga computacional e esforço devido a operações de travessia intensa.

## Novo fluxo de processamento de ativos

As etapas principais de processamento permanecem funcionais consistentes, mas agora são executadas em uma estrutura distribuída e paralelizada, melhorando significativamente o throughput.

### Aprimoramentos de arquitetura

- **Integração de banco de dados de gráfico**:
   - Transição do JCR hierárquico para um banco de dados de gráficos nativo
   - Permite a manipulação eficiente de relacionamentos e dependências
   - Elimina a complexidade da simulação de operações de gráficos em armazenamento hierárquico
- **Processamento distribuído multithread**:
   - O processamento é executado em vários pods em um ambiente de nuvem
   - Remove a dependência em um único nó líder
   - Permite escalabilidade horizontal e execução paralela
- **Eliminação de dependência de mapa pai:**
   - Remove a necessidade de trajeto explícito do gráfico
   - Reduz as operações de I/O e a latência de processamento
   - Simplifica o pipeline de processamento
- **Alocação de ID exclusiva sincronizada**
   - A coordenação centralizada garante:
   - Nenhuma duplicação de IDs de documento
   - Consistência entre nós distribuídos
   - Mantém a integridade referencial em um ambiente simultâneo
- **Banco de dados escalonável nativo em nuvem (hospedado pela AWS)**
   - Camada de banco de dados altamente disponível e resiliente
   - Suporta dimensionamento elástico com base na carga de trabalho
   - Melhora a confiabilidade e o desempenho geral do sistema

![](images/workflow.png)

## Vantagens da nova arquitetura

- Melhorias de desempenho:
   - A execução paralela reduz significativamente o tempo de processamento
   - A eliminação de operações de travessia intensa reduz a latência
   - O tratamento otimizado de gráficos melhora a velocidade da resolução de dependências
- Escalabilidade:
   - O dimensionamento horizontal entre pods permite lidar com grandes volumes de assimilação
   - A infraestrutura nativa em nuvem se adapta dinamicamente às demandas de carga de trabalho
- Confiabilidade e disponibilidade:
   - O processamento distribuído remove um único ponto de falha
   - O banco de dados hospedado pela AWS garante alta disponibilidade e tolerância a falhas
- Ganhos de eficiência:
   - Redução da sobrecarga de I/O devido à remoção da travessia do mapa principal
   - Melhor utilização dos recursos nos nós de computação
- Integridade dos dados:
   - A alocação de ID sincronizada mantém a consistência entre sistemas distribuídos
   - Mantém a robustez ao permitir a simultaneidade

## Configurar banco de dados

O Experience Manager Guides permite a configuração simplificada do banco de dados para ambientes da AEM Cloud. Para configurar o banco de dados para sua instância da AEM Cloud, execute as seguintes etapas:

1. Acesse o AEM Cloud Manager: Navegue até o Adobe Experience Cloud Manager usando a URL abaixo, substituindo os espaços reservados pelos detalhes de sua organização, programa e ambiente: `https://experience.adobe.com/#/${orgName}/cloud-manager/environments.html/program/${programId}/environment/${envId}`

1. Configurar o ambiente: depois de abrir a página de configuração de ambiente por meio do Cloud Manager, você poderá ajustar as definições específicas da sua instância, incluindo a definição das configurações de banco de dados necessárias.

Essa abordagem simplificada garante acesso e configuração fáceis para ambientes AEM na infraestrutura em nuvem da Adobe.

1. Configure as propriedades abaixo:


| Nome de propriedade | Valor | Serviço aplicado | Tipo |
|----------------------------------|--------------------------------|-----------------|----------|
| DATABASE_URL | `<host>:<port>/<db_name>` | Autor | Variável |
| GUIDES_ENABLE_DATABASE | `true` | Autor | Variável |
| DATABASE_PASSWORD | `password` | Autor | Segredo |
| DATABASE_USERNAME | `username` | Autor | Variável |
| RUN_POSTPROCESS_IN_PHASES | `true` | Autor | Variável |
| DATABASE_CONNECTION_POOL_SIZE | `10` | Autor | Variável |


![](images/environment-config.png){width="350"}

1. Salvar alterações: depois de fazer as alterações de configuração, **salve-as** na interface do Cloud Manager.

1. Disponibilidade do sistema: depois que as configurações forem totalmente aplicadas, abra o GET `http://host/bin/guides/v1/system/status` e verifique as propriedades abaixo:
   - `<isDatabase>`: deve ser verdadeiro
   - `<databaseConnectionCheck>`: deve ser passado

   Se os valores acima estiverem corretos na resposta, o sistema estará disponível para ser usado com o banco de dados recém-configurado.

Ao seguir esse processo, você terá um ambiente de nuvem do AEM devidamente configurado e pronto para uso.

>[!NOTE]
>
> Se você estiver migrando para um ambiente existente com conteúdo pré-existente, primeiro execute a Fase 2 (Migrar conteúdo existente) antes de assimilar qualquer novo conteúdo. Isso garante que as GUIDs temporárias sejam atribuídas corretamente ao novo conteúdo.

## Assimilar dados no AEM DAM (Ambiente de nuvem) (Fase 1)

Para configurar uma nova pasta no AEM DAM (Digital Asset Manager), assimilar dados e compará-los com um ambiente baseado em JCR, siga as etapas abaixo.

1. Crie uma nova pasta no DAM.

2. Assimilar dados usando a Ferramenta de Carregamento de Dados: para obter detalhes, consulte **Carregando o Assets na AEM Cloud**.

3. Verifique o sistema
   - Depois que o upload for concluído, verifique se os ativos estão presentes no DAM.
   - Verifique se os metadados (como tipos de arquivo, descrições e tags) foram extraídos e associados aos ativos.
   - Verifique o processamento do Experience Manager Guides (multithread) para confirmar se todas as referências, a extração de metadados e as validações foram bem-sucedidas.
   - Testar o acesso e editar um documento para confirmar a integridade do sistema.

4. Comparação com o ambiente baseado em JCR
   - Compare os resultados em vários casos de teste.
   - Avaliar a velocidade de assimilação.


Para migrar o conteúdo que foi carregado e processado antes de alternar para uma configuração baseada em banco de dados do Experience Manager Guides, um script de migração pode ser usado. O script usa um conjunto de APIs para iniciar e monitorar o processo de migração. As etapas a seguir descrevem a abordagem recomendada.

## Migrar conteúdo do JCR para o banco de dados (Fase 2)

Para migrar o conteúdo que foi carregado e processado antes de alternar para uma configuração baseada em banco de dados do Experience Manager Guides, você deve usar um script de migração. O script usa um conjunto de APIs para iniciar e monitorar o processo de migração. As etapas a seguir descrevem a abordagem recomendada.

1. Acione a API de migração usando qualquer cliente REST.
2. Verifique o progresso da migração.
3. Monitorar a migração até a conclusão: Continue a monitorar até que a API de progresso relate 100% de conclusão. Uma vez concluído, todo o conteúdo anteriormente carregado e processado do repositório JCR será migrado para o banco de dados.

   >[!NOTE]
   >
   > - Verifique se os cabeçalhos de autorização necessários (como tokens OAuth, chaves de API ou tokens de acesso do console do desenvolvedor) estão incluídos para autenticar solicitações com o AEM.
   > - A duração da migração depende do tamanho do repositório de conteúdo. Recomenda-se a realização de verificações periódicas do progresso, juntamente com o monitoramento de erros ou interrupções.
   > - Revise os logs de migração, se disponíveis, para avaliar o desempenho da migração e identificar problemas.

4. Para suportar a migração para repositórios grandes, siga a configuração abaixo

   >[!NOTE]
   >
   > Aplique essa configuração somente se erros de passagem do repositório forem encontrados durante a migração.

   `file name: `org.apache.jackrabbit.oak.query.QueryEngineSettingsService.xml&quot;

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0"
         xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
         jcr:primaryType="sling:OsgiConfig"
         queryLimitInMemory="5000000"
         queryLimitReads="1000000"
   />
   ```


## API de migração

### Iniciar migração

- ponto de extremidade: `POST /bin/guides/v1/assets/process`
- corpo da solicitação: (`application/json`):

```json
  {
    "path": "/content/dam/dita-templates",
    "excludedPaths": [
      "/content/dam/demo",
      "/content/dam/demo1"
    ],
    "type": "ASSET_PROCESSING"
  }
```

- retorna o processingId da migração.
- aciona o fluxo de trabalho de processamento de ativos incorporado ao produto.

### Verificar status da migração

ponto de extremidade: `GET /bin/guides/v1/assets/process/status?processingId=<processingId>`

### Cancelar uma migração em execução

- ponto de extremidade: `POST /bin/guides/v1/assets/process/cancel`
- corpo da solicitação (application/json):

  ```
  {
   "processingId": "processingId"
  }
  ```

### Retomar uma migração com falha ou cancelada

- ponto de extremidade: `POST /bin/guides/v1/assets/process/resume`
- corpo da solicitação (application/json):

  ```
  {
   "processingId": "processingId"
  }
  ```

## Fazer upload de ativos para a nuvem do AEM

O Adobe Experience Manager (AEM) as a Cloud Service fornece várias abordagens para a assimilação de conteúdo em massa. Para garantir o desempenho ideal, especialmente para o pós-processamento do Experience Manager Guides, é essencial adotar uma estratégia de assimilação compatível e escalável.

### Assimilação em massa usando integrações de armazenamento em nuvem

O AEM oferece suporte à assimilação de conteúdo em massa por meio de provedores de armazenamento na nuvem compatíveis, permitindo que as organizações conectem sua solução de armazenamento preferencial e importem conteúdo diretamente para o AEM. Essa abordagem é recomendada para assimilação em larga escala e sensível ao desempenho devido aos seguintes benefícios:

- Infraestrutura dimensionável: o processo de assimilação é executado em uma infraestrutura em nuvem gerenciada pela Adobe, permitindo o dimensionamento automático com base no volume de carga e de conteúdo. Isso garante um desempenho de assimilação consistente mesmo para grandes conjuntos de dados.

- Planejamento de assimilação previsível: os usuários podem estimar a duração da assimilação antecipadamente, o que ajuda no planejamento de lançamento, na programação e na coordenação com as equipes dependentes.

  ![](images/ingestion-time.png){width="350"}

- Registro e rastreamento abrangentes: o fluxo de trabalho de assimilação inclui recursos detalhados de registro e rastreamento, fornecendo visibilidade sobre o progresso, estados de sucesso e possíveis problemas durante o processo de importação.

  ![](images/bulk-import-job.png){width="350"}

- Assimilação programada: a assimilação de conteúdo pode ser programada para ocorrer durante períodos predefinidos, garantindo impacto mínimo ou inexistente sobre os usuários finais e as operações em andamento.

Para obter mais informações, consulte [Usando Importação em Massa](https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/migration/bulk-import).

## Assimilação em massa usando upload do AEM

A AEM também fornece o [upload do AEM](https://github.com/adobe/aem-uploa), uma biblioteca e uma CLI (Command-Line Interface, interface de linha de comando) que permitem que os usuários assimilem conteúdo diretamente de um sistema de arquivos local. Essa opção pode ser integrada em soluções personalizadas ou usada como uma ferramenta independente da CLI para fazer upload de conteúdo.

Como essa abordagem é executada na máquina local dos usuários, ela requer uma conexão de rede estável e ininterrupta para garantir uma experiência de assimilação confiável e contínua.


## Verificação de integridade da conectividade do banco de dados do Experience Manager Guides

As implantações do Experience Manager Guides configuradas para usar um banco de dados exigem conectividade de banco de dados estável e consistente para operar de forma confiável. A verificação do status da conexão do banco de dados é uma etapa de verificação de integridade essencial para descartar problemas relacionados à conectividade que podem afetar a funcionalidade do sistema.

Essa verificação de integridade permite que os usuários confirmem se o banco de dados está configurado, acessível e funcionando conforme esperado. Para verificar o status da conexão DB, siga as etapas abaixo.

1. Abra qualquer navegador ou cliente REST
2. Acione uma chamada do GET usando esta [URL](https://host:port/bin/guides/v1/system/status)
3. Os campos abaixo podem ser usados para determinar a configuração do sistema e o status de integridade
   1. isDatabase:
      - true: o ambiente está configurado com o banco de dados.
      - false: o ambiente não está usando o banco de dados

   2. databaseConnectionCheck:
      - aprovado: o Experience Manager Guides verificará o status da conexão e, se o Guides puder se conectar ao banco de dados, retornará o status como aprovado.
      - falha: o ambiente não pode se comunicar com o banco de dados. Os clientes devem interromper imediatamente o uso do sistema e entrar em contato com o suporte da Adobe.

## Monitoramento de log

O Experience Manager Guides com banco de dados registra com eficiência os detalhes para fornecer uma insight no estado do sistema.
Use as consultas abaixo no Splunk para obter logs para cenários diferentes.

1. Logs de migração:
   - `index IN ("dx_aem_engineering") aem_service=cm-${programid}-${environmentId} sourcetype=aemerror "AssetProcessingJob" OR "AssetJobProducerDb" NOT "ServiceEvent"`
2. Logs pós-processamento:
   - `index IN ("dx_aem_engineering") aem_service= cm-${programid}-${environmentId} sourcetype=aemerror com.adobe.fmdita.uuid.concrete.Cor*`


>[!NOTE]
>
> Leia mais sobre [recursos de consulta do Splunk](https://www.splunk.com/en_us/blog/learn/splunk-cheat-sheet-query-spl-regex-commands.html) para filtrar esses logs com base na duração do tempo, no nível de log ou para pesquisar alguns padrões específicos.










