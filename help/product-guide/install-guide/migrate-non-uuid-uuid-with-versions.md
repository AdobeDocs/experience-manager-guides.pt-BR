---
title: Converter conteúdo não UUID com versões em conteúdo UUID
description: Saiba como migrar conteúdo não UUID com versões.
exl-id: 9387e0d1-906c-4e5c-a7a0-0ed1600f5eb6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 1%

---

# Migrar conteúdo não UUID com versões

Execute estas etapas para migrar seu conteúdo não UUID com versões para conteúdo UUID.

## Matriz de compatibilidade

| Versão atual dos Guias do AEM (não UUID) | Versão necessária para migrar para UUID | Caminho de atualização compatível |
|---|---|---|
| 3.8.5 | 4.0 não UUID | Instale o 4.1 (UUID) e execute a migração |
| 4.0, 4.0.x, 4.1 ou 4.1.x | Igual ao não UUID atual | Instale o 4.1 (UUID) e execute a migração |
| 4.2 ou superior | ND | Ainda não suportado |

## Pacotes obrigatórios

1. **Limpeza de versão**: `com.adobe.guides.version-purge-1.0.11.zip` (opcional)
1. **Pré-migração**: `com.adobe.guides.pre-uuid-migration-1.0.7.zip`
1. **Migração**: `com.adobe.guides.uuid-upgrade-1.0.17`
1. **Pós-migração**: `com.adobe.guides.post-uuid-migration-1.0.2.zip`


## Pré-migração

1. (Opcional) Execute a limpeza de versões no conteúdo para remover versões desnecessárias e acelerar o processo de migração. Para executar a limpeza de versão na versão 4.1 (NÃO suportado na 4.0), instale o pacote `com.adobe.guides.version-purge-1.0.11.zip`, e vá para a interface do usuário usando esse URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Este utilitário não remove nenhuma versão usada em linhas de base ou revisões ou tem rótulos.
1. Instale o pacote de pré-migração (`com.adobe.guides.pre-uuid-migration-1.0.7.zip`).

1. Execute a consulta a seguir para obter um relatório com um tempo estimado (ETA) de quanto tempo a migração levará e ele indicará se há arquivos com problemas de conteúdo que não seriam migrados.

>[!NOTE]
>
>Você precisa de permissão de administrador para executar a migração.


| URL do ponto de extremidade | Tipo de solicitação | Parâmetro da consulta | Resultados esperados |
|---|---|---|---|
| `/bin/guides/pre_uuid_upgrade` <br> <br>**Por exemplo**: http://localhost:4502/bin/guides/pre_uuid_upgrade?root=/content/dam | GET | **raiz**: Pasta raiz<br> **Valor**: `/content/dam` para todo o repositório. | Um relatório de pré-migração (.csv) será criado listando o número de arquivos, as versões totais e os erros. <br><br> **Saída de exemplo**:<br>RootFolder: /content/dam <br>Total de arquivos: 2697 <br>Total de versões: 10380 <br>Número de arquivos com erros: 28 <br>Um relatório detalhado estará disponível via AEM CRX em `/content/uuid-pgrade/UuidMigrationReport_1688400131039.csv` |

Essa etapa pode falhar se houver muitos arquivos DITA no sistema. Para resolver isso, aumente o limite do número de arquivos percorridos na query aumentando o valor de *Limite de leitura na memória (queryLimitReads)* no Serviço de configurações do mecanismo de consulta Apache Jackrabbit de 100000, um número maior que o número total de ativos DITA presentes no sistema.

## Migração

### Etapa 1: atualizar configuração

1. Verifique se o espaço livre disponível é pelo menos 10 vezes o espaço ocupado pelo AEM (diretório crx-quickstart) durante a migração. Após concluir a migração, você poderá recuperar a maior parte do espaço em disco executando a compactação (consulte [Limpeza de revisão](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Ativar *Ativar iniciadores do fluxo de trabalho de pós-processamento* in `com.adobe.fmdita.config.ConfigManager` e *Ativar pós-processamento da versão* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Instale a versão UUID da versão compatível sobre a versão não UUID. Por exemplo, se você estiver usando uma build 4.0 não UUID ou uma build 4.1 não UUID, será necessário instalar a versão 4.1 do UUID.

1. Instale o novo pacote para migração de uuid (`com.adobe.guides.uuid-upgrade-1.0.17`).

1. Desabilite os seguintes fluxos de trabalho e qualquer outro fluxo de trabalho executado em `/content/dam` uso de inicializadores no `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Fluxo de trabalho do Ativo de atualização DAM
   * Fluxo de trabalho de writeback de metadados DAM

1. Desativar *Ativar iniciadores do fluxo de trabalho de pós-processamento* in `com.adobe.fmdita.config.ConfigManager` e desativar *Ativar pós-processamento da versão* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Desativar a propriedade Ativar validação (`validation.enabled`) no Serviço de marcação CQ diário.

1. Assegure que `uuid.regex` a pasta de propriedades está definida corretamente no `com.adobe.fmdita.config.ConfigManager`. Se estiver em branco, defina-o como o valor padrão - `^GUID-(?<id>.*)`.
1. Adicionar um agente de log separado para `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` A resposta do navegador também está disponível em `/content/uuid-upgrade/logs`.

### Etapa 2: executar o script e validar

Executar a consulta fornecida em uma pasta com dados menores antes de executá-la `/content/dam`.

>[!TIP]
>
>Você pode verificar se todos os arquivos na pasta foram atualizados corretamente e se todos os recursos funcionam somente para essa pasta.

| URL do ponto de extremidade | Tipo de solicitação | Parâmetro da consulta | Resultados esperados |
|---|---|---|---|
| `/bin/guides/uuid_upgrade`<br><br> **Por exemplo**: `http://localhost:4502/bin/guides/uuid_upgrade?root=/content/dam/test` | GET | **raiz**: Pasta raiz <br>**Valor**: /content/dam para todo o repositório.<br><br>**ignoreImageVersions**<br> **Valor**: true/false (ignora o processamento das versões de imagem. O valor padrão é false) | Relatório de migração com Lista de arquivos migrados com êxito, falha na atualização, atualização com erros e tempo total gasto. <br><br> **Saída de exemplo**: <br> [INFORMAÇÕES] Lista de arquivos com falha:0 <br>[INFORMAÇÕES] Não. de arquivos atualizados com êxito: 2241 <br>[INFORMAÇÕES] Não. de arquivos atualizados com erros: 28 <br>[INFORMAÇÕES] Não. Falha na atualização de um número de arquivos: 0 <br> [INFORMAÇÕES] Tempo total gasto: 0:37:03.131 |

>[!NOTE]
>
> A migração de conteúdo pode ser executada em nível de pasta ou no `/content/dam` ou na mesma pasta (execute a migração novamente).

Além disso, é importante garantir que a migração de conteúdo também seja feita para todos os ativos de mídia, como imagens e gráficos usados no conteúdo DITA.

#### Migração da linha de base

Execute a consulta na pasta que você já migrou para migrar as linhas de base nela.

| URL do ponto de extremidade | Tipo de solicitação | Parâmetro da consulta | Resultados esperados |
|---|---|---|---|
| `/bin/guides/baseline_uuid_upgrade`<br><br> **Por exemplo**: ` http://localhost:4502/bin/guides/baseline_uuid_upgrade?root=/content/dam/test` | GET | **raiz**: Pasta raiz <br> **Valor**: /content/dam para todo o repositório. <br><br> **ignoreImageVersions**<br> **Valor**: verdadeiro/falso <br>(Ignora o processamento das versões da imagem. O valor padrão é false) <br><br> **doReviews** <br> **Valor**: verdadeiro/falso <br> (Se as revisões precisarem ser atualizadas ou não. O valor padrão é false.) Relatório de migração com Lista de arquivos migrados com êxito, falha na atualização, atualização com erros e tempo total gasto. <br> <br> **Saída de exemplo**:<br>[INFORMAÇÕES] Falha na lista de arquivos <br> [INFORMAÇÕES] Não. de arquivos atualizados com sucesso 2241<br> [INFORMAÇÕES] Não. de arquivos atualizados com erros 28<br>[INFORMAÇÕES] Não. Falha ao atualizar 0 de arquivos<br>[INFORMAÇÕES] Tempo total gasto: 0:37:03.131 |


### Etapa 3: restaurar a configuração

Depois que o servidor for migrado com êxito, ative o pós-processamento, a marcação e os workflows a seguir (incluindo todos os outros workflows que são desativados inicialmente durante a migração) para continuar trabalhando no servidor.

* Fluxo de trabalho do Ativo de atualização DAM
* Fluxo de trabalho de metadados DAM

>[!NOTE]
>
>Se alguns arquivos não forem processados ou forem corrompidos antes da migração, eles serão corrompidos antes da migração e permanecerão corrompidos mesmo após a migração.

## Validação de migração

1. Instalar o pacote de migração pós-uuid (`com.adobe.guides.post-uuid-migration-1.0.2.zip`).

1. Execute a consulta a seguir para validar se não houve erros durante a migração que causassem a quebra de links. Esse script identificará se havia algum link que não estava desfeito antes, mas que foi desfeito agora por qualquer motivo.

   | URL do ponto de extremidade | Tipo de solicitação | Parâmetro da consulta | Resultados esperados |
   |---|---|---|---|
   | `/bin/guides/get_broken_links` <br> <br> **Por exemplo**:<br>`http://localhost:4502/bin/guides/get_broken_links` | GET | ND | Relatório de migração com o número total de arquivos com UUIDs corrompidos e seus respectivos caminhos de arquivo. <br> <br> **Saída de exemplo**:<br>[DEPURAR] Verificando se todas essas GUIDs são usadas no conteúdo.<br>[DEPURAR] Número total de arquivos com UUIDs possivelmente quebrados: 0 <br>[DEPURAR] Caminhos com UUIDs possivelmente quebrados:0 |

1. Quando a migração for concluída, a maior parte do espaço em disco poderá ser recuperada executando a compactação (consulte `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

## Migração de conteúdo delta

1. Para migrar o conteúdo delta do servidor ativo (não UUID) para o servidor UUID atual, instale o script de pré-migração no servidor não UUID.

1. Execute a seguinte consulta em todo o conjunto de dados (ou subpasta) para identificar e exportar todos os arquivos modificados após o carimbo de data e hora fornecido: O carimbo de data e hora usa o formato ISO8601 para datas e horas ( AAAA-MM-DDTHH:mm:ss.SSZ) e também permite representações parciais, como AAAA-MM-DD.

   | URL do ponto de extremidade | Tipo de solicitação | Parâmetro da consulta | Resultados esperados |
   |---|---|---|---|
   | `/bin/guides/data_export`<br><br>**Por exemplo**: <br> `http://localhost:4502/bin/guides/data_export?timestamp=2023-07-11&root=/content/dam` | GET | **carimbo de data e hora** <br> **Valor**: DD/MM/AAAA<br><br> **raiz**: Pasta raiz <br> **Valor**: `/content/dam` para todo o repositório. | Um arquivo zip com conteúdo delta é criado em /var/dxml/exports. <br> <br>**Amostra**: dataexport_1689761491218.zip (o arquivo é criado) |

1. Baixe o arquivo zip exportado pelo script. A última linha da resposta deve fornecer o caminho do arquivo zip gerado (armazenado em /var/dxml/exports no sistema).

1. Faça upload do arquivo zip no servidor uuid no caminho desejado na interface do usuário do Assets.

1. Verifique se o pacote de pós-migração está instalado no servidor uuid.

1. Execute a seguinte consulta para importar o conteúdo delta do arquivo zip carregado para o sistema. A consulta deve incluir o caminho do arquivo zip carregado para identificar e processar corretamente os dados.

   | URL do ponto de extremidade | Tipo de solicitação | Parâmetro da consulta | Resultados esperados |
   |---|---|---|---|
   | `/bin/guides/data_import`<br> **Por exemplo**:`http://localhost:4502/bin/guides/data_import?path=/content/dam/dataexport_1689344927551.zip&createVersion=true` | POST | **caminho**<br> **Valor**: `/content/dam/filename.zip`(Local do arquivo carregado) **createVersion** <br> **Valor**: verdadeiro/falso<br>(O valor padrão de createVersion é false). | O arquivo é carregado no caminho de conteúdo desejado.<br><br>**Amostra**: `dataexport_1689761491218.zip`<br><br> (O mesmo arquivo que foi exportado na etapa anterior é carregado no caminho desejado em `/content/dam`). |

1. O script criará um novo arquivo se ele não existir ou substituirá o arquivo existente se ele tiver sido modificado.

>[!NOTE]
>
> O histórico de versões e quaisquer outras alterações feitas no servidor (como workflows e revisões ) precisam ser atualizados manualmente.
