---
title: Atualizar Versões Anteriores Do Adobe Experience Manager Guides On Premise
description: Saiba como atualizar o Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3159'
ht-degree: 0%

---

# Atualizar o Adobe Experience Manager Guides no local (Versão 4.4.0 e anterior)

Este artigo fornece instruções para atualizar **Adobe Experience Manager Guides** versões **anteriores a 4.6.0** (até **4.4.0** inclusive).

Se você estiver em uma versão **anterior a 3.8.5**, consulte a seção **Atualizar Experience Manager Guides** no guia de instalação específico do produto, disponível no [arquivo PDF da ajuda do Adobe Experience Manager Guides](https://helpx.adobe.com/br/xml-documentation-for-experience-manager/archive.html).

Para obter instruções de atualização para versões mais recentes, consulte [Atualizar o Adobe Experience Manager Guides para a versão 4.6.0 e posterior](./upgrade-aemg-latest-version.md).

## Antes de começar

>[!NOTE]
>
> Você deve atualizar as instruções específicas para a versão licenciada do seu produto e instalar o service pack do AEM antes de atualizar a versão do Experience Manager Guides.

>[!IMPORTANT]
>
> Antes de começar a atualização, faça um **backup completo do sistema** para evitar perda de dados.

## Caminhos de atualização abordados neste artigo

Este artigo inclui procedimentos para:

- [Atualizar para a versão 4.4.0](#upgrade-to-version-440)
- [Atualizar para a versão 4.3.1.5](#upgrade-to-version-4315)
- [Atualizar para a versão 4.3.1](#upgrade-to-version-431)
- [Atualizar para a versão 4.3.0](#upgrade-to-version-430)
- [Atualizar para a versão 4.2.1](#upgrade-to-version-421)
- [Atualizar para a versão 4.2](#upgrade-to-version-42)
- [Atualização da versão 3.8.5 para a versão 4.0](#upgrade-from-version-385-to-version-40)


## Pré-requisitos globais (aplica-se a todos os upgrades, a menos que um procedimento indique o contrário)

Antes de executar o processo de atualização, conclua estas tarefas:

1. Importar comentários de revisão em tópicos abertos para revisão.
2. Fechar todas as análises ativas.
3. Feche todas as tarefas de tradução.
4. Desinstale todos os hotfixes do Experience Manager Guides instalados com base na versão anterior (versão principal ou patch).

Algumas atualizações também exigem a definição do nível de log como `INFO` para uma classe de atualização de tradução e o registro em log em um arquivo separado; esses requisitos são chamados nos procedimentos de atualização relevantes.

## Atualização da versão 3.8.5 para a versão 4.0

>[!NOTE]
>
> Este processo de atualização é aplicável **somente** de **3.8.5** para **4.0**. Para atualizações do **3.4 ou superior** para o **3.8.5**, consulte o guia de instalação específico do produto disponível no [arquivo PDF da ajuda do Adobe Experience Manager Guides](https://helpx.adobe.com/br/xml-documentation-for-experience-manager/archive.html).

Se você estiver usando a versão **3.8.5** do Experience Manager Guides, é possível atualizar para a versão **4.0** sem desinstalar a versão anterior.

### Antes de instalar a versão 4.0

1. Verifique se o Experience Manager Guides está na versão **3.8.5**.
2. Baixe o pacote de script de atualização: pesquise por **&quot;Pacote de Atualização da solução XML Documentation 4.0&quot;** no Portal de Distribuição de Software da Adobe (baixa um `.zip`).
3. Carregue o pacote para o AEM por meio do **Gerenciador de Pacotes** e instale-o.
4. Após a instalação do pacote de atualização, execute os scripts na ordem descrita abaixo.

**Verificar API de compatibilidade de atualização**

Essa API foi projetada para avaliar o status atual do sistema e relatar se a atualização é possível ou não. Para executar esse script, acione o endpoint fornecido abaixo:

| Ponto final | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Tipo de solicitação | **GET** <br> **Observação**: você pode usar um navegador da Web no qual esteja conectado à instância do AEM como administrador. |
| Resposta esperada | -   Caso todos os nós necessários possam ser movidos, você receberá uma verificação aprovada. <br>-   Caso um nó esteja presente no local de destino, você receberá um erro relevante. Limpe o repositório \(delete node /var/dxml\) e reinstale o pacote de atualização e acione esse endpoint novamente. <br>**Observação:** não é um erro comum, pois o local de destino não foi usado anteriormente pelo Experience Manager Guides 3.x. <br> -   Se o script não for bem-sucedido, não continue e relate à equipe de sucesso do cliente. |

**API de migração de dados do sistema**

Esta API foi projetada para migrar os dados do sistema conforme mencionado na seção **Mapeamento de Migração**.

1. Não execute este script se a API de verificação de compatibilidade de atualização falhar \(não continuar\).
1. Depois que a API Verificar compatibilidade de atualização retornar sucesso, você poderá executar o script de atualização.

| Ponto final | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Tipo de solicitação | **POST** <br>**Observação**: este script é uma solicitação POST, portanto, deve ser executado por meio de agentes como o Postman. |
| Resposta esperada | -   Depois que a migração for bem-sucedida, você poderá instalar a solução XML Documentation versão 4.0.<br>-   Caso haja erros, restaure para o último ponto de verificação e compartilhe os logs de erro junto com a saída da API com a equipe de sucesso do cliente. |


**Mapeamento de migração**

Essa API migra todos os dados do local de origem para o local de destino.

| Origem | Destino |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

### Instalar versão 4.0

1. Instale a versão 4.0 somente se as etapas de atualização forem bem-sucedidas.
1. Baixe o pacote da versão 4.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html):

   - Se você estiver usando a versão UUID do software, procure por &quot;Versão 4.0 UUID para a solução XML Documentation para o AEM 6.5&quot;.
   - Se você estiver usando uma versão não UUID do software, procure por &quot;Versão 4.0 não UUID para a solução da XML Documentation para o AEM 6.5&quot;.
Faça upload do pacote para a instância do servidor do AEM existente\(s\) usando o Gerenciador de pacotes do CRX e instale-o.

     >[!NOTE]
     >
     > Aguarde até que todos os componentes do sistema sejam iniciados.

1. Limpe o cache do navegador após instalar o pacote.
1. Se um dispatcher estiver configurado na instância do AEM Author, execute as seguintes etapas:
   - Verifique se os seguintes itens são tratados nas regras do dispatcher:
   - O padrão de URL /home/users/\*/references está na lista de permissões.
   - O padrão de URL /libs/cq/security/userinfo.json não é armazenado em cache.
1. Limpar o cache do Dispatcher \(para limpar qualquer `clientlibs` armazenado em cache\).

## Atualizar para a versão 4.2

Você pode atualizar diretamente para a versão **4.2** se estiver usando a versão **4.0**, **4.1** ou **4.1.x**.

### Antes de instalar a versão 4.2

Antes de iniciar o processo de atualização do Experience Manager Guides 4.2, verifique se você tem:

1. Atualizado para o Experience Manager Guides **4.0**, **4.1** ou **4.1.x**.
2. Todas as tarefas de tradução foram fechadas.
3. Defina o nível de log como `INFO` para `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e registre em um novo arquivo de log (por exemplo, `logs/translation_upgrade.log`).

   >[!NOTE]
   > 
   > Você deve fechar todas as revisões ativas. Se as revisões não forem fechadas durante a atualização para a versão 4.2, as tarefas de revisão em andamento mais antigas poderão continuar a abrir páginas de revisão mais antigas; as novas tarefas de revisão criadas após a atualização exibem as atualizações de funcionalidade mais recentes.

### Instalar versão 4.2

1. Baixe o pacote **4.2** do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
2. Instale o pacote 4.2.
3. Após a instalação, aguarde a seguinte mensagem nos logs:

   `Completed the post deployment setup script`

   A mensagem acima indica que todas as etapas de instalação foram concluídas.

   Se você encontrar algum dos seguintes erros, relate-os ao Sucesso do cliente:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`

4. (Opcional) Atualização do plug-in do conector Oxygen lançado com a versão 4.2.
5. Limpe o cache do navegador após instalar o pacote.
6. Continue atualizando as personalizações conforme detalhado na próxima seção.

### Após instalar a versão 4.2

>[!IMPORTANT]
>
> O modelo de alta tecnologia não é exibido no servidor atualizado. Para incluir o modelo de alta tecnologia no servidor, você pode copiá-lo: Source: `/libs/fmdita/pdf/Hi-Tech` Destino: `/content/dam/dita-templates/pdf`.

Em seguida, prossiga com as tarefas de pós-atualização compartilhadas em [Tarefas de pós-atualização comuns (todas as versões)](#common-postupgrade-tasks-all-versions).

## Atualizar para a versão 4.2.1

>[!TIP]
>
> É recomendável instalar o **Hotfix4.2.1.3** sobre a versão **4.2.1**.

Você pode atualizar diretamente para a versão **4.2.1** se estiver usando o **4.1**, **4.1.x** ou **4.2**.

>[!NOTE]
>
> O pós-processamento e a indexação podem levar algumas horas. Inicie a atualização fora dos horários de pico.

### Antes de instalar a versão 4.2.1

1. Atualize para o Experience Manager Guides **4.1**, **4.1.x** ou **4.2**.
2. Feche todas as tarefas de tradução.
3. Defina o nível de log como `INFO` para `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e registre em um novo arquivo (por exemplo, `logs/translation_upgrade.log`).

>[!NOTE]
>
> Você deve fechar todas as revisões ativas (mesmo comportamento do 4.2).

### Instalar versão 4.2.1

1. Baixe o pacote **4.2.1** do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
2. Instale o pacote 4.2.1.
3. Opcionalmente, acione o trabalho de atualização do mapa de tradução. Para obter detalhes, consulte [Habilitar gatilho de script por meio de um Servlet](#enable-trigger-of-script-via-a-servlet).

4. Após a instalação, aguarde por: `Completed the post deployment setup script` em logs.

   Relate esses erros ao Sucesso do cliente:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Opcional) Atualização do plug-in do conector Oxygen lançado com a versão **4.2**
6. Limpar o cache do navegador.
7. Continuar com [tarefas comuns pós-atualização (todas as versões)](#common-postupgrade-tasks-all-versions).

### Após instalar a versão 4.2.1

>[!IMPORTANT]
>
> O modelo de alta tecnologia não é exibido no servidor atualizado. Para incluir o modelo de alta tecnologia no servidor, você pode copiá-lo: Source: `/libs/fmdita/pdf/Hi-Tech` Destino: `/content/dam/dita-templates/pdf`.

Prossiga com [Tarefas comuns pós-atualização (todas as versões)](#common-postupgrade-tasks-all-versions) e (se necessário) [Indexe conteúdo existente para localizar e substituir o mapa](#index-existing-content-for-map-find-and-replace).


## Atualizar para a versão 4.3.0

A atualização para a versão 4.3.0 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 4.2 ou 4.2.x, é possível atualizar diretamente para a versão 4.3.0.

>[!NOTE]
>
>O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

### Antes de instalar a versão 4.3.0

Antes de iniciar o processo de atualização do Experience Manager Guides 4.3.0, verifique se você tem:

1. Atualização para o Experience Manager Guides versão 4.2 ou 4.2.x e conclusão das respectivas etapas de instalação.
1. Todas as tarefas de tradução foram fechadas.

### Instalar a versão 4.3.0

1. Baixe o pacote da versão 4.3.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote da versão 4.3.0.
1. Limpe o cache do navegador após instalar o pacote.
1. Atualize o arquivo `ui_config.json` da guia **Configuração do Editor XML** no Perfil de Pasta.

### Após instalar a versão 4.3.0

Continue com:

- [Tarefas comuns após a atualização (todas as versões)](#common-postupgrade-tasks-all-versions)
- Se aplicável: [Pós-processar conteúdo existente para o relatório de links corrompidos](#post-process-existing-content-for-broken-link-report)

## Atualizar para a versão 4.3.1

A atualização para a versão 4.3.1 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 4.3.0, 4.2 ou 4.2.1, é possível atualizar diretamente para a versão 4.3.1.

>[!NOTE]
>
>O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

### Antes de instalar a versão 4.3.1

Antes de iniciar o processo de atualização do Experience Manager Guides 4.3.1, verifique se você tem:

1. Atualização para o Experience Manager Guides versão 4.3.0, 4.2 ou 4.2.1 e conclusão das respectivas etapas de instalação.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.

### Instalar a versão 4.3.1

1. Baixe o pacote de versão 4.3.1 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote da versão 4.3.1.
1. Opcionalmente, acione o trabalho de atualização do mapa de tradução. Para obter detalhes, consulte [Habilitar gatilho de script por meio de um Servlet](#enable-trigger-of-script-via-a-servlet).
1. Após a instalação, aguarde por: `Completed the post deployment setup script` em logs.
Relate esses erros ao Sucesso do cliente:\
   `Error in post deployment setup script`, `Exception while porting the translation MAP`, `Unable to port translation map from v1 to v2 for property`
1. (Opcional) Atualização do plug-in do conector Oxygen lançado com a versão **4.2**.
1. Limpar o cache do navegador.

### Após instalar a versão 4.3.1

Continue com:

- [Tarefas comuns após a atualização (todas as versões)](#common-postupgrade-tasks-all-versions)
- Se aplicável: [Indexar conteúdo existente para localizar e substituir mapa](#index-existing-content-for-map-find-and-replace)
- Se aplicável: [Pós-processar conteúdo existente para o relatório de links corrompidos](#post-process-existing-content-for-broken-link-report)


## Atualizar para a versão 4.3.1.5

Você pode atualizar diretamente para **4.3.1.5** se estiver usando a versão **4.3.1**.

### Instalar versão 4.3.1.5

1. Baixe o pacote **4.3.1.5** do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
2. Instale o pacote 4.3.1.5.
3. Aguarde até que o processo de instalação seja concluído com êxito.
4. Continue atualizando as personalizações conforme detalhado na próxima seção.

## Após instalar a versão 4.3.1.5

>[!NOTE]
>
>Se quiser usar o pacote org.apache.velocity, execute as seguintes etapas antes de fazer upload do pacote:
> 1. Ir para `<server>:<port>/system/console/bundles`
> 1. Procure por org.apache.velocity.
> 1. Desinstale o pacote pesquisado.
> 1. Instale o pacote de velocidade necessário.

1. Quando a atualização for concluída, verifique se todas as personalizações/sobreposições estão validadas e atualizadas para corresponder ao novo código do aplicativo. Alguns exemplos são apresentados abaixo:
   - Todos os componentes sobrepostos de `/libs/fmdita` ou ` /libs` devem ser comparados com o novo código de produto e as atualizações devem ser feitas em arquivos sobrepostos em `/apps`.
   - Todas as categorias de clientlib usadas do produto devem ser revisadas para alterações. Todas as configurações substituídas \(exemplos abaixo\) devem ser comparadas com as mais recentes para obter os recursos mais recentes:
   - `elementmapping.xml`
   - `ui\_config.json\` (pode ter sido definido em perfis de pasta\)
   - emendado `com.adobe.fmdita.config.ConfigManager`


## Atualizar para a versão 4.4.0

Você pode atualizar diretamente para **4.4.0** se estiver usando: **4.3.1**, **4.3.0**, **4.2** ou **4.2.1 (Hotfix 4.2.1.3)**.

>[!NOTE]
>
>O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

### Antes de instalar a versão 4.4.0

Antes de iniciar o processo de atualização do Experience Manager Guides 4.4.0, verifique se você tem:

1. Atualizado para o Experience Manager Guides versão 4.3.1, 4.3.0 ou 4.2.1 (Hotfix 4.2.1.3) e concluído sua respectiva etapa de instalação.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.

### Instalar a versão 4.4.0

1. Baixe o pacote da versão 4.4.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
2. Instale o pacote 4.4.0.
3. Opcionalmente, acione o trabalho de atualização do mapa de tradução. Para obter detalhes, consulte [Habilitar gatilho de script por meio de um Servlet](#enable-trigger-of-script-via-a-servlet).
4. Após concluir a instalação do pacote, aguarde a seguinte mensagem nos logs:

   `Completed the post deployment setup script`

   A mensagem acima indica que todas as etapas da instalação foram concluídas.

   Caso encontre qualquer um dos seguintes prefixos de ERRO, relate-os à equipe de sucesso do cliente:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Opcional) Atualize o plug-in do conector Oxygen lançado com a versão **4.4.0**.
6. Limpar o cache do navegador.
7. Continuar com:

   - [Tarefas comuns pós-atualização (todas as versões)](#common-ppostupgrade-tasks-all-versions)
   - [Indexar conteúdo existente para localizar e substituir o mapa](#index-existing-content-for-map-find-and-replace) (somente se aplicável)
   - [Pós-processar conteúdo existente para o relatório de links corrompidos](#post-process-existing-content-for-broken-link-report) (somente se aplicável)
   - [Atualização do mapa de tradução (gatilho de servlet)](#translation-map-upgrade-servlet-trigger) (Somente se aplicável)


## Tarefas comuns pós-atualização (todas as versões)

Depois de instalar o Experience Manager Guides, talvez seja necessário mesclar as configurações aplicáveis da versão recém-instalada à configuração.

>[!NOTE]
>
> O modelo de fluxo de trabalho **Ativo de atualização do DAM** pode ser personalizado. Se você tiver personalizações, sincronize-as com as alterações do Experience Manager Guides na cópia de trabalho do modelo.

### Validar o fluxo de trabalho do Ativo de atualização do DAM (alterações pós-processamento)

1. Abra a interface do usuário de Modelos de fluxo de trabalho do AEM (exemplo mostrado na origem):\
   `http://<host>:4502/libs/cq/workflow/admin/console/content/models.html`
2. Selecione **Fluxo de trabalho do Ativo de atualização do DAM**.
3. Selecione **Editar**.
4. Se o componente **Iniciador de Pós-Processamento DXML** estiver presente, verifique se as personalizações estão sincronizadas.
5. Se o componente estiver ausente, insira-o:
   1. Clique em **Inserir componente** (responsável pelo pós-processamento dos Guias como etapa final).
   2. Configure a **Etapa do processo**:
      **Guia comum**
- Título: `DXML Post Process Initiator`
- Descrição: `DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset`
      **Guia Processo**
- Processo: selecionar `DXML Post Process Initiator`
- Selecionar `Handler Advance`
- Selecionar `Done`
   3. Clique em **Sincronizar** na parte superior direita depois de concluir as alterações. Você receberá uma notificação de sucesso.

>[!NOTE]
>
> Atualize e verifique se as alterações personalizadas e a etapa de pós-processamento do Experience Manager Guides estão presentes no modelo de fluxo de trabalho final.

### Validar configurações do inicializador

1. Vá para a interface do Fluxo de Trabalho do AEM e abra **Iniciadores**.

```http
    http://localhost:4502/libs/cq/workflow/content/console.html
```

1. Localize e faça alterações \(se necessário\) nos dois inicializadores a seguir \(que devem estar ativos\) correspondentes ao **fluxo de trabalho do Ativo de atualização do DAM**:

1. Iniciador para &quot;*Nó Criado*&quot; para **Fluxo de trabalho do Ativo de Atualização do DAM**- para a condição `"jcr:content/jcr:mimeType!=video"`, o valor de &#39;Globbing&#39; deve ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` deve ter `"event-user-data:changedByWorkflowProcess"`.
   - Iniciador do *Nó Modificado* do **Fluxo de trabalho do Ativo de Atualização do DAM -** para a condição &quot;`jcr:content/jcr:mimeType!=video`&quot;, o valor de &quot;Globbing&quot; deve ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` deve ter `"event-user-data:changedByWorkflowProcess"`.

### Validar sobreposições e personalizações

Depois que a atualização for concluída:

1. Quando a atualização for concluída, verifique se todas as personalizações/sobreposições estão validadas e atualizadas para corresponder ao novo código do aplicativo. Alguns exemplos são apresentados abaixo:
   - Quaisquer componentes sobrepostos de/libs/fmditaor/libsdevem ser comparados com o novo código do produto e as atualizações devem ser feitas em arquivos sobrepostos em/apps.
   - Todas as categorias de clientlib usadas do produto devem ser revisadas para alterações. Todas as configurações substituídas \(exemplos abaixo\) devem ser comparadas com as mais recentes para obter os recursos mais recentes:
   - elementmapping.xml
   - ui\_config.json\(pode ter sido definido em perfis de pasta\)
   - emendado `com.adobe.fmdita.config.ConfigManager`

1. Se você tiver adicionado personalizações em damAssetLucene, talvez seja necessário aplicá-las novamente. Depois de fazer essas alterações, defina reindex como true. Isso reindexará todos os nós existentes com as personalizações. Depois de concluído, o sinalizador de reindexação será definido como falso novamente. Isso pode levar algumas horas, dependendo do número de ativos no sistema.

## Indexar conteúdo existente para localizar e substituir mapa

Esta seção consolida o procedimento de **indexação** repetido usado para habilitar os novos recursos de **localização e substituição** em nível de mapa.

**Quando você puder ignorar a indexação**

A origem inclui notas &quot;ignoradas&quot; dependendo do caminho de atualização (por exemplo, &quot;Você não precisa executar essas etapas se atualizar do 4.3.0 ou 4.3.1&quot; e notas semelhantes). Siga a nota de salto declarada na seção de atualização.

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa:

1. Execute uma solicitação POST (com autenticação):

```http
POST http://<server:port>/bin/guides/map-find/indexing
```

Parâmetros opcionais compatíveis na origem:

- Indexar caminhos de mapa específicos (o padrão é indexar todos os mapas):

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>
  ```

- Mapas DITA de índice em uma pasta raiz (e suas subpastas):

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test
  ```

  >[!NOTE]
  >
  > Se `paths` e `root` forem aprovados, somente `paths` será considerado.

1. A API retorna um `jobId`. Para verificar o status, envie uma solicitação GET:

   ```http
   GET http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}
   ```

   Comportamento de conclusão esperado:

   - Ao concluir, o GET responde com sucesso e indica se algum mapa falhou.
   - Confirmar mapas indexados com êxito nos logs do servidor.

### Verificar se a indexação damAssetLucene está completa (quando aplicável)

A fonte observa que a indexação de damAssetLucene pode levar horas, dependendo do tamanho dos dados, e você pode confirmar a conclusão quando `reindex` estiver `false` em:

`http://<server:port>/oak:index/damAssetLucene`

Se você tiver adicionado personalizações em `damAssetLucene`, talvez precise aplicá-las novamente depois que a reindexação for concluída.

### Solução alternativa para &quot;consulta lida ou percorreu mais de 100.000 nós&quot; (se o processo falhar)

Se o trabalho de indexação falhar e o erro mostrar:

&quot;A consulta leu ou percorreu mais de 100.000 nós. Para não afetar outras tarefas, o processamento foi interrompido.&quot;

Tente esta solução alternativa a partir da origem:

1. No índice oak `damAssetLucene`, adicione a propriedade booleana `indexNodeName=true` em `/oak:index/damAssetLucene/indexRules/dam:Asset`.
2. Adicione um novo nó chamado `excerpt` em `/oak:index/damAssetLucene/indexRules/dam:Asset/properties` e defina as propriedades conforme mostrado na origem:
   - `name=rep:excerpt`
   - `propertyIndex=true`
   - `notNullCheckEnabled=true`
3. Reindexe `damAssetLucene` definindo `reindex=true` e aguarde até ele se tornar `false` novamente (pode levar horas).
4. Execute novamente o script de indexação (repita o POST e o rastreamento de jobs).

## Pós-processar conteúdo existente para o relatório de links quebrados

Esta seção consolida o procedimento **pós-processamento** repetido usado para habilitar o **relatório de links desfeitos**.

**Quando você puder ignorar o pós-processamento**

A origem inclui notas &quot;ignorar&quot; dependendo do caminho de atualização (por exemplo, &quot;Você não precisa executar essas etapas se atualizar da 4.3.0&quot; ou &quot;da 4.3.0 ou 4.3.1&quot;). Siga a nota de salto declarada na seção de atualização.

Execute as seguintes etapas para ativar o relatório de links quebrados:

1. (Opcional) Aumente o queryLimitReads do Oak para repositórios grandes

   Se houver mais de **100.000 arquivos DITA**, atualize `queryLimitReads` em `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` para um valor maior que o número de ativos (exemplo: `200000`), reimplante e prossiga.

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 <br> Valor Padrão: 100000 |

1. Execute as seguintes APIs para executar o pós-processamento em todos os arquivos:

   | Ponto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitação | **POST** Este script é uma solicitação POST, portanto, deve ser executado por agentes como o Postman. |
   | Resposta esperada | A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com a ID do trabalho para o mesmo ponto de extremidade.<br> Exemplo de URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Ponto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitação | **GET** |
   | Param | jobId: transmita a jobId recebida da solicitação de publicação anterior. |
   | Resposta esperada | - Quando o trabalho for concluído, a solicitação do GET responderá com êxito. <br> - Em caso de erro, compartilhe os logs de erro junto com a saída da API com a equipe de sucesso do cliente.  <br>Exemplo de URL: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Reverta para o valor padrão ou existente anterior de `queryLimitReads` se você o alterou na etapa 1.

## Ativar acionador de script por meio de um Servlet

Várias versões incluem uma etapa opcional para acionar um trabalho de atualização do mapa de tradução por meio de um servlet. Esta seção consolida esse procedimento repetido e inclui todos os detalhes fornecidos na origem.


>[!NOTE]
>
> Não é necessário executar essas etapas se você atualizar do 4.3.0 ou 4.3.1.

PUBLICAÇÃO:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Resposta:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

Na resposta JSON acima, a chave `lockNodePath` contém o caminho para o nó criado no repositório que aponta para o trabalho enviado. Ela será excluída automaticamente quando o trabalho for concluído. Até lá, é possível consultar esse nó para saber o status atual do trabalho.

Procure por `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` e `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` antes de prosseguir para as próximas etapas.

>[!NOTE]
>
> Você deve verificar se o nó ainda está presente e o status do trabalho.

**GET**: `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`


### Passos para lidar com o conflito da &quot;reescrita fmdita&quot;

O Experience Manager Guides inclui um módulo de reescrita Sling personalizado (`fmditarewriter`) para manipular links gerados para links entre mapas.

Se você tiver outra reescrita personalizada do Sling em sua base de código:

- Use um `order` valor **maior que 50** porque Guides usa `order=50`.
- Durante essa atualização, o valor de `order` muda de `1000` para `50`, portanto, você deve mesclar seu reescritor personalizado existente (se houver) com `fmditarewriter`.

