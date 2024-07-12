---
title: Converter conteúdo não UUID com versões em conteúdo UUID
description: Saiba como migrar conteúdo não UUID com versões para conteúdo UUID.
feature: Migration
role: Admin
level: Experienced
exl-id: 8f3a89fc-7d18-453d-909d-6dff5e275cab
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 0%

---

# Migrar conteúdo com versão

Execute estas etapas para migrar seu conteúdo de versão não UUID para o conteúdo UUID.

>[!NOTE]
>
>Siga as [instruções de atualização](./upgrade-xml-documentation.md) específicas para a versão licenciada do seu produto.

## Matriz de compatibilidade

| Versão atual do Experience Manager Guides (não UUID) | Versão necessária para migrar para UUID | Caminho de atualização compatível |
|---|---|---|
| 3.8.5, 4.0.x ou 4.1.x | 4.1 não UUID | Instale o 4.1 (UUID) e execute a migração |
| 4.2, 4.2.x ou 4.3 | 4.3.0 não UUID | Instale o 4.3.1 (UUID) e execute a migração |
| 4.3.1 | ND | ND |

## Instalação do pacote

Baixe os pacotes necessários no Portal de distribuição de software Adobe, com base em sua versão:
<details>
<summary>  Pacotes para caminho de atualização da versão 4.1</summary>

1. **Pré-migração**: [com.adobe.guides.pre-uuid-migration-1.0.9.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.pre-uuid-migration-1.0.9.zip)
1. **Migração**: [com.adobe.guides.uuid-upgrade-1.0.19.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.uuid-upgrade-1.0.19.zip)
</details>


<details>
<summary> Pacotes para caminho de atualização da versão 4.3.1</summary>

1. **Pré-migração**: [com.adobe.guides.pre-uuid-migration-1.1.3.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.pre-uuid-migration-1.1.3.zip)
1. **Migração**: [com.adobe.guides.uuid-upgrade-1.1.15.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.uuid-upgrade-1.1.15.zip)

</details>

## Pré-migração

Execute as seguintes verificações na versão não UUID (4.1 não UUID ou 4.3.0 não UUID):

1. Instale o pacote de pré-migração de acordo com sua versão.

   >[!NOTE]
   >
   >* Você precisa de permissão de administrador para executar a migração.
   >* Recomenda-se a correção de arquivos com erros antes de prosseguir com a migração.

1. (Opcional) Execute a limpeza de versões no conteúdo para remover versões desnecessárias e acelerar o processo de migração. Para executar a limpeza de versão, selecione a opção **Limpeza de Versão** na tela de migração e vá para a interface do usuário usando a URL `http://<server- name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
   >[!NOTE]
   >
   >Este utilitário não remove nenhuma versão usada em linhas de base ou revisões ou tem rótulos.

1. Iniciar `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
1. Selecione **Avaliação de Compatibilidade** no painel esquerdo e procure um caminho de pasta.
1. Verifique a compatibilidade para listar as seguintes informações:
   * Total de arquivos
   * Total de versões
   * Tempo estimado para migração
   * Número de arquivos com erros

   ![guia de avaliação de compatibilidade na migração](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Selecione **Configurar validações** no painel esquerdo. Em seguida, **Selecione o mapa** e **Selecione a predefinição** do mapa para configurá-los. A lista de validação de saída atual exibe os arquivos de saída presentes antes da migração e pode ser validada em relação aos arquivos de saída gerados após a migração.

   ![Configurar a guia Validações na migração](assets/migration-configure-validation.png){width="800" align="left"}




## Migração

### Etapa 1: atualizar configuração

1. Verifique se o espaço livre disponível é pelo menos dez vezes o espaço ocupado pelo AEM (diretório crx-quickstart) durante a migração. Após concluir a migração, você poderá recuperar a maior parte do espaço em disco executando a compactação (consulte [Limpeza de revisão](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Habilitar *Habilitar Iniciadores de Fluxo de Trabalho de Processamento do Post* em `com.adobe.fmdita.config.ConfigManager` e *Habilitar Pós-processamento de Versão* em `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Instale a versão UUID da versão compatível sobre a versão não UUID. Por exemplo, se você estiver usando a build 4.1 não UUID, será necessário instalar a versão 4.1 do UUID e executar a migração.

1. Instale o novo pacote para migração de uuid.

1. Desabilite os fluxos de trabalho a seguir e qualquer outro fluxo de trabalho executado no `/content/dam` usando iniciadores no `http://<server-name>/libs/cq/workflow/content/console.html`.

   * Fluxo de trabalho do Ativo de atualização DAM
   * Fluxo de trabalho de writeback de metadados DAM

1. Desabilite *Habilitar Iniciadores de Fluxo de Trabalho de Processamento do Post* em `com.adobe.fmdita.config.ConfigManager` e desabilite *Habilitar Pós-processamento de Versão* em `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Desabilite a propriedade Habilitar validação (`validation.enabled`) no Serviço de Marcação CQ Diário.

1. Verifique se a pasta de propriedade `uuid.regex` está definida corretamente em `com.adobe.fmdita.config.ConfigManager`. Se estiver em branco, defina-o como o valor padrão - `^GUID-(?<id>.*)`.
1. Adicionar um agente de log separado para `com.adobe.fmdita.uuid` A resposta do navegador também está disponível em `/content/uuid-upgrade/logs`.

### Etapa 2: executar a migração e validar

#### Instalar o pacote de migração

1. Iniciar `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.

   ![Guia de atualização do sistema na migração](assets/migration-system-upgrade.png){width="800" align="left"}

1. Selecione **Atualização do sistema** no painel esquerdo para executar a migração. Inicie em uma pasta com dados menores antes de executá-la em `/content/dam`.

1. Selecione **Baixar relatório** enquanto a migração está em execução para verificar se todos os arquivos da pasta foram atualizados corretamente e se todos os recursos funcionam somente para essa pasta.


>[!NOTE]
>
> A migração de conteúdo pode ser executada em um nível de pasta, no `/content/dam` completo ou na mesma pasta (executar a migração novamente).

Além disso, é importante garantir que a migração de conteúdo seja feita para todos os ativos de mídia, como imagens e gráficos usados no conteúdo DITA.

#### Migração de linha de base e revisão

Selecione **Atualização de Linha de Base/Revisão** no painel esquerdo para migrar as linhas de base e revisar no nível da pasta.

![Guia Linha de base e revisão na migração](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Etapa 3: restaurar a configuração

Depois de migrar o servidor com êxito, ative o pós-processamento, a marcação e os workflows a seguir (incluindo todos os outros workflows que foram desativados inicialmente durante a migração) para continuar trabalhando no servidor.

* Fluxo de trabalho do Ativo de atualização DAM
* Fluxo de trabalho de metadados DAM

>[!NOTE]
>
>Se alguns arquivos não forem processados ou corrompidos antes da migração, eles serão corrompidos antes da migração e permanecerão corrompidos mesmo após a migração.

## Validação de migração

1. Depois que a migração for concluída, selecione **Validar atualização do sistema** no painel esquerdo e valide os arquivos de saída antes e depois da migração para garantir que a migração seja bem-sucedida.

   ![Validar guia de atualização do sistema na migração](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Depois que a validação for concluída, a maior parte do espaço em disco poderá ser recuperada executando a compactação (consulte `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).
