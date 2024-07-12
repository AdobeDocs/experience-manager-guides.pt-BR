---
title: Notas de versão | Novidades da versão 2024.4.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2024.4.0 do Adobe Experience Manager Guides as a Cloud Service.
exl-id: e9db535a-5ad5-4ff0-94af-b4425594316a
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '1806'
ht-degree: 0%

---

# Novidades da versão 2024.4.0

Este artigo aborda os recursos novos e aprimorados da versão 2024.4.0 do Adobe Experience Manager Guides.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2024.4.0](fixed-issues-2024-04-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2024.4.0](upgrade-instructions-2024-04-0.md).

## Capacidade de traduzir conteúdo em vários idiomas usando grupos de idiomas pré-configurados

O Experience Manager Guides agora permite criar grupos de idiomas e traduzir facilmente seu conteúdo em vários idiomas. Esse recurso ajuda a organizar e gerenciar traduções de acordo com as necessidades da organização.

Por exemplo, se você precisar traduzir o conteúdo para alguns países na Europa, é possível criar um grupo de idiomas para idiomas europeus, como inglês (EN), francês (FR), alemão (DE), espanhol (ES) e italiano (IT).



![painel de tradução](assets/translation-languages-2404.png){width="300" align="left"}

*Selecione os grupos de idiomas ou idiomas para os quais você deseja traduzir os documentos.*

>[!NOTE]
>
>Se a pasta de destino de um idioma estiver ausente ou se o idioma de destino for o mesmo da origem, ele ficará esmaecido e exibirá um sinal de aviso.

Como administrador, você pode criar grupos de idiomas e configurá-los para vários perfis de pasta. Como autor, você pode exibir os grupos de idiomas configurados no perfil da pasta.


De modo geral, a criação de grupos de idiomas aumenta a eficiência e a produtividade dos projetos de tradução, melhorando, em última análise, o processo de localização em vários idiomas.


Saiba como [traduzir documentos do Editor da Web](../user-guide/translate-documents-web-editor.md).



## Excluir ou desabilitar o projeto de tradução automaticamente após a tradução

Agora, como administrador, você pode configurar os projetos de tradução para serem desativados ou excluídos automaticamente após concluir a tradução. Esse recurso ajuda você a usar os recursos e gerenciar arquivos com eficiência após concluir a tradução.

Excluir um projeto remove permanentemente todos os arquivos e pastas presentes no projeto. A exclusão dos projetos de tradução também permite liberar o espaço em disco ocupado.

Você pode desativar os projetos de tradução se desejar usá-los posteriormente.

![](assets/editor-setting-translation.png){width="550" align="left"}


*Defina os grupos de idiomas e as configurações de limpeza para projetos de tradução.*


Saiba mais sobre como [excluir ou desabilitar automaticamente o projeto de tradução](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).


## Ativar a saída dos mapas na coleção de ativação em massa na instância de Visualização

Agora, além de ativar a saída para sua coleção de ativação em massa na instância de publicação, o Experience Manager Gudies as Cloud Service fornece o recurso para ativá-lo na instância **Preview**.


Este recurso ajuda a ativar o conteúdo para uma instância de visualização, permitindo verificar sua aparência e funcionamento antes de ativá-lo para a instância do **Publish**.


![ criou a guia de histórico de auditoria da coleção de ativação em massa](assets/bulk-collection-audit-history.png){width="800" align="left"}

*Exiba as informações sobre as saídas do mapa ativado na guia **Histórico de Auditoria**.*


Saiba mais sobre a [ativação em massa](../user-guide/conf-bulk-activation-publish-map-collection.md).

## Aprimoramentos nos conectores de fonte de dados

Os seguintes aprimoramentos foram feitos nos conectores de fonte de dados da versão 2024.4.0:

### Conecte-se às fontes de dados do Salsify, Akeneo e Microsoft Azure DevOps Boards (ADO)

Além dos conectores prontos para uso existentes, o Experience Manager Guides também fornece conectores para fontes de dados do Salsify, Akeneo e Microsoft Azure DevOps Boards (ADO). Como administrador, você pode baixar e instalar esses conectores. Em seguida, configure os conectores instalados.

### Copie e cole o exemplo de consulta para criar um trecho de conteúdo ou tópico

Você pode copiar e colar facilmente uma amostra de consulta de dados no gerador para criar um trecho de conteúdo ou tópico. Com esse recurso, não é necessário lembrar a sintaxe ou criar um query manualmente. Em vez de digitar manualmente a consulta, você pode copiar e colar uma consulta de exemplo, editá-la e usá-la para buscar os dados de acordo com suas necessidades.

![caixa de diálogo inserir trecho do conteúdo](assets/insert-content-snippet.png){width="800" align="left"}

*Copie e edite uma consulta de exemplo para criar o trecho de conteúdo.*

### Conectar-se a arquivos de dados JSON usando um conector de arquivos


Agora, como administrador, você pode configurar um conector de arquivo JSON para usar arquivos de dados JSON como fonte de dados. Use o conector para importar os arquivos JSON do seu computador ou do Adobe Experience Manager Assets. Em seguida, como autor, você pode criar fragmentos de conteúdo ou tópicos usando os geradores.

Esse recurso ajuda você a usar os dados armazenados em seus arquivos JSON e reutilizá-los em vários snippets. O conteúdo também é atualizado dinamicamente sempre que você atualiza os arquivos JSON.

### Configure vários URLs de recursos para um conector criar trechos de conteúdo ou tópicos

Como administrador, você pode configurar vários URLs de recursos para alguns conectores, como Cliente REST genérico, Salsify, Akeneo e placas DevOps (ADO) do Microsoft Azure.

Em seguida, como autor, conecte-se às fontes de dados para criar trechos de conteúdo ou tópicos usando os geradores. Esse recurso é útil, pois você não precisa criar uma fonte de dados para cada URL. Ele ajuda você a buscar dados rapidamente de qualquer um dos recursos de uma fonte de dados específica em um único trecho de conteúdo ou tópico.

Exibir mais detalhes sobre os conectores de fonte de dados e como [configurar um conector de fonte de dados na interface do usuário](../cs-install-guide/conf-data-source-connector-tools.md).

Saiba como [usar dados da sua fonte de dados](../user-guide/web-editor-content-snippet.md).

## Personalizar sua experiência no Editor da Web com a nova interface do usuário de preferências do usuário

A caixa de diálogo **Preferências do Usuário** no Editor da Web agora inclui uma nova guia **Aparência**. Esta nova guia permite configurar convenientemente as preferências mais comuns de aparência na interface do Editor da Web.

Você pode configurar a exibição dos arquivos por título ou nome de arquivo e alterar o tema do aplicativo e a exibição do código-fonte. Também ajuda a definir as configurações para localizar um arquivo aberto na exibição de repositório e lidar com espaços não separáveis.

![guia aparência das preferências do usuário](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Personalize a aparência de acordo com suas preferências.*

Saiba mais sobre a descrição do recurso **Preferências do usuário** na seção [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Localizar um arquivo aberto na visualização de repositório do Editor da Web

Selecione a opção **Sempre localizar arquivos no repositório** em **Preferências do Usuário** para navegar rapidamente e localizar seu arquivo no modo de exibição de repositório. Você não precisa pesquisá-la manualmente.

Ao editar, esse recurso também ajuda a visualizar facilmente o local do arquivo na hierarquia do repositório.

Para obter mais detalhes, exiba [localizar um arquivo aberto na exibição de repositório](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).


## Manuseio aprimorado de espaços não separáveis no Editor da Web

O Experience Manager Guides permite que você mostre um indicador de espaço sem quebra ao editar documentos no Editor da Web. Também melhora o manuseio de espaços não separáveis.
Ele converte vários espaços em branco consecutivos em um único espaço para preservar a visualização WYSIWYG do documento no Editor da Web. Esse recurso também ajuda a melhorar a aparência geral e o profissionalismo do documento.


Para obter mais detalhes, exiba os [outros recursos do Editor da Web](../user-guide/web-editor-other-features.md).




## Desative o pós-processamento para pastas seletivas no Adobe Experience Manager Assets


Como administrador, agora você pode desativar o pós-processamento e a geração de UUIDs para pastas seletivas no Experience Manager Assets. Essa configuração pode ser útil, especialmente ao lidar com muitos ativos ou estruturas de pastas complexas. Também ajuda vários usuários a fazer upload dos ativos simultaneamente rapidamente, sem interferir uns nos outros.  

Desativar o pós-processamento para uma pasta também afeta todas as suas pastas secundárias. No entanto, o Experience Manager Guides agora oferece a capacidade de ativar seletivamente o pós-processamento para pastas secundárias individuais na pasta ignorada.

Saiba como [desabilitar o pós-processamento para uma pasta](../cs-install-guide/conf-folder-post-processing.md).

## Experiência renovada para pesquisar e filtrar arquivos na visualização de repositório

Agora, você tem uma experiência aprimorada ao filtrar arquivos. A funcionalidade renovada para filtrar arquivos fornece uma maneira aprimorada de pesquisar e navegar facilmente pelos arquivos.


![pesquisar arquivos no modo de exibição de repositório](assets/repository-filter-search-2404.png){width="300" align="left"}

*Pesquisar os arquivos que contêm o texto`general purpose.`*

Aproveite benefícios como acesso mais rápido a arquivos relevantes e uma interface do usuário mais intuitiva, tornando sua experiência de pesquisa mais estável e eficiente.

![filtro de pesquisa rápida ](assets/repository-filter-search-quick.png) {width="300" align="left"}

*Use os filtros rápidos para procurar arquivos DITA e não DITA.*

Saiba mais sobre o recurso **Pesquisa de filtro** na seção [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Lista segmentada para exibir e inserir elementos válidos de acordo com sua posição

Ao editar um documento no Editor da Web, agora é possível exibir uma lista separada de elementos válidos no local atual e fora dele. Com base nas suas necessidades, você escolhe um elemento entre as seguintes opções:

* **Elementos válidos no local atual** que você pode inserir no próprio local do cursor atual.
* **Elementos válidos fora do local atual** que você pode inserir depois de qualquer um dos pais para o elemento atual na hierarquia de elementos.

![Inserir caixa de diálogo do elemento](assets/insert-element-dialog.png){width="300" align="left"}

*Exiba as listas segregadas de elementos válidos para inserir um elemento no local atual.*


Essa lista dividida de elementos válidos ajuda a manter a estrutura de conteúdo e a seguir os padrões DITA.

Saiba mais sobre o recurso **Inserir Elemento** na seção [Barra de ferramentas secundária](../user-guide/web-editor-features.md#2051ea0j0y4).


## O Tipo de propriedades de conteúdo é exibido como um menu suspenso

Agora, as Propriedades de Conteúdo **Tipo** aparecem como um menu suspenso. Você pode visualizar e selecionar as tags da hierarquia completa para a tag atual na lista suspensa.

Esse menu suspenso ajuda a acessar rapidamente as tags relevantes na estrutura hierárquica.


![menu suspenso de tipos nas propriedades de conteúdo](assets/content-properties-type.png){width="300" align="left"}

*Selecione uma marca da hierarquia para a marca atual.*

Saiba mais sobre o recurso **Propriedades de Conteúdo** na seção [Painel Direito](../user-guide/web-editor-features.md#id2051eb003yk).



## Desempenho aprimorado ao verificar arquivos em massa no Editor de mapa

O Experience Manager Guides melhora o desempenho e a experiência do recurso de check-in de arquivos em massa do Editor de mapas. Essa melhoria ajuda a fazer o check-in dos arquivos em massa com mais rapidez.
Você também pode visualizar o progresso da operação de check-in para os arquivos da caixa de diálogo **Salvar como nova versão e Desbloquear**. Por fim, a mensagem de sucesso é exibida após a conclusão da operação e o check-in de todos os arquivos com check-out selecionados.

![Salvar como nova versão e desbloquear a caixa de diálogo](./assets/save-version-lock.png){width="300" align="left"}

*Exiba a lista e o status dos arquivos com check-in em massa do Editor de Mapas.*

Saiba como [trabalhar com o Editor de Mapa Avançado](../user-guide/map-editor-advanced-map-editor.md)

## Baixar o arquivo temporário ao gerar a saída pelo DITA-OT

Você também pode baixar os arquivos temporários gerados ao publicar a saída do site AEM, HTML, Personalizada, JSON ou PDF por meio do DITA-OT. Esse recurso ajuda você a analisar quaisquer problemas que possam ocorrer durante o processo de geração de saída e solucionar problemas com eficiência.  
Você também pode baixar o arquivo metadata.xml se tiver selecionado quaisquer propriedades de metadados que foram passados para a saída gerada usando DITA-OT. 

Para obter mais detalhes sobre as predefinições, consulte [Noções básicas sobre as predefinições de saída](../user-guide/generate-output-understand-presets.md).


## Substitua as credenciais do JWT do IMS pelas credenciais do OAuth do IMS para publicação baseada em microsserviços


As credenciais da Conta de Serviço (JWT) foram substituídas em favor das credenciais **Servidor a Servidor do OAuth**. Seus aplicativos que usam as credenciais da Conta de serviço (JWT) deixarão de funcionar após 1º de janeiro de 2025. Você deve migrar para a nova credencial até 1º de janeiro de 2025 para garantir que seu aplicativo continue funcionando.


O serviço de publicação na nuvem do Experience Manager Guides agora é protegido pela autenticação baseada em OAuth do Adobe IMS. Saiba como [configurar a publicação baseada em microsserviço com autenticação OAuth](../knowledge-base/publishing/configure-microservices-imt-config.md).
