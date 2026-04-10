---
title: Atualizar o Adobe Experience Manager Guides
description: Saiba como atualizar o Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '1661'
ht-degree: 0%

---

# Atualizar o Adobe Experience Manager Guides para a versão 4.6.0 e superior

Este artigo fornece instruções para atualizar suas versões do Experience Manager Guides para 4.6.0 e superior.

>[!NOTE]
>
> Siga as instruções de atualização específicas para a versão licenciada do seu produto.

Você pode atualizar sua versão atual do Experience Manager Guides para a versão 5.1.0 Service Pack 3:

- Se você estiver usando a versão 5.1.0 ou 5.1.x, é possível atualizar diretamente para a versão 5.1.0 Service Pack 3.
- Se você estiver usando a versão 4.6.0, 4.6.x, 5.0.0 ou 5.0.x, será necessário atualizar para a versão 5.1.0.
- Se você estiver em uma versão anterior à 4.6.0, consulte [Atualizar o Adobe Experience Manager Guides para a versão 4.4.0 e anterior](./upgrade-aemg-prev-versions.md) para obter instruções detalhadas de atualização.

>[!NOTE]
>
> Você deve instalar o service pack do AEM antes de atualizar a versão do Experience Manager Guides.

Para obter mais detalhes, consulte os seguintes procedimentos:

- [Atualizar para a versão 5.1.0](#upgrade-to-version-510)
- [Atualizar para a versão 5.0.0](#upgrade-to-version-500)
- [Atualizar para a versão 4.6.0](#upgrade-to-version-460)

>[!IMPORTANT]
>
> Antes de começar a atualização, faça um backup completo do sistema para evitar perda de dados.


## Atualizar para a versão 5.1.0


>[!IMPORTANT]
>
> Se você estiver usando o AEM 6.5 e planeja migrar para o AEM 6.5 LTS, conclua a atualização do AEM primeiro antes de prosseguir com a atualização do Experience Manager Guides 5.1.0. Para obter detalhes, consulte [Atualização para o Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

**Pré-requisitos**

>[!NOTE]
>
>Se estiver atualizando para o 5.1.0 Service Pack 3, você precisa estar na versão 5.1.0 ou 5.1.x do Experience Manager Guides. O processo de atualização da versão 5.1.0 do Service Pack 3 segue as mesmas etapas da versão 5.1.0.

Antes de iniciar o processo de atualização do Experience Manager Guides 5.1.0, verifique se você tem:

1. Atualizado para o Experience Manager Guides versão 4.6.3, 4.6.4, 5.0.0 ou 5.0.0 Service Pack 1.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.

>[!NOTE]
>
> O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

**Instalar versão 5.1.0**

Baixe o pacote da versão 5.1.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html) e siga as instruções fornecidas em [Fluxo de trabalho de atualização de instalação e pós-instalação](#installation-and-post-installation-upgrade-workflow) para concluir o processo de atualização.


## Atualizar para a versão 5.0.0

>[!TIP]
>
> A atualização para a versão 5.0.0 Service Pack 3 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 5.0.0 Service Pack 2, 5.0.0 Service Pack 1 ou 5.0.0, é possível atualizar diretamente para a versão 5.0.0 Service Pack 3. As etapas de atualização são as mesmas da versão 5.0.0.

>[!NOTE]
>
> O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

**Pré-requisitos**

Antes de iniciar o processo de atualização do Experience Manager Guides 5.0.0, verifique se você tem:

1. Atualizado para a versão 4.6.3, 4.6.1, 4.6.0 ou 4.4 do Experience Manager Guides.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.


**Instalar versão 5.0.0**

Baixe o pacote da versão 5.0.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html) e siga as instruções fornecidas em [Fluxo de trabalho de atualização de instalação e pós-instalação](#installation-and-post-installation-upgrade-workflow) para concluir o processo de atualização.

## Atualizar para a versão 4.6.0

>[!TIP]
>
> É recomendável instalar o 4.6.0 Service Pack 4 sobre o versão 4.6.0, 4.6.0 Service Pack 1 ou 4.6.0 Service Pack 3. O processo de atualização do Service Pack 4.6.0 segue as mesmas etapas do release 4.6.0.

A atualização para a versão 4.6.0 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 4.4.0, 4.3.1, 4.3.0, 4.2 ou 4.2.1 (Hotfix 4.2.1.3), será possível atualizar diretamente para a versão 4.6.0.

>[!NOTE]
>
> O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

**Pré-requisitos**

Antes de iniciar o processo de atualização do Experience Manager Guides 4.6.0, verifique se você tem:

1. Atualizado para Experience Manager Guides versão 4.3.1, 4.3.0 ou 4.2.1 (Hotfix 4.2.1.3).
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.

**Instalar versão 4.6.0**

Baixe o pacote da versão 4.6.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html) e siga as instruções fornecidas em [Fluxo de trabalho de atualização de instalação e pós-instalação](#installation-and-post-installation-upgrade-workflow) para concluir o processo de atualização.

## Fluxo de trabalho de atualização da instalação e pós-instalação

### Instalar o pacote de versão

Execute as seguintes etapas para instalar o pacote de versão:

1. Instale o pacote de versão no qual deseja atualizar.
1. Você pode optar por pressionar o acionador para iniciar o trabalho de atualização do mapa de tradução. Para obter detalhes, consulte [Habilitar gatilho de script por meio de um Servlet](#enable-trigger-of-script-via-a-servlet).

1. Após concluir a instalação do pacote, aguarde a seguinte mensagem nos logs:

   `Completed the post deployment setup script`

   A mensagem acima indica que todas as etapas da instalação foram concluídas.

   Caso encontre qualquer um dos erros a seguir, relate-os à equipe de sucesso do cliente:

   - Erro no script de configuração pós-implantação
   - Exceção ao portar o MAP de tradução
   - Não é possível portar o mapa de conversão de v1 para v2 para a propriedade
1. (Opcional) Atualização do plug-in do conector Oxygen lançado com a versão para a qual você está atualizando.
1. Limpe o cache do navegador após instalar o pacote.

### Processo pós-instalação

Depois de instalar o Experience Manager Guides, você pode mesclar as várias configurações aplicáveis da versão recém-instalada à configuração.

>[!NOTE]
>
> O modelo dam-update-asset pode ser personalizado. Se alguma personalização foi feita, precisamos sincronizar as personalizações e o Experience Manager Guides na cópia de trabalho do modelo.

**Fluxo de trabalho do Ativo de atualização do DAM \(Alterações pós-processamento\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Selecione **Fluxo de trabalho do Ativo de atualização do DAM**.
1. Selecione **Editar**.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver presente, verifique se as personalizações estão sincronizadas.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver ausente, execute as seguintes etapas para inseri-lo:

   - Selecione **Inserir componente** \(Responsável pelo pós-processamento do Experience Manager Guides como a etapa final do processo\).
   - Configure a **Etapa do processo** com os detalhes abaixo:

     **Guia comum:**

      - **Título:** Iniciador de Pós-Processamento DXML

      - **Descrição**: etapa do iniciador do pós-processamento DXML que acionará um trabalho de sling para pós-processamento DXML do ativo modificado/criado

     **Guia Processo**

      - Selecione o **Iniciador de Pós-Processamento de DXML** na lista suspensa **Processo**
      - Selecionar **Avanço do manipulador**
      - Selecionar **Concluído**

1. Selecione **Sincronizar** no canto superior direito depois de concluir as alterações. Você receberá uma notificação de sucesso.

   >[!NOTE]
   >
   > Atualize e verifique se as alterações personalizadas e a etapa de pós-processamento do Experience Manager Guides estão presentes no modelo de fluxo de trabalho final.

1. Depois que o **fluxo de trabalho do Ativo de atualização do DAM** for validado, verifique as configurações do iniciador correspondentes. Para fazer isso, acesse a interface do Fluxo de trabalho do AEM e abra iniciadores.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Localize e faça alterações \(se necessário\) nos dois inicializadores a seguir \(que devem estar ativos\) correspondentes ao **fluxo de trabalho do Ativo de atualização do DAM**:

1. Iniciador para &quot;*Nó Criado*&quot; para **Fluxo de trabalho do Ativo de Atualização do DAM**- para a condição `"jcr:content/jcr:mimeType!=video"`, o valor de &#39;Globbing&#39; deve ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; deve ter `"event-user-data:changedByWorkflowProcess"`.
   - Iniciador para &quot;*Nó Modificado*&quot; para **Fluxo de trabalho do Ativo de Atualização do DAM -** para a condição &quot;`jcr:content/jcr:mimeType!=video`&quot;, o valor &#39;Globbing&#39; deve ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` deve ter `"event-user-data:changedByWorkflowProcess"`.

1. Quando a atualização for concluída, verifique se todas as personalizações/sobreposições estão validadas e atualizadas para corresponder ao novo código do aplicativo. Alguns exemplos são apresentados abaixo:
   - Quaisquer componentes sobrepostos do `/libs/fmditaor/libsshould` devem ser comparados com o novo código de produto, e as atualizações devem ser feitas em arquivos sobrepostos em/apps.
   - Qualquer categoria `clientlib` usada do produto deve ser revisada para alterações. Todas as configurações substituídas `\(examples below\)` devem ser comparadas com as mais recentes para obter os recursos mais recentes:
   - elementmapping.xml
   - `ui\_config.json\(may have been set in folder profiles\)`
   - emendado `com.adobe.fmdita.config.ConfigManager`

1. Se você tiver adicionado personalizações em damAssetLucene, talvez seja necessário aplicá-las novamente. Depois de fazer essas alterações, defina reindex como true. Isso reindexará todos os nós existentes com as personalizações. Depois de concluído, o sinalizador de reindexação será definido como falso novamente. Isso pode levar algumas horas, dependendo do número de ativos no sistema.

### Etapas para reindexar os índices do Experience Manager Guides

1. Abra `crx/de` e navegue até o caminho do índice: `/oak:index/guidesAssetProperties`
2. Defina a propriedade de reindexação como `true` (`false` por padrão) e clique em **Salvar tudo**.
3. Quando a reindexação for concluída, a propriedade reindex será definida novamente como `false`, e a contagem de reindexação será incrementada em 1.

   >[!NOTE]
   >
   > Isso pode levar alguns minutos, dependendo da quantidade de dados presentes.
4. Siga as mesmas etapas para outros índices adicionados ou modificados: `guidesBulkActivation`, `guidesPeerLinkIndex` e `guidesKonnectTemplateIndex`.

### Etapas para indexar o conteúdo existente

Execute as seguintes etapas para indexar o conteúdo existente:

- Execute uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados || Exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- A API retornará um `jobId`. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com a ID do trabalho para o mesmo ponto de extremidade - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por exemplo: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.


>[!NOTE]
>
> Se você estiver usando o esquema personalizado, defina o caminho dos arquivos DTD e XSD catalog.xml personalizados no repositório do AEM na opção **Integrar catálogos**.

### Etapas para lidar com o conflito `'fmdita rewriter'`

O Experience Manager Guides tem um módulo [**personalizado de reescrita do sling**](../install-conf-guide/conf-output-generation.md#custom-rewriter) para manipular os links gerados no caso de mapas cruzados (links entre os tópicos de dois mapas diferentes).

Se você tiver outro reescritor sling personalizado em sua base de código, use um valor de `'order'` maior que 50, pois o reescritor Experience Manager Guides sling usa `'order'` 50.  Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de regravação de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta atualização, como o valor de `'order'` é alterado de 1000 para 50, você precisa mesclar o reescritor personalizado existente, se houver, com `'fmdita-rewriter'`.


### Etapas para reindexar o damAssetLucene

A definição do índice é atualizada para damAssetLucene com AEM Guides. Depois de atualizar para a versão necessária, consulte [este artigo](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) para reindexar o damAssetLucene.

>[!NOTE]
>
> Ao seguir a documentação, verifique se ambas as propriedades (`reindex=true` e `reindex-async=true` para `/oak:index/damAssetLucene`) foram atualizadas simultaneamente por meio da operação Salvar.

