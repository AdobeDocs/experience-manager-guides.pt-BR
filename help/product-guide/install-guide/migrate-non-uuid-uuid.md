---
title: Migração de conteúdo não UUID para UUID
description: Saiba como migrar conteúdo não UUID para UUID
feature: Migration
role: Admin
level: Experienced
exl-id: f53f4eef-5e99-4342-9919-508b90ee3571
source-git-commit: c9ad3bd0e43863ac9ad65776e4e8a81c3176f9a0
workflow-type: tm+mt
source-wordcount: '1503'
ht-degree: 1%

---

# Migração de conteúdo não UUID para UUID {#id226TI0U20XA}


Execute estas etapas para migrar seu conteúdo da versão 4.3.1 não UUID para a versão 4.3.2 UUID.

>[!IMPORTANT]
>
> * Antes de iniciar o processo de migração, verifique se você tem:
>
>   1. Todas as análises ativas foram fechadas.
>   1. Todas as tarefas de tradução foram fechadas.
> * Antes de migrar o conteúdo para o servidor UUID, verifique se você tem um servidor não UUID com uma versão compatível do AEM Guides instalada.
> * Se você estiver usando uma versão anterior à 4.3.1, atualize para a versão 4.3.1. Siga as [instruções de atualização](./upgrade-xml-documentation.md) específicas para a versão licenciada do seu produto.
> * Atualmente, as versões posteriores à 4.3.1 não são compatíveis com a migração.


## Instalação do pacote

Baixe os pacotes necessários no Portal de distribuição de software Adobe, com base em sua versão:


1. **Pré-migração**: [com.adobe.guides.pre-uuid-migration-1.2.27.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.guides.pre-uuid-migration-1.2.27.zip)
1. **Baixar a versão 4.3.2** do UUID: [com.adobe.fmdita-6.5-uuid-4.3.2.1977.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.fmdita-6.5-uuid-4.3.2.1977.zip)
1. **Migração**: [com.adobe.guides.uuid-upgrade-1.2.110.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.guides.uuid-upgrade-1.2.110.zip)

## Verificações de pré-migração

Execute as seguintes verificações na versão 4.3.1 não UUID:

1. Instale o pacote de pré-migração [com.adobe.guides.pre-uuid-migration-1.2.27.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.guides.pre-uuid-migration-1.2.27.zip) sobre a versão 4.3.1.

   >[!NOTE]
   >
   >* Você precisa de permissão de administrador para executar a migração.
   >* Recomenda-se a correção de arquivos com erros antes de prosseguir com a migração.

1. Se houver mais de 100.000 arquivos DITA no sistema, atualize as configurações de limite de consulta para que o script funcione:

   * Navegue até `/system/console/configMgr and increase both the configs to more than number of assets - queryLimitInMemory` e `queryLimitReads under org.apache.jackrabbit.oak.query.QueryEngineSettingsService`

1. Iniciar `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
1. Selecione **Avaliação de Compatibilidade** no painel esquerdo e procure o caminho da pasta `/content/dam` para todos os ativos.
1. Verifique a compatibilidade para listar as seguintes informações:
   * Total de arquivos
   * Tempo estimado para migração
   * Número de arquivos com erros
   * Arquivos com nome de arquivo GUID

   ![guia de avaliação de compatibilidade na migração](assets/migration-compatibility-assessment.png)


1. Se o erro for exibido, analise os logs e corrija-os. Você pode executar novamente a matriz de compatibilidade depois de corrigir os erros.

1. Selecione **Configurar validações** no painel esquerdo. Em seguida, **Selecione o mapa** e **Selecione a predefinição** do mapa para configurá-los. A lista de validação de saída atual exibe os arquivos de saída presentes antes da migração e pode ser validada em relação aos arquivos de saída gerados após a migração.

   Ao selecionar vários mapas DITA grandes, é possível validar se todo o conteúdo foi migrado com êxito sem problemas. Selecionar predefinições com linhas de base nelas garante também que as linhas de base e as versões sejam migradas com sucesso.

   ![Configurar a guia Validações na migração](assets/migration-configure-validation.png)


1. (Opcional) Execute a limpeza de versões no conteúdo para remover versões desnecessárias e acelerar o processo de migração. Para executar a limpeza de versão, selecione a opção **Limpeza de Versão** na tela de migração e vá para a interface do usuário usando a URL `http://<server- name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
   >[!NOTE]
   >
   >Este utilitário não remove nenhuma versão usada em linhas de base ou revisões ou tem rótulos.

Para obter mais detalhes, consulte [limpar versões mais antigas](../install-guide/version-management.md#purge-older-versions-of-dita-files).


## Pré-requisitos de migração

1. Executar a migração de UUID somente em uma instância do Autor.
1. Garantir a disponibilidade da infraestrutura a seguir:
   * A instância do autor é submetida a upsizing em termos de CPU e memória para oferecer suporte ao processamento mais rápido e à memória adicional necessária para a atividade em massa. por exemplo, se a CPU alocada no momento e a memória forem 8 vCPU e um heap de 24 GB, use o dobro do tamanho para essa atividade.
   * O espaço em disco geral e o espaço em disco temporário `(crx-quickstart directory)` devem ter um buffer 10 vezes maior do que o que já foi consumido. Após concluir a migração, você poderá recuperar a maior parte do espaço em disco executando a compactação.
   * Execute a **compactação Tar offline** antes de iniciar esta atividade.
   * Certifique-se de que nenhuma indexação ou manutenção do sistema seja planejada durante a janela dessa migração.

1. Instale a versão UUID da versão compatível sobre a versão não UUID. Por exemplo, se você estiver usando a build não UUID 4.3.1, será necessário instalar a versão UUID 4.3.2 [com.adobe.fmdita-6.5-uuid-4.3.2.1977.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.fmdita-6.5-uuid-4.3.2.1977.zip)) e executar a migração.


1. Instale o pacote de atualização de migração uuid [com.adobe.guides.uuid-upgrade-1.2.110.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.guides.uuid-upgrade-1.2.110.zip).
1. Desabilite iniciadores para os seguintes fluxos de trabalho usando a URL: `http://<server-name>/libs/cq/workflow/content/console.html`.

   * Fluxo de trabalho do Ativo de atualização DAM
   * Fluxo de trabalho de writeback de metadados DAM

   >[!NOTE]
   >
   >Idealmente, todos os inicializadores de fluxo de trabalho, que são executados em qualquer caminho dentro de `content/dam`, devem ser desabilitados.

1. Atualize as seguintes configurações de acordo com as alterações sugeridas:

   | Configuração | Propriedade | Valor |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | Ativar iniciadores do fluxo de trabalho de pós-processamento | Desabilitar |
   | `com.adobe.fmdita.config.ConfigManager` | uuid. regex | `^GUID-(?<id>.*)` |
   | `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation` | Ativar pós-processamento da versão | Desabilitar |
   | Serviço de marcação CQ diário | Ativar validação (validation.enabled) | Desabilitar |

1. Adicionar um agente de log separado para:
   * `com.adobe.fmdita.uuid`
   * `com.adobe.guides.uuid`.


1. (Se não tiver sido feito anteriormente) Se houver mais de 100.000 arquivos DITA no sistema, atualize o `queryLimitReads` em `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` para um valor maior (qualquer valor maior que o número de ativos presentes, por exemplo, 200.000).

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 <br> Valor Padrão: 100000 |

## Migração

1. Iniciar `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.

   ![Guia de atualização do sistema na migração](assets/migration-system-upgrade.png)
   >[!NOTE]
   >
   > Se você escolher &quot;Habilitar backup de ativos DITA&quot;, os arquivos de backup temporários serão armazenados em `/content/uuid-upgrade` e os backups de arquivos DITA serão excluídos quando a migração de um arquivo for concluída.


1. Selecione **Atualização do sistema** no painel esquerdo para executar a migração. É recomendável migrar todos os dados de uma só vez, já que o sistema lida de maneira ideal com o agrupamento internamente. Somente os arquivos que não são ativos DITA e não são usados em nenhum ativo DITA podem ser ignorados para migração.

1. (Opcional) Selecione as pastas para as quais deseja ignorar a migração. Use essa opção para migrar essas pastas posteriormente ou para ignorá-las. Verifique se essas pastas não têm ativos DITA e não são referenciadas por (e não serão referenciadas por) ativos DITA. Por exemplo, `content/dam/projects`.

1. Selecione *Habilitar backup de ativo dita* para criar um backup de ativo antes da migração. Esse backup é usado para reversão em caso de erro ao migrar um arquivo. Se a migração for bem-sucedida, o backup será excluído. No entanto, isso reduz o processo de migração.

1. Inicie a migração.
   >[!NOTE]
   >
   > Baixe os logs completos e observe se houve erros. Se qualquer erro ou exceção for encontrado *Não continue*, mas primeiro corrija o erro. Erros comuns são listados no final deste artigo.

1. Quando a migração for concluída, o relatório estará disponível para download e logs inteiros também poderão ser baixados.

1. Selecione **Baixar relatório** enquanto a migração está em execução para verificar se todos os arquivos da pasta foram atualizados corretamente e se todos os recursos funcionam somente para essa pasta.


   >[!NOTE]
   >
   > A migração de conteúdo pode ser executada em um nível de pasta, no `/content/dam` completo ou na mesma pasta (executar a migração novamente).

   Além disso, é importante garantir que a migração de conteúdo seja feita para todos os ativos de mídia, como imagens e gráficos usados no conteúdo DITA.

1. Depois que todos os arquivos forem migrados, selecione **Atualização de Linha de Base/Revisão** no painel esquerdo para migrar as linhas de base e revisar no nível da pasta.

![Guia Linha de base e revisão na migração](assets/migration-baseline-review-upgrade.png)

>[!NOTE]
>
>Se você reiniciar o sistema ou a migração for anulada, o script será retomado quando você executá-lo novamente com os mesmos parâmetros de antes. Entre em contato com a equipe de sucesso do cliente se você tiver problemas devido ao desligamento.

## Análise dos relatórios de cada etapa

**Etapa: Atualização do Sistema**

| Resumo após a conclusão do processo | Como interpretar? | Ação |
|---|---|---|
| Número total de arquivos: 345997 | Número total de arquivos processados no conjunto de pastas especificado. | ND |
| Número de arquivos atualizados com êxito: 344516 | Número de arquivos migrados com êxito para UUID. | ND |
| Número de arquivos atualizados com erros: 29 | Ocorreram erros nesses arquivos e devem ser os mesmos relatados na etapa de pré-migração. | ND |
| Número de arquivos ignorados: 1452 | Alguns arquivos no repositório DAM podem ter subativos, que são ignorados por não serem qualificados para migração de UUID. | ND |
| Número de arquivos com falha de atualização: 0 | Se a contagem não for 0, os logs deverão ser analisados para verificar se há problemas. | Verifique a exceção. Talvez seja necessário corrigir o erro e executar a migração novamente. |
| Tempo total necessário: 2:40:06.157 |  |  |

**Etapa: Atualizar Linhas de Base**

| Resumo após a conclusão do processo | Como interpretar? | Ação |
|---|---|---|
| Número total de arquivos: 4833 | Número de mapas DITA com pelo menos uma linha de base. |
| Número de arquivos atualizados com êxito: 4705 | Número de mapas DITA, atualizados com êxito com todas as linhas de base. |
| Número de arquivos atualizados com erros: 0 | Número de mapas DITA cujas linhas de base não foram atualizadas. |
| Número de arquivos ignorados: 1647 | Número de mapas DITA sem nenhuma linha de base. |
| Número de arquivos com falha de atualização: 128 | O número de objetos de linha de base inválidos (estavam vazios) está listado no relatório (Excel). | Verificar se há outros erros além de: `baselineObj not found on` |


## Pós-migração

1. Depois que a migração for concluída, selecione **Validar atualização do sistema** no painel esquerdo e valide os arquivos de saída antes e depois da migração para garantir que a migração seja bem-sucedida.

   ![Validar guia de atualização do sistema na migração](assets/migration-validate-system-upgrade.png)

1. Depois de migrar o servidor, habilite com êxito os seguintes fluxos de trabalho e configurações (incluindo todos os outros fluxos de trabalho que foram desabilitados inicialmente durante a migração) para continuar trabalhando no servidor:

   * Fluxo de trabalho do Ativo de atualização DAM
   * Fluxo de trabalho de metadados DAM

   >[!NOTE]
   >
   >Idealmente, qualquer inicializador de fluxo de trabalho, que estava sendo executado em qualquer caminho dentro de `content/dam` antes da migração, deve ser habilitado.

1. Habilite as seguintes configurações:

   | Configuração | Propriedade | Valor |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | *Habilitar Iniciadores de Fluxo de Trabalho de Pós-Processamento* | Habilitar |
   | `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation` | *Habilitar Pós-Processamento de Versão* | Habilitar |
   | Serviço de marcação CQ diário | *Habilitar validação (validation.enabled)* | Habilitar |

1. Propriedades do Assets para analisar após a migração:

   | Configuração | Propriedade | Valor de pré-migração em não UUID | Valor pós migração na UUID |
   |---|---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | **Usar título para nomes de página de site AEM** | Falso (valor padrão) | Verdadeiro |

   >[!NOTE]
   >
   > Se, antes da migração, a propriedade **Usar título para nomes de página de Sites AEM** dentro de `com.adobe.fmdita.config.ConfigManager`, for definida como *False*, essa propriedade precisará ser atualizada após a migração.


1. Depois que a validação for concluída, a maior parte do espaço em disco poderá ser recuperada executando a compactação (consulte `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=pt-BR`).

