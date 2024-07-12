---
title: Converter conteúdo não UUID com versões para conteúdo UUID da interface do usuário
description: Saiba como migrar conteúdo não UUID com versões 4.3.x.
source-git-commit: f18c19eb493cd4d2003f68b082e71ebe7b3e6b7a
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Migrar conteúdo não UUID com versões da Interface do Usuário

Se você estiver usando a versão 4.3.x ou posterior, execute estas etapas para migrar o conteúdo não UUID com versões para o conteúdo UUID.

## Matriz de compatibilidade

| Versão atual do AEM Guides (não UUID) | Versão necessária para migrar para UUID | Caminho de atualização compatível |
|---|---|---|
| 4.3.x ou superior | 4.3.0 não UUID | Instalar 4.3.1 (UUID) |

## Pacotes obrigatórios

1. **Limpeza de versão**: `com.adobe.guides.version-purge-1.0.11.zip` (opcional)
1. **Pré-migração**: `com.adobe.guides.pre-uuid-migration-1.1.2 .zip`
1. **Migração**: `com.adobe.guides.uuid-upgrade-1.1.13.zip`



## Pré-migração

1. (Opcional) Execute a limpeza de versões no conteúdo para remover versões desnecessárias e acelerar o processo de migração. Para executar a limpeza da versão 4.1 (NÃO há suporte na 4.0), instale o pacote `com.adobe.guides.version-purge-1.0.11.zip` e vá para a interface do usuário usando esta URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Este utilitário não remove nenhuma versão usada em linhas de base ou revisões ou tem rótulos.
1. Instalar o pacote de pré-migração (`ccom.adobe.guides.pre-uuid-migration-1.1.2 .zip`).

   >[!NOTE]
   >
   >* Você precisa de permissão de administrador para executar a migração.
   >* Recomenda-se a correção de arquivos com erros antes de prosseguir com a migração.

1. Selecione **Avaliação de Compatibilidade** no painel esquerdo e procure um caminho de pasta.
1. Verifique a compatibilidade para listar as seguintes informações:
   * Total de arquivos
   * Total de versões
   * Tempo estimado para migração
   * Número de arquivos com erros



![guia de avaliação de compatibilidade na migração](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Selecione **Configurar validações** no painel esquerdo. Em seguida, **Selecione o mapa** e **Selecione a predefinição** do mapa para configurá-los. A lista de validação de saída atual exibirá os arquivos de saída presentes antes da migração e poderá ser validada em relação aos arquivos de saída gerados após a migração posteriormente.

![Configurar a guia Validações na migração](assets/migration-configure-validation.png){width="800" align="left"}




## Migração

### Etapa 1: atualizar configuração

1. Verifique se o espaço livre disponível é pelo menos 10 vezes o espaço ocupado pelo AEM (diretório crx-quickstart) durante a migração. Após concluir a migração, você poderá recuperar a maior parte do espaço em disco executando a compactação (consulte [Limpeza de revisão](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Habilitar *Habilitar Iniciadores de Fluxo de Trabalho de Processamento do Post* em `com.adobe.fmdita.config.ConfigManager` e *Habilitar Pós-processamento de Versão* em `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Instale a versão UUID da versão compatível sobre a versão não UUID. Por exemplo, se você estiver usando uma build 4.0 não UUID ou uma build 4.1 não UUID, será necessário instalar a versão 4.1 do UUID.

1. Instale o novo pacote para migração de uuid (`com.adobe.guides.uuid-upgrade-1.1.13`).

1. Desabilite os fluxos de trabalho a seguir e qualquer outro fluxo de trabalho executado no `/content/dam` usando iniciadores no `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Fluxo de trabalho do Ativo de atualização DAM
   * Fluxo de trabalho de writeback de metadados DAM

1. Desabilite *Habilitar Iniciadores de Fluxo de Trabalho de Processamento do Post* em `com.adobe.fmdita.config.ConfigManager` e desabilite *Habilitar Pós-processamento de Versão* em `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Desabilite a propriedade Habilitar validação (`validation.enabled`) no Serviço de Marcação CQ Diário.

1. Verifique se a pasta de propriedade `uuid.regex` está definida corretamente em `com.adobe.fmdita.config.ConfigManager`. Se estiver em branco, defina-o como o valor padrão - `^GUID-(?<id>.*)`.
1. Adicionar um agente de log separado para `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` A resposta do navegador também está disponível em `/content/uuid-upgrade/logs`.

### Etapa 2: executar a migração e validar

#### Instalar o pacote de migração

![Guia de atualização do sistema na migração](assets/migration-system-upgrade.png){width="800" align="left"}

* Selecione **Atualização do sistema** no painel esquerdo para executar a migração. Inicie em uma pasta com dados menores antes de executá-la em `/content/dam`.

* Selecione **Baixar relatório** enquanto a migração está em execução para verificar se todos os arquivos da pasta foram atualizados corretamente e se todos os recursos funcionam somente para essa pasta.


>[!NOTE]
>
> A migração de conteúdo pode ser executada em um nível de pasta ou no `/content/dam` completo, ou na mesma pasta (execute a migração novamente).

Além disso, é importante garantir que a migração de conteúdo também seja feita para todos os ativos de mídia, como imagens e gráficos usados no conteúdo DITA.

#### Migração de linha de base e revisão

Selecione **Atualização de Linha de Base/Revisão** no painel esquerdo para migrar as linhas de base e revisar no nível da pasta.

![Guia Linha de base e revisão na migração](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Etapa 3: restaurar a configuração

Depois que o servidor for migrado com êxito, ative o pós-processamento, a marcação e os workflows a seguir (incluindo todos os outros workflows que são desativados inicialmente durante a migração) para continuar trabalhando no servidor.

* Fluxo de trabalho do Ativo de atualização DAM
* Fluxo de trabalho de metadados DAM

>[!NOTE]
>
>Se alguns arquivos não forem processados ou forem corrompidos antes da migração, eles serão corrompidos antes da migração e permanecerão corrompidos mesmo após a migração.

## Validação de migração

Depois que a migração for concluída, selecione **Validar atualização do sistema** no painel esquerdo e valide os arquivos de saída antes e depois da migração para garantir que ela seja bem-sucedida.

![Validar guia de atualização do sistema na migração](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Quando a migração for concluída, a maior parte do espaço em disco poderá ser recuperada executando a compactação (consulte `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

