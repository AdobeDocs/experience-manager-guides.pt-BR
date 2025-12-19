---
title: Atualizar o Adobe Experience Manager Guides
description: Saiba como atualizar o Adobe Experience Manager Guides
exl-id: f058b39f-7408-4874-942b-693e133886cf
feature: Installation
role: Admin
level: Experienced
source-git-commit: 7ecf29537ddfbfcff644c4f6e3dff32750868282
workflow-type: tm+mt
source-wordcount: '9155'
ht-degree: 0%

---

# Atualizar o Adobe Experience Manager Guides {#id224MBE0M0XA}

>[!NOTE]
>
> Siga as instruções de atualização específicas para a versão licenciada do seu produto.

Você pode atualizar sua versão atual do Experience Manager Guides para a versão 5.1.0 Service Pack 3:

- Se você estiver usando a versão 5.1.0 ou 5.1.x, é possível atualizar diretamente para a versão 5.1.0 Service Pack 3.
- Se você estiver usando a versão 4.6.0, 4.6.x, 5.0.0 ou 5.0.x, será necessário atualizar para a versão 5.1.0.
- Se você estiver usando a versão 4.6.3, 4.6.1, 4.6 ou 4.4, será necessário atualizar para a versão 5.0.0.
- Se você estiver usando a versão 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 ou 4.1.x, será necessário atualizar para a versão 4.4 antes de atualizar para a versão 5.0.0.
- Se você estiver usando a versão 4.0, será necessário atualizar para a versão 4.2 antes de atualizar para a versão 4.3.x.
- Se você estiver usando a versão 3.8.5, será necessário atualizar para a versão 4.0 antes de atualizar para a versão 4.2.
- Se você estiver usando uma versão anterior à 3.8.5, consulte a seção Atualizar Experience Manager Guides no guia de instalação específico do produto, disponível no [arquivo PDF de ajuda do Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).


>[!NOTE]
>
> Você deve instalar o service pack do AEM antes de atualizar a versão do Experience Manager Guides.

Para obter mais detalhes, consulte os seguintes procedimentos:

- [Atualizar para a versão 5.1.0](#upgrade-to-version-510)
- [Atualizar para a versão 5.0.0](#upgrade-to-version-500)
- [Atualizar para a versão 4.6.0](#upgrade-to-version-460)
- [Atualizar para a versão 4.4.0](#upgrade-to-version-440)
- [Atualizar para a versão 4.3.1.5](#upgrade-to-version-4315)
- [Atualizar para a versão 4.3.1](#upgrade-to-version-431)
- [Atualizar para a versão 4.3.0](#upgrade-to-version-430)
- [Atualizar para a versão 4.2.1](#upgrade-to-version-421)
- [Atualizar para a versão 4.2](#upgrade-to-version-42)
- [Atualização da versão 3.8.5 para a versão 4.0](#upgrade-from-version-385-to-version-40)


>[!IMPORTANT]
>
> Antes de começar a atualização, faça um backup completo do sistema para evitar perda de dados.

## Atualização da versão 3.8.5 para a versão 4.0

Se estiver usando o Experience Manager Guides versão 3.8.5, você pode atualizar para a versão 4.0 do Experience Manager Guides. Com o recurso de atualização, não é necessário desinstalar a versão anterior do Experience Manager Guides.

Antes de executar o processo, há determinadas tarefas que você deve concluir. As subseções a seguir o guiarão pelos pré-requisitos, pela geração de relatórios e pelo processo de migração. Além disso, após instalar a versão 4.0 do Experience Manager Guides, você poderá personalizar várias configurações, de acordo com as configurações do cliente.

>[!NOTE]
>
> Este processo de atualização é aplicável somente da versão 3.8.5 para a versão 4.0. Para o processo de atualização da versão 3.4 ou superior para a 3.8.5, consulte a seção *Atualizar Experience Manager Guides* no guia de instalação específico do produto, disponível em [arquivo PDF de ajuda do Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).



**&#x200B;**&#x200B;Pré-requisitos&#x200B;**&#x200B;**

Antes de iniciar o processo de atualização do Experience Manager Guides, verifique se você tem:

1. Foram importados os comentários de revisão em tópicos abertos para revisão.
1. Todas as análises ativas foram fechadas.
1. Todas as tarefas de tradução foram fechadas.
1. Desinstale todos os hotfixes do Experience Manager Guides instalados na parte superior da versão anterior do Experience Manager Guides (versão principal ou patch).

**Antes de instalar a versão 4.0**

Antes de instalar a versão 4.0, execute as seguintes etapas:

1. Verifique se, neste momento, o Experience Manager Guides está na versão 3.8.5.
1. Baixe o pacote de script de atualização. Para fazer isso, pesquise por &quot;Pacote de Atualização da Solução XML Documentation 4.0&quot; no [Portal de Distribuição de Software Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html), que baixará um arquivo zip.
1. Faça upload deste pacote para o AEM por meio do Gerenciador de pacotes e instale este pacote.
1. Quando o pacote de atualização estiver instalado, execute os scripts abaixo na mesma ordem e siga as instruções fornecidas:

**Verificar API de compatibilidade de atualização**

Essa API foi projetada para avaliar o status atual do sistema e relatar se a atualização é possível ou não. Para executar esse script, acione o endpoint fornecido abaixo:

| Ponto final | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Tipo de solicitação | **GET** Você pode usar um navegador da Web, no qual você tenha feito logon na instância do AEM como administrador. |
| Resposta esperada | -   Caso todos os nós necessários possam ser movidos, você receberá uma verificação aprovada. <br>-   Caso um nó esteja presente no local de destino, você receberá um erro relevante. Limpe o repositório \(delete node /var/dxml\) e reinstale o pacote de atualização e acione esse endpoint novamente. <br>**Observação:** não é um erro comum, pois o local de destino não foi usado anteriormente pelo Experience Manager Guides 3.x. <br> -   Se o script não for bem-sucedido, não continue e relate à equipe de sucesso do cliente. |

**API de migração de dados do sistema**

Esta API foi projetada para migrar os dados do sistema conforme mencionado na seção **Mapeamento de Migração**.

1. Não execute este script se a API de verificação de compatibilidade de atualização falhar \(não continuar\).
1. Depois que a API Verificar compatibilidade de atualização retornar sucesso, você poderá executar o script de atualização.

| Ponto final | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Tipo de solicitação | **POST** Este script é uma solicitação POST, portanto, deve ser executado por agentes como o Postman. |
| Resposta esperada | -   Depois que a migração for bem-sucedida, você poderá instalar a solução XML Documentation versão 4.0.<br>-   Caso haja erros, restaure para o último ponto de verificação e compartilhe os logs de erro junto com a saída da API com a equipe de sucesso do cliente. |

**Mapeamento de Migração**: a API acima migra todos os dados do local de origem para o local de destino.

| Origem | Destino |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Instalar versão 4.0 {#id23598G006XA}

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

A atualização para a versão 4.2 depende da versão atual do Experience Manager Guides.

Se você estiver usando a versão 4.0, 4.1 ou 4.1.x, é possível atualizar diretamente para a versão 4.2.

**&#x200B;**&#x200B;Pré-requisitos&#x200B;**&#x200B;**

Antes de iniciar o processo de atualização do Experience Manager Guides 4.2, verifique se você tem:

1. Atualizado para a versão 4.0, 4.1 ou 4.1.x do Experience Manager Guides.
1. Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log.`

>[!NOTE]
>
> Você deve fechar todas as revisões ativas. Se as tarefas de revisão não forem fechadas durante a atualização para a versão 4.2, as tarefas de revisão em andamento mais antigas continuarão levando os usuários para as páginas de revisão mais antigas, e as tarefas de revisão criadas após a atualização exibirão as atualizações mais recentes na funcionalidade.

## Instalar versão 4.2 {#id2245IK0E0EV}

1. Baixe o pacote da versão 4.2 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote da versão 4.2.
1. Após concluir a instalação do pacote, aguarde a seguinte mensagem\(s\) nos logs:

   `Completed the post deployment setup script`

   A mensagem acima indica que todas as etapas da instalação foram concluídas.

   Caso encontre qualquer um dos seguintes prefixos de ERRO, relate-os à equipe de sucesso do cliente:

   - Erro no script de configuração pós-implantação
   - Exceção ao portar o MAP de tradução
   - Não é possível portar o mapa de conversão de v1 para v2 para a propriedade
1. Atualização do plugin do conector Oxygen lançado com a versão 4.2 \(se necessário\).
1. Limpe o cache do navegador após instalar o pacote.
1. Continue atualizando as personalizações conforme detalhado na próxima seção.

## Depois de instalar a versão 4.2 {#id2326F02004K}

>[!IMPORTANT]
>
> O modelo de alta tecnologia não é exibido no servidor atualizado. Para incluir o modelo de alta tecnologia em seu servidor, você pode copiá-lo: Source: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

Depois de instalar o Experience Manager Guides, você pode mesclar as várias configurações aplicáveis da versão recém-instalada à configuração.

>[!NOTE]
>
> O modelo dam-update-asset pode ser personalizado. Se alguma personalização foi feita, precisamos sincronizar as personalizações e o Experience Manager Guides na cópia de trabalho do modelo.

1. **Fluxo de trabalho do Ativo de atualização do DAM \(Alterações pós-processamento\):**

1. Abrir URL:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Selecione **Fluxo de trabalho do Ativo de atualização do DAM**.
1. Clique em **Editar**.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver presente, verifique se as personalizações estão sincronizadas.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver ausente, execute as seguintes etapas para inseri-lo:

1. Clique em **Inserir componente** \(Responsável pelo pós-processamento do Experience Manager Guides como a etapa final do processo\).
1. Configure a **Etapa do processo** com os detalhes abaixo:

   **Guia comum**

   **Título:** Iniciador de Pós-Processamento DXML

   **Descrição**: etapa do iniciador do pós-processamento DXML que acionará um trabalho de sling para pós-processamento DXML do ativo modificado/criado

   **Guia Processo**

   - Selecione o **Iniciador de Pós-Processamento de DXML** no menu suspenso **Processo**

   - Selecionar **Avanço do manipulador**

   - Selecionar **Concluído**

1. Clique em **Sincronizar** na parte superior direita depois de concluir as alterações. Você receberá uma notificação de sucesso.

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
   - Iniciador de &quot;*Nó Modificado*&quot; para **Fluxo de trabalho do Ativo de Atualização do DAM -** para a condição &quot;`jcr:content/jcr:mimeType!=video`&quot;,
   - o valor de &#39;Globbing&#39; deve ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; deve ter `"event-user-data:changedByWorkflowProcess"`.
1. Quando a atualização for concluída, verifique se todas as personalizações/sobreposições estão validadas e atualizadas para corresponder ao novo código do aplicativo. Alguns exemplos são apresentados abaixo:
   - Quaisquer componentes sobrepostos de/libs/fmditaor/libsdevem ser comparados com o novo código do produto e as atualizações devem ser feitas em arquivos sobrepostos em/apps.
   - Todas as categorias de clientlib usadas do produto devem ser revisadas para alterações. Todas as configurações substituídas \(exemplos abaixo\) devem ser comparadas com as mais recentes para obter os recursos mais recentes:
   - elementmapping.xml
   - ui\_config.json\(pode ter sido definido em perfis de pasta\)
   - emendado `com.adobe.fmdita.config.ConfigManager`
   - Verifique se qualquer um dos códigos personalizados estava usando caminhos antigos \(como mencionado na seção [Mapeamento de migração](#id2244LE040XA)\) - deve ser atualizado para os novos caminhos para que as personalizações também funcionem conforme esperado.
1. Leia sobre as novas configurações trazidas na versão atual \(verifique as [Notas de versão](../release-info/release-notes-4-3.md)\) e veja se alguma funcionalidade foi afetada, em seguida, tome as medidas apropriadas. Um exemplo pode ser o uso da seção &quot;Manuseio aprimorado de arquivos e versões&quot;, introduzida na versão 4.0, para a qual é necessário ativar uma configuração.

## Etapas para indexar o conteúdo existente para usar a nova localização e substituição:

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa:

- Execute uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados \|\| Por exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com a ID do trabalho para o mesmo ponto de extremidade -

`http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

Se o trabalho de atualização falhar e o log de erros mostrar o seguinte erro:

&quot;A *consulta* leu ou percorreu mais de *100000 nós*. Para não afetar outras tarefas, o processamento foi interrompido.&quot;

Isso pode ocorrer porque o índice não está configurado corretamente para a consulta usada na atualização. Você pode tentar a seguinte solução alternativa:

1. No índice damAssetLucene oak, adicione a propriedade booleana `indexNodeName` como `true` no nó.
   `/oak:index/damAssetLucene/indexRules/dam:Asset`
1. Adicione um novo nó com o trecho de nome sob o nó.

   `/oak:index/damAssetLucene/indexRules/dam:Asset/properties`
e defina as seguintes propriedades no nó:

   ```
   name - rep:excerpt
   propertyIndex - {Boolean}true
   notNullCheckEnabled - {Boolean}true
   ```

   A estrutura de `damAssetLucene` deve ser parecida com:

   ```
   <damAssetLucene compatVersion="{Long}2" async="async, nrt" jcr:primaryType="oak:QueryIndexDefinition" evaluatePathRestrictions="{Boolean}true" type="lucene">
   <indexRules jcr:primaryType="nt:unstructured">
     <dam:Asset indexNodeName="{Boolean}true" jcr:primaryType="nt:unstructured">
       <properties jcr:primaryType="nt:unstructured">
         <excerpt name="rep:excerpt" propertyIndex="{Boolean}true" jcr:primaryType="nt:unstructured" notNullCheckEnabled="{Boolean}true"/>
       </properties>
       </dam:Asset>
     </indexRules>
   </damAssetLucene>    
   ```


   (juntamente com outros nós e propriedades existentes)

1. Reindexe o índice `damAssetLucene` (definindo o sinalizador de reindexação como `true` em
e aguarde até que ele seja `false` novamente (isso indica que a reindexação foi concluída). Observe que pode levar algumas horas, dependendo do tamanho do índice.
1. Execute o script de indexação novamente executando as etapas anteriores.


## Atualizar para a versão 4.2.1

>[!TIP]
>
>É recomendável instalar o Hotfix 4.2.1.3 sobre a versão 4.2.1.

A atualização para a versão 4.2.1 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 4.1, 4.1.x ou 4.2, é possível atualizar diretamente para a versão 4.2.1.

>[!NOTE]
>
>O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

**&#x200B;**&#x200B;Pré-requisitos&#x200B;**&#x200B;**

Antes de iniciar o processo de atualização do Experience Manager Guides 4.2.1, verifique se você tem:

1. Atualizado para a versão 4.1, 4.1.x ou 4.2 do Experience Manager Guides.
1. Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log.`

>[!NOTE]
>
> Você deve fechar todas as revisões ativas. Se as tarefas de revisão não forem fechadas durante a atualização para a versão 4.2, as tarefas de revisão em andamento mais antigas continuarão levando os usuários para as páginas de revisão mais antigas, e as tarefas de revisão criadas após a atualização exibirão as atualizações mais recentes na funcionalidade.

## Instalar versão 4.2.1

1. Baixe o pacote de versão 4.2.1 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote da versão 4.2.1.
1. Você pode optar por ACESSAR o acionador para iniciar o trabalho de atualização do mapa de tradução. Para obter detalhes, consulte [Habilitar gatilho de script por meio de um Servlet](#enable-trigger-of-script-via-a-servlet-for-421).


1. Após concluir a instalação do pacote, aguarde a seguinte mensagem\(s\) nos logs:

   `Completed the post deployment setup script`

   A mensagem acima indica que todas as etapas da instalação foram concluídas.

   Caso encontre qualquer um dos seguintes prefixos de ERRO, relate-os à equipe de sucesso do cliente:

   - Erro no script de configuração pós-implantação
   - Exceção ao portar o MAP de tradução
   - Não é possível portar o mapa de conversão de v1 para v2 para a propriedade
1. Atualização do plugin do conector Oxygen lançado com a versão 4.2 \(se necessário\).
1. Limpe o cache do navegador após instalar o pacote.
1. Continue atualizando as personalizações conforme detalhado na próxima seção.

### Ativar acionador de script por meio de um Servlet (para 4.2.1)

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

Exemplo de log:
Este é um exemplo de logs que aparecerão no arquivo de log depois que você acionar o script.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Procure por `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` e `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` antes de prosseguir para as próximas etapas.



## Depois de instalar a versão 4.2.1

>[!IMPORTANT]
>
> O modelo de alta tecnologia não é exibido no servidor atualizado. Para incluir o modelo de alta tecnologia em seu servidor, você pode copiá-lo: Source: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

Depois de instalar o Experience Manager Guides, você pode mesclar as várias configurações aplicáveis da versão recém-instalada à configuração.

>[!NOTE]
>
> O modelo dam-update-asset pode ser personalizado. Se alguma personalização foi feita, precisamos sincronizar as personalizações e o Experience Manager Guides na cópia de trabalho do modelo.

1. **Fluxo de trabalho do Ativo de atualização do DAM \(Alterações pós-processamento\):**

1. Abrir URL:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Selecione **Fluxo de trabalho do Ativo de atualização do DAM**.
1. Clique em **Editar**.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver presente, verifique se as personalizações estão sincronizadas.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver ausente, execute as seguintes etapas para inseri-lo:

1. Clique em **Inserir componente** \(Responsável pelo pós-processamento do Experience Manager Guides como a etapa final do processo\).
1. Configure a **Etapa do processo** com os detalhes abaixo:

   **Guia comum**

   **Título:** Iniciador de Pós-Processamento DXML

   **Descrição**: etapa do iniciador do pós-processamento DXML que acionará um trabalho de sling para pós-processamento DXML do ativo modificado/criado

   **Guia Processo**

   - Selecione o **Iniciador de Pós-Processamento de DXML** no menu suspenso **Processo**

   - Selecionar **Avanço do manipulador**

   - Selecionar **Concluído**

1. Clique em **Sincronizar** na parte superior direita depois de concluir as alterações. Você receberá uma notificação de sucesso.

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
   - Quaisquer componentes sobrepostos de/libs/fmditaor/libsdevem ser comparados com o novo código do produto e as atualizações devem ser feitas em arquivos sobrepostos em/apps.
   - Todas as categorias de clientlib usadas do produto devem ser revisadas para alterações. Todas as configurações substituídas \(exemplos abaixo\) devem ser comparadas com as mais recentes para obter os recursos mais recentes:
   - elementmapping.xml
   - ui\_config.json\(pode ter sido definido em perfis de pasta\)
   - emendado `com.adobe.fmdita.config.ConfigManager`
   - Verifique se qualquer um dos códigos personalizados estava usando caminhos antigos \(como mencionado na seção [Mapeamento de migração](#id2244LE040XA)\) - deve ser atualizado para os novos caminhos para que as personalizações também funcionem conforme esperado.
1. Leia sobre as novas configurações trazidas na versão atual \(verifique as [Notas de versão](../release-info/release-notes-4-2-1.md)\) e veja se alguma funcionalidade foi afetada, em seguida, tome as medidas apropriadas. Um exemplo pode ser o uso da seção &quot;Manuseio aprimorado de arquivos e versões&quot;, introduzida na versão 4.0, para a qual é necessário ativar uma configuração.

## Etapas para indexar o conteúdo existente para usar a nova localização e substituição:

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa:

- Verifique se a indexação `damAssetLucene` foi concluída. Pode levar algumas horas, dependendo da quantidade de dados presentes no servidor. Você pode confirmar que a reindexação foi concluída verificando se o campo de reindexação está definido como falso em
  `http://<server:port>/oak:index/damAssetLucene`.  Além disso, se você tiver adicionado personalizações em `damAssetLucene`, talvez seja necessário aplicá-las novamente.

- Execute uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados \|\| Por exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Você também pode passar uma pasta raiz para indexar os mapas DITA de uma pasta específica (e suas subpastas). Por exemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observe que se os parâmetros de caminhos e de raiz forem transmitidos, somente o parâmetro de caminhos será considerado.

- A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com ID do trabalho para o mesmo ponto de extremidade - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.


## Atualizar para a versão 4.3.0

A atualização para a versão 4.3.0 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 4.2 ou 4.2.x, é possível atualizar diretamente para a versão 4.3.0.

>[!NOTE]
>
>O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

**&#x200B;**&#x200B;Pré-requisitos&#x200B;**&#x200B;**

Antes de iniciar o processo de atualização do Experience Manager Guides 4.3.0, verifique se você tem:

1. Atualização para o Experience Manager Guides versão 4.2 ou 4.2.x e conclusão das respectivas etapas de instalação.
1. Todas as tarefas de tradução foram fechadas.



## Instalar a versão 4.3.0

1. Baixe o pacote da versão 4.3.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote da versão 4.3.0.
1. Limpe o cache do navegador após instalar o pacote.
1. Atualize o arquivo `ui_config.json` da guia **Configuração do Editor XML** no Perfil de Pasta.


## Depois de instalar a versão 4.3.0

Depois de instalar o Experience Manager Guides, você pode mesclar as várias configurações aplicáveis da versão recém-instalada à configuração.

## Etapas para pós-processar o conteúdo existente para usar o relatório de link corrompido


Execute as seguintes etapas para o pós-processamento do conteúdo existente e uso do novo relatório de link desfeito:

1. (Opcional) Se houver mais de 100.000 arquivos dita no sistema, atualize o `queryLimitReads` em `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` para um valor maior (qualquer valor maior que o número de ativos presentes, por exemplo, 200.000) e reimplante.

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



## Atualizar para a versão 4.3.1

A atualização para a versão 4.3.1 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 4.3.0, 4.2 ou 4.2.1, é possível atualizar diretamente para a versão 4.3.1.

>[!NOTE]
>
>O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

**&#x200B;**&#x200B;Pré-requisitos&#x200B;**&#x200B;**

Antes de iniciar o processo de atualização do Experience Manager Guides 4.3.1, verifique se você tem:

1. Atualização para o Experience Manager Guides versão 4.3.0, 4.2 ou 4.2.1 e conclusão das respectivas etapas de instalação.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.


## Instalar a versão 4.3.1

1. Baixe o pacote de versão 4.3.1 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote da versão 4.3.1.
1. Você pode optar por ACESSAR o acionador para iniciar o trabalho de atualização do mapa de tradução. Para obter detalhes, consulte [Habilitar gatilho de script por meio de um Servlet](#enable-trigger-of-script-via-a-servlet-for-431).


1. Após concluir a instalação do pacote, aguarde a seguinte mensagem\(s\) nos logs:

   `Completed the post deployment setup script`

   A mensagem acima indica que todas as etapas da instalação foram concluídas.

   Caso encontre qualquer um dos seguintes prefixos de ERRO, relate-os à equipe de sucesso do cliente:

   - Erro no script de configuração pós-implantação
   - Exceção ao portar o MAP de tradução
   - Não é possível portar o mapa de conversão de v1 para v2 para a propriedade
1. Atualização do plugin do conector Oxygen lançado com a versão 4.2 \(se necessário\).
1. Limpe o cache do navegador após instalar o pacote.
1. Continue atualizando as personalizações conforme detalhado na próxima seção.

### Ativar acionador de script por meio de um Servlet (para 4.3.1)

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

Exemplo de log:
Este é um exemplo de logs que aparecerão no arquivo de log depois que você acionar o script.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Procure por `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` e `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` antes de prosseguir para as próximas etapas.

## Depois de instalar a versão 4.3.1



Depois de instalar o Experience Manager Guides, você pode mesclar as várias configurações aplicáveis da versão recém-instalada à configuração.

>[!NOTE]
>
> O modelo dam-update-asset pode ser personalizado. Se alguma personalização foi feita, precisamos sincronizar as personalizações e o Experience Manager Guides na cópia de trabalho do modelo.

1. **Fluxo de trabalho do Ativo de atualização do DAM \(Alterações pós-processamento\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Selecione **Fluxo de trabalho do Ativo de atualização do DAM**.
1. Clique em **Editar**.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver presente, verifique se as personalizações estão sincronizadas.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver ausente, execute as seguintes etapas para inseri-lo:

1. Clique em **Inserir componente** \(Responsável pelo pós-processamento do Experience Manager Guides como a etapa final do processo\).
1. Configure a **Etapa do processo** com os detalhes abaixo:

   **Guia comum**

   **Título:** Iniciador de Pós-Processamento DXML

   **Descrição**: etapa do iniciador do pós-processamento DXML que acionará um trabalho de sling para pós-processamento DXML do ativo modificado/criado

   **Guia Processo**

   - Selecione o **Iniciador de Pós-Processamento de DXML** no menu suspenso **Processo**

   - Selecionar **Avanço do manipulador**

   - Selecionar **Concluído**

1. Clique em **Sincronizar** na parte superior direita depois de concluir as alterações. Você receberá uma notificação de sucesso.

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
   - Quaisquer componentes sobrepostos de/libs/fmditaor/libsdevem ser comparados com o novo código do produto e as atualizações devem ser feitas em arquivos sobrepostos em/apps.
   - Todas as categorias de clientlib usadas do produto devem ser revisadas para alterações. Todas as configurações substituídas \(exemplos abaixo\) devem ser comparadas com as mais recentes para obter os recursos mais recentes:
   - elementmapping.xml
   - ui\_config.json\(pode ter sido definido em perfis de pasta\)
   - emendado `com.adobe.fmdita.config.ConfigManager`


## Etapas para indexar o conteúdo existente

>[!NOTE]
>
> Não é necessário executar essas etapas se você atualizar do 4.3.0 ou 4.2.1.

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa:


- Execute uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados \|\| Por exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


- A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com ID do trabalho para o mesmo ponto de extremidade - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Etapas para pós-processar o conteúdo existente para usar o relatório de link corrompido

>[!NOTE]
>
> Não é necessário executar essas etapas se você atualizar do 4.3.0

Execute as seguintes etapas para o pós-processamento do conteúdo existente e uso do novo relatório de link desfeito:

1. (Opcional) Se houver mais de 100.000 arquivos dita no sistema, atualize o `queryLimitReads` em `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` para um valor maior (qualquer valor maior que o número de ativos presentes, por exemplo, 200.000) e reimplante.

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



## Atualizar para a versão 4.3.1.5

A atualização para a versão 4.3.1.5 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 4.3.1, será possível atualizar diretamente para a versão 4.3.1.5.



## Instalar versão 4.3.1.5

1. Baixe o pacote de versão 4.3.1.5 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instalar pacote da versão 4.3.1.5.

1. Aguarde até que o processo de instalação seja concluído com êxito.
1. Continue atualizando as personalizações conforme detalhado na próxima seção.


## Depois de instalar a versão 4.3.1.5


>[!NOTE]
>
>Se quiser usar o pacote org.apache.velocity, execute as seguintes etapas antes de fazer upload do pacote:
> 1. Acesse `<server>:<port>/system/console/bundles`.
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

A atualização para a versão 4.4.0 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 4.3.1, 4.3.0, 4.2 ou 4.2.1 (Hotfix 4.2.1.3), é possível atualizar diretamente para a versão 4.4.0

>[!NOTE]
>
>O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

**&#x200B;**&#x200B;Pré-requisitos&#x200B;**&#x200B;**

Antes de iniciar o processo de atualização do Experience Manager Guides 4.4.0, verifique se você tem:

1. Atualizado para o Experience Manager Guides versão 4.3.1, 4.3.0 ou 4.2.1 (Hotfix 4.2.1.3) e concluído sua respectiva etapa de instalação.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.


## Instalar a versão 4.4.0

1. Baixe o pacote da versão 4.4.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote da versão 4.4.0.
1. Você pode optar por ACESSAR o acionador para iniciar o trabalho de atualização do mapa de tradução. Para obter detalhes, consulte [Habilitar gatilho de script por meio de um Servlet](#enable-trigger-of-script-via-a-servlet).

1. Após concluir a instalação do pacote, aguarde a seguinte mensagem\(s\) nos logs:

   `Completed the post deployment setup script`

   A mensagem acima indica que todas as etapas da instalação foram concluídas.

   Caso encontre qualquer um dos seguintes prefixos de ERRO, relate-os à equipe de sucesso do cliente:

   - Erro no script de configuração pós-implantação
   - Exceção ao portar o MAP de tradução
   - Não é possível portar o mapa de conversão de v1 para v2 para a propriedade
1. Atualização do plugin do conector Oxygen lançado com a versão 4.4.0 \(se necessário\).
1. Limpe o cache do navegador após instalar o pacote.
1. Continue atualizando as personalizações conforme detalhado na próxima seção.


## Depois de instalar a versão 4.4.0

Depois de instalar o Experience Manager Guides, você pode mesclar as várias configurações aplicáveis da versão recém-instalada à configuração.

>[!NOTE]
>
> O modelo dam-update-asset pode ser personalizado. Se alguma personalização foi feita, precisamos sincronizar as personalizações e o Experience Manager Guides na cópia de trabalho do modelo.

1. **Fluxo de trabalho do Ativo de atualização do DAM \(Alterações pós-processamento\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Selecione **Fluxo de trabalho do Ativo de atualização do DAM**.
1. Clique em **Editar**.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver presente, verifique se as personalizações estão sincronizadas.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver ausente, execute as seguintes etapas para inseri-lo:

1. Clique em **Inserir componente** \(Responsável pelo pós-processamento do Experience Manager Guides como a etapa final do processo\).
1. Configure a **Etapa do processo** com os detalhes abaixo:

   **Guia comum**

   **Título:** Iniciador de Pós-Processamento DXML

   **Descrição**: etapa do iniciador do pós-processamento DXML que acionará um trabalho de sling para pós-processamento DXML do ativo modificado/criado

   **Guia Processo**

   - Selecione o **Iniciador de Pós-Processamento de DXML** no menu suspenso **Processo**

   - Selecionar **Avanço do manipulador**

   - Selecionar **Concluído**

1. Clique em **Sincronizar** na parte superior direita depois de concluir as alterações. Você receberá uma notificação de sucesso.

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
   - Quaisquer componentes sobrepostos de/libs/fmditaor/libsdevem ser comparados com o novo código do produto e as atualizações devem ser feitas em arquivos sobrepostos em/apps.
   - Todas as categorias de clientlib usadas do produto devem ser revisadas para alterações. Todas as configurações substituídas \(exemplos abaixo\) devem ser comparadas com as mais recentes para obter os recursos mais recentes:
   - elementmapping.xml
   - ui\_config.json\(pode ter sido definido em perfis de pasta\)
   - emendado `com.adobe.fmdita.config.ConfigManager`

1. Se você tiver adicionado personalizações em damAssetLucene, talvez seja necessário aplicá-las novamente. Depois de fazer essas alterações, defina reindex como true. Isso reindexará todos os nós existentes com as personalizações. Depois de concluído, o sinalizador de reindexação será definido como falso novamente. Isso pode levar algumas horas, dependendo do número de ativos no sistema.

## Etapas para indexar o conteúdo existente

>[!NOTE]
>
> Não é necessário executar essas etapas se você atualizar do 4.3.0 ou 4.3.1.

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa:

- Execute uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados \|\| Por exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com ID do trabalho para o mesmo ponto de extremidade - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por exemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Etapas para pós-processar o conteúdo existente para usar o relatório de link corrompido

>[!NOTE]
>
> Não é necessário executar essas etapas se você atualizar do 4.3.0 ou 4.3.1.

Execute as seguintes etapas para o pós-processamento do conteúdo existente e uso do novo relatório de link desfeito:

1. (Opcional) Se houver mais de 100.000 arquivos dita no sistema, atualize o `queryLimitReads` em `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` para um valor maior (qualquer valor maior que o número de ativos presentes, por exemplo, 200.000) e reimplante.

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

### Ativar acionador de script por meio de um Servlet

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



## Etapas para lidar com o conflito `'fmdita rewriter'`

O Experience Manager Guides tem um módulo [**personalizado de reescrita do sling**](../cs-install-guide/conf-output-generation.md#custom-rewriter) para manipular os links gerados no caso de mapas cruzados (links entre os tópicos de dois mapas diferentes).

Se você tiver outro reescritor sling personalizado em sua base de código, use um valor de `'order'` maior que 50, pois o reescritor Experience Manager Guides sling usa `'order'` 50.  Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de regravação de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta atualização, como o valor de `'order'` é alterado de 1000 para 50, você precisa mesclar o reescritor personalizado existente, se houver, com `'fmdita-rewriter'`.


**Tópico pai:**&#x200B;[&#x200B; Baixar e instalar](download-install.md)


## Atualizar para a versão 4.6.0

>[!TIP]
>
> É recomendável instalar o 4.6.0 Service Pack 4 sobre o versão 4.6.0, 4.6.0 Service Pack 1 ou 4.6.0 Service Pack 3. O processo de atualização do Service Pack 4.6.0 segue as mesmas etapas do release 4.6.0.

A atualização para a versão 4.6.0 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 4.4.0, 4.3.1, 4.3.0, 4.2 ou 4.2.1 (Hotfix 4.2.1.3), será possível atualizar diretamente para a versão 4.6.0.

>[!NOTE]
>
> O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

**&#x200B;**&#x200B;Pré-requisitos&#x200B;**&#x200B;**

Antes de iniciar o processo de atualização do Experience Manager Guides 4.6.0, verifique se você tem:

1. Atualizado para o Experience Manager Guides versão 4.3.1, 4.3.0 ou 4.2.1 (Hotfix 4.2.1.3) e concluído sua respectiva etapa de instalação.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.


## Instalar a versão 4.6.0

1. Baixe o pacote da versão 4.6.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote da versão 4.6.0.
1. Você pode optar por ACESSAR o acionador para iniciar o trabalho de atualização do mapa de tradução. Para obter detalhes, consulte [Habilitar gatilho de script por meio de um Servlet](#enable-trigger-of-script-via-a-servlet).

1. Após concluir a instalação do pacote, aguarde a seguinte mensagem\(s\) nos logs:

   `Completed the post deployment setup script`

   A mensagem acima indica que todas as etapas da instalação foram concluídas.

   Caso encontre qualquer um dos seguintes prefixos de ERRO, relate-os à equipe de sucesso do cliente:

   - Erro no script de configuração pós-implantação
   - Exceção ao portar o MAP de tradução
   - Não é possível portar o mapa de conversão de v1 para v2 para a propriedade
1. Atualização do plugin do conector Oxygen lançado com a versão 4.6.0 \(se necessário\).
1. Limpe o cache do navegador após instalar o pacote.

## Depois de instalar a versão 4.6.0

Depois de instalar o Experience Manager Guides, você pode mesclar as várias configurações aplicáveis da versão recém-instalada à configuração.

>[!NOTE]
>
> O modelo dam-update-asset pode ser personalizado. Se alguma personalização foi feita, precisamos sincronizar as personalizações e o Experience Manager Guides na cópia de trabalho do modelo.

1. **Fluxo de trabalho do Ativo de atualização do DAM \(Alterações pós-processamento\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Selecione **Fluxo de trabalho do Ativo de atualização do DAM**.
1. Clique em **Editar**.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver presente, verifique se as personalizações estão sincronizadas.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver ausente, execute as seguintes etapas para inseri-lo:

1. Clique em **Inserir componente** \(Responsável pelo pós-processamento do Experience Manager Guides como a etapa final do processo\).
1. Configure a **Etapa do processo** com os detalhes abaixo:

   **Guia comum**

   **Título:** Iniciador de Pós-Processamento DXML

   **Descrição**: etapa do iniciador do pós-processamento DXML que acionará um trabalho de sling para pós-processamento DXML do ativo modificado/criado

   **Guia Processo**

   - Selecione o **Iniciador de Pós-Processamento de DXML** na lista suspensa **Processo**

   - Selecionar **Avanço do manipulador**

   - Selecionar **Concluído**

1. Clique em **Sincronizar** na parte superior direita depois de concluir as alterações. Você receberá uma notificação de sucesso.

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
   - Quaisquer componentes sobrepostos de/libs/fmditaor/libsdevem ser comparados com o novo código do produto e as atualizações devem ser feitas em arquivos sobrepostos em/apps.
   - Todas as categorias de clientlib usadas do produto devem ser revisadas para alterações. Todas as configurações substituídas \(exemplos abaixo\) devem ser comparadas com as mais recentes para obter os recursos mais recentes:
   - elementmapping.xml
   - ui\_config.json\(pode ter sido definido em perfis de pasta\)
   - emendado `com.adobe.fmdita.config.ConfigManager`

1. Se você tiver adicionado personalizações em damAssetLucene, talvez seja necessário aplicá-las novamente. Depois de fazer essas alterações, defina reindex como true. Isso reindexará todos os nós existentes com as personalizações. Depois de concluído, o sinalizador de reindexação será definido como falso novamente. Isso pode levar algumas horas, dependendo do número de ativos no sistema.

## Etapas para reindexar os índices do Experience Manager Guides

1. Abra `crx/de` e navegue até o caminho do índice: `/oak:index/guidesAssetProperties`
2. Defina a propriedade de reindexação como `true` (`false` por padrão) e clique em **Salvar tudo**.
3. Quando a reindexação for concluída, a propriedade reindex será definida novamente como `false`, e a contagem de reindexação será incrementada em 1.

   >[!NOTE]
   >
   > Isso pode levar alguns minutos, dependendo da quantidade de dados presentes.
4. Siga as mesmas etapas para outros índices adicionados ou modificados: `guidesBulkActivation`, `guidesPeerLinkIndex` e `guidesKonnectTemplateIndex`.

## Etapas para indexar o conteúdo existente



Execute as seguintes etapas para indexar o conteúdo existente:

- Execute uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados || Exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com a ID do trabalho para o mesmo ponto de extremidade - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por exemplo: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.


>[!NOTE]
>
> Se você estiver usando o esquema personalizado, defina o caminho dos arquivos DTD e XSD catalog.xml personalizados no repositório do AEM na opção **Integrar catálogos**.




## Etapas para lidar com o conflito `'fmdita rewriter'`

O Experience Manager Guides tem um módulo [**personalizado de reescrita do sling**](../cs-install-guide/conf-output-generation.md#custom-rewriter) para manipular os links gerados no caso de mapas cruzados (links entre os tópicos de dois mapas diferentes).

Se você tiver outro reescritor sling personalizado em sua base de código, use um valor de `'order'` maior que 50, pois o reescritor Experience Manager Guides sling usa `'order'` 50.  Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de regravação de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta atualização, como o valor de `'order'` é alterado de 1000 para 50, você precisa mesclar o reescritor personalizado existente, se houver, com `'fmdita-rewriter'`.


## Atualizar para a versão 5.0.0

>[!TIP]
>
> A atualização para a versão 5.0.0 do Service Pack 2 depende da versão atual do Experience Manager Guides. Se você estiver usando a versão 5.0.0 Service Pack 1 ou 5.0.0, é possível atualizar diretamente para a versão 5.0.0 Service Pack 2.

>[!NOTE]
>
> O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

**&#x200B;**&#x200B;Pré-requisitos&#x200B;**&#x200B;**

Antes de iniciar o processo de atualização do Experience Manager Guides 5.0.0, verifique se você tem:

1. Atualizado para o Experience Manager Guides versão 4.6.3, 4.6.1, 4.6.0 ou 4.4 e concluído sua respectiva etapa de instalação.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.


## Instalar versão 5.0.0

1. Baixe o pacote da versão 5.0.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote da versão 5.0.0.
1. Você pode optar por ACESSAR o acionador para iniciar o trabalho de atualização do mapa de tradução. Para obter detalhes, consulte [Habilitar gatilho de script por meio de um Servlet](#enable-trigger-of-script-via-a-servlet).

1. Após concluir a instalação do pacote, aguarde a seguinte mensagem\(s\) nos logs:

   `Completed the post deployment setup script`

   A mensagem acima indica que todas as etapas da instalação foram concluídas.

   Caso encontre qualquer um dos seguintes prefixos de ERRO, relate-os à equipe de sucesso do cliente:

   - Erro no script de configuração pós-implantação
   - Exceção ao portar o MAP de tradução
   - Não é possível portar o mapa de conversão de v1 para v2 para a propriedade
1. Atualização do plug-in do conector Oxygen lançado com a versão 5.0.0 \(se necessário\).
1. Limpe o cache do navegador após instalar o pacote.

## Depois de instalar a versão 5.0.0

Depois de instalar o Experience Manager Guides, você pode mesclar as várias configurações aplicáveis da versão recém-instalada à configuração.

>[!NOTE]
>
> O modelo dam-update-asset pode ser personalizado. Se alguma personalização foi feita, precisamos sincronizar as personalizações e o Experience Manager Guides na cópia de trabalho do modelo.

1. **Fluxo de trabalho do Ativo de atualização do DAM \(Alterações pós-processamento\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Selecione **Fluxo de trabalho do Ativo de atualização do DAM**.
1. Clique em **Editar**.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver presente, verifique se as personalizações estão sincronizadas.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver ausente, execute as seguintes etapas para inseri-lo:

1. Clique em **Inserir componente** \(Responsável pelo pós-processamento do Experience Manager Guides como a etapa final do processo\).
1. Configure a **Etapa do processo** com os detalhes abaixo:

   **Guia comum**

   **Título:** Iniciador de Pós-Processamento DXML

   **Descrição**: etapa do iniciador do pós-processamento DXML que acionará um trabalho de sling para pós-processamento DXML do ativo modificado/criado

   **Guia Processo**

   - Selecione o **Iniciador de Pós-Processamento de DXML** na lista suspensa **Processo**

   - Selecionar **Avanço do manipulador**

   - Selecionar **Concluído**

1. Clique em **Sincronizar** na parte superior direita depois de concluir as alterações. Você receberá uma notificação de sucesso.

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
   - Quaisquer componentes sobrepostos de/libs/fmditaor/libsdevem ser comparados com o novo código do produto e as atualizações devem ser feitas em arquivos sobrepostos em/apps.
   - Todas as categorias de clientlib usadas do produto devem ser revisadas para alterações. Todas as configurações substituídas \(exemplos abaixo\) devem ser comparadas com as mais recentes para obter os recursos mais recentes:
   - elementmapping.xml
   - ui\_config.json\(pode ter sido definido em perfis de pasta\)
   - emendado `com.adobe.fmdita.config.ConfigManager`

1. Se você tiver adicionado personalizações em damAssetLucene, talvez seja necessário aplicá-las novamente. Depois de fazer essas alterações, defina reindex como true. Isso reindexará todos os nós existentes com as personalizações. Depois de concluído, o sinalizador de reindexação será definido como falso novamente. Isso pode levar algumas horas, dependendo do número de ativos no sistema.

## Etapas para reindexar os índices do Experience Manager Guides

1. Abra `crx/de` e navegue até o caminho do índice: `/oak:index/guidesAssetProperties`
2. Defina a propriedade de reindexação como `true` (`false` por padrão) e clique em **Salvar tudo**.
3. Quando a reindexação for concluída, a propriedade reindex será definida novamente como `false`, e a contagem de reindexação será incrementada em 1.

   >[!NOTE]
   >
   > Isso pode levar alguns minutos, dependendo da quantidade de dados presentes.
4. Siga as mesmas etapas para outros índices adicionados ou modificados: `guidesBulkActivation`, `guidesPeerLinkIndex` e `guidesKonnectTemplateIndex`.

## Etapas para indexar o conteúdo existente



Execute as seguintes etapas para indexar o conteúdo existente:

- Execute uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados || Exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com a ID do trabalho para o mesmo ponto de extremidade - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por exemplo: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.


>[!NOTE]
>
> Se você estiver usando o esquema personalizado, defina o caminho dos arquivos DTD e XSD catalog.xml personalizados no repositório do AEM na opção **Integrar catálogos**.




## Etapas para lidar com o conflito `'fmdita rewriter'`

O Experience Manager Guides tem um módulo [**personalizado de reescrita do sling**](../cs-install-guide/conf-output-generation.md#custom-rewriter) para manipular os links gerados no caso de mapas cruzados (links entre os tópicos de dois mapas diferentes).

Se você tiver outro reescritor sling personalizado em sua base de código, use um valor de `'order'` maior que 50, pois o reescritor Experience Manager Guides sling usa `'order'` 50.  Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de regravação de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta atualização, como o valor de `'order'` é alterado de 1000 para 50, você precisa mesclar o reescritor personalizado existente, se houver, com `'fmdita-rewriter'`.



## Etapas para reindexar o damAssetLucene

A definição do índice é atualizada para damAssetLucene com Guias. Consulte [este artigo](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) para reindexar o damAssetLucene depois de atualizar para a versão 5.0.0.

>[!NOTE]
>
> Ao seguir a documentação, verifique se ambas as propriedades (reindex=true e reindex-async=true para /oak:index/damAssetLucene) são atualizadas simultaneamente por meio da operação de salvamento.

## Atualizar para a versão 5.1.0

>[!IMPORTANT]
>
> Se você estiver usando o AEM 6.5 e planeja migrar para o AEM 6.5 LTS, conclua a atualização do AEM primeiro antes de prosseguir com a atualização do Experience Manager Guides 5.1.0. Para obter detalhes, consulte [Atualização para o Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

**Pré-requisitos**

>[!NOTE]
>
>Se estiver atualizando para o 5.1.0 Service Pack 3, você precisa estar na versão 5.1.0 ou 5.1.x do Experience Manager Guides.

Antes de iniciar o processo de atualização do Experience Manager Guides 5.1.0, verifique se você tem:

1. Atualizado para o Experience Manager Guides versão 4.6.3, 4.6.4, 5.0.0 ou 5.0.0 Service Pack 1 e concluído a respectiva etapa de instalação.
1. (Opcional) Todas as tarefas de tradução foram fechadas.
1. Alterado o nível de log para **INFO** para a classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e anexado esses logs em um novo arquivo de log, por exemplo, `logs/translation_upgrade.log`.

>[!NOTE]
>
> O pós-processamento e a indexação podem levar algumas horas. Recomendamos que você inicie o processo de atualização fora do horário de pico.

## Instalar versão 5.1.0

1. Baixe o pacote da versão 5.1.0 do [Portal de Distribuição de Software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/br/aem.html).
1. Instale o pacote da versão 5.1.0.
1. Você pode optar por ACESSAR o acionador para iniciar o trabalho de atualização do mapa de tradução. Para obter detalhes, consulte [Habilitar gatilho de script por meio de um Servlet](#enable-trigger-of-script-via-a-servlet).

1. Após concluir a instalação do pacote, aguarde a seguinte mensagem\(s\) nos logs:

   `Completed the post deployment setup script`

   A mensagem acima indica que todas as etapas da instalação foram concluídas.

   Caso encontre qualquer um dos seguintes prefixos de ERRO, relate-os à equipe de sucesso do cliente:

   - Erro no script de configuração pós-implantação
   - Exceção ao portar o MAP de tradução
   - Não é possível portar o mapa de conversão de v1 para v2 para a propriedade
1. Atualização do plugin do conector Oxygen lançado com a versão 5.1.0 \(se necessário\).
1. Limpe o cache do navegador após instalar o pacote.

## Depois de instalar a versão 5.1.0

Depois de instalar o Experience Manager Guides, você pode mesclar as várias configurações aplicáveis da versão recém-instalada à configuração.

>[!NOTE]
>
> O modelo dam-update-asset pode ser personalizado. Se alguma personalização foi feita, precisamos sincronizar as personalizações e o Experience Manager Guides na cópia de trabalho do modelo.

1. **Fluxo de trabalho do Ativo de atualização do DAM \(Alterações pós-processamento\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Selecione **Fluxo de trabalho do Ativo de atualização do DAM**.
1. Selecione **Editar**.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver presente, verifique se as personalizações estão sincronizadas.
1. Se o componente **Iniciador de Pós-Processamento DXML** estiver ausente, execute as seguintes etapas para inseri-lo:

1. Selecione **Inserir componente** \(Responsável pelo pós-processamento do Experience Manager Guides como a etapa final do processo\).
1. Configure a **Etapa do processo** com os detalhes abaixo:

   **Guia comum**

   **Título:** Iniciador de Pós-Processamento DXML

   **Descrição**: etapa do iniciador do pós-processamento DXML que acionará um trabalho de sling para pós-processamento DXML do ativo modificado/criado

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
   - Quaisquer componentes sobrepostos de/libs/fmditaor/libsdevem ser comparados com o novo código do produto e as atualizações devem ser feitas em arquivos sobrepostos em/apps.
   - Todas as categorias de clientlib usadas do produto devem ser revisadas para alterações. Todas as configurações substituídas \(exemplos abaixo\) devem ser comparadas com as mais recentes para obter os recursos mais recentes:
   - elementmapping.xml
   - ui\_config.json\(pode ter sido definido em perfis de pasta\)
   - emendado `com.adobe.fmdita.config.ConfigManager`

1. Se você tiver adicionado personalizações em damAssetLucene, talvez seja necessário aplicá-las novamente. Depois de fazer essas alterações, defina reindex como true. Isso reindexará todos os nós existentes com as personalizações. Depois de concluído, o sinalizador de reindexação será definido como falso novamente. Isso pode levar algumas horas, dependendo do número de ativos no sistema.

## Etapas para reindexar os índices do Experience Manager Guides

1. Abra `crx/de` e navegue até o caminho do índice: `/oak:index/guidesAssetProperties`
2. Defina a propriedade de reindexação como `true` (`false` por padrão) e clique em **Salvar tudo**.
3. Quando a reindexação for concluída, a propriedade reindex será definida novamente como `false`, e a contagem de reindexação será incrementada em 1.

   >[!NOTE]
   >
   > Isso pode levar alguns minutos, dependendo da quantidade de dados presentes.
4. Siga as mesmas etapas para outros índices adicionados ou modificados: `guidesBulkActivation`, `guidesPeerLinkIndex` e `guidesKonnectTemplateIndex`.

## Etapas para indexar o conteúdo existente



Execute as seguintes etapas para indexar o conteúdo existente:

- Execute uma solicitação POST no servidor \(com autenticação correta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados || Exemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação do GET com a ID do trabalho para o mesmo ponto de extremidade - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por exemplo: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.


>[!NOTE]
>
> Se você estiver usando o esquema personalizado, defina o caminho dos arquivos DTD e XSD catalog.xml personalizados no repositório do AEM na opção **Integrar catálogos**.




## Etapas para lidar com o conflito `'fmdita rewriter'`

O Experience Manager Guides tem um módulo [**personalizado de reescrita do sling**](../cs-install-guide/conf-output-generation.md#custom-rewriter) para manipular os links gerados no caso de mapas cruzados (links entre os tópicos de dois mapas diferentes).

Se você tiver outro reescritor sling personalizado em sua base de código, use um valor de `'order'` maior que 50, pois o reescritor Experience Manager Guides sling usa `'order'` 50.  Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de regravação de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta atualização, como o valor de `'order'` é alterado de 1000 para 50, você precisa mesclar o reescritor personalizado existente, se houver, com `'fmdita-rewriter'`.



## Etapas para reindexar o damAssetLucene

A definição do índice é atualizada para damAssetLucene com Guias. Consulte [este artigo](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) para reindexar o damAssetLucene depois de atualizar para a versão 5.1.0.

>[!NOTE]
>
> Ao seguir a documentação, verifique se ambas as propriedades (reindex=true e reindex-async=true para /oak:index/damAssetLucene) são atualizadas simultaneamente por meio da operação de salvamento.



**Tópico pai:** [Baixar e instalar](download-install.md)
