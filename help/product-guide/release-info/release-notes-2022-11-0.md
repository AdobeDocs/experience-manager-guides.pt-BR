---
title: Notas de versão | Adobe Experience Manager Guides as a Cloud Service, versão de novembro de 2022
description: Versão de novembro do Adobe Experience Manager Guides as a Cloud Service
exl-id: 9f329ec1-dd74-47cc-8567-3fadd962584a
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 0%

---

# Versão de novembro do Adobe Experience Manager Guides as a Cloud Service

## Atualização para a versão de novembro

Atualize sua configuração atual do Adobe Experience Manager Guides as a Cloud Service (mais tarde chamada de *AEM Guides as a Cloud Service*) executando as seguintes etapas:
1. Confira o código Git do Cloud Services e alterne para a ramificação configurada no pipeline do Cloud Services correspondente ao ambiente que você deseja atualizar.
1. Atualize a propriedade `<dox.version>` no arquivo `/dox/dox.installer/pom.xml` do seu código Git do Cloud Services para 2022.11.198.
1. Confirme as alterações e execute o pipeline dos Serviços em nuvem para atualizar para a versão de novembro do AEM Guides as a Cloud Service.

## Etapas para indexar o conteúdo existente (somente se você estiver em uma versão anterior à versão de setembro do AEM Guides as a Cloud Service)

Execute as seguintes etapas para indexar o conteúdo existente e usar o novo texto de localização e substituição no nível do mapa:

* Execute uma solicitação POST para o servidor (com autenticação correta) - `http://<server:port>/bin/guides/map-find/indexing`.
(Opcional: é possível passar caminhos específicos dos mapas para indexá-los; por padrão, todos os mapas serão indexados || Exemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* A API retornará um jobId. Para verificar o status do trabalho, você pode enviar uma solicitação GET com a ID do trabalho para o mesmo ponto de extremidade - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Por exemplo: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Quando o trabalho for concluído, a solicitação do GET acima responderá com sucesso e mencionará se algum mapa falhou. Os mapas indexados com êxito podem ser confirmados nos logs do servidor.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com a versão de novembro de 2022 do AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Não compatível | Atualização 4 e superior para 2020 |
| | |

*A linha de base e as condições criadas no AEM são compatíveis com as versões do FMPS a partir de 2020.2.

### Conector de oxigênio

| Versão do AEM Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.11.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |  |


## Novos recursos e melhorias

O AEM Guides as a Cloud Service fornece melhorias e novos recursos na versão de novembro:


### Excluir arquivos do painel de repositório

Agora é possível excluir facilmente arquivos (um único arquivo por vez) do menu **Opções** do arquivo selecionado no painel de repositório.
<img src="assets/repository-delete-file.png" alt="Excluir do repositório" width="500">

Um prompt de confirmação é exibido antes de excluir o arquivo. Se o arquivo não for referenciado a partir de outro arquivo, ele será excluído e uma mensagem de sucesso será exibida.

Se o arquivo selecionado estiver com check-out, não será possível excluí-lo e uma mensagem de erro será exibida. Se o arquivo selecionado for adicionado a uma coleção de favoritos ou for referenciado de qualquer outro arquivo, o AEM guides verificará sua confirmação e oferecerá a opção de excluí-lo à força. Se você excluir um tópico referenciado e tiver aberto o arquivo contendo referências para edição, ele mostrará o link corrompido para o arquivo referenciado.

**Observação**: você também pode excluir o arquivo selecionado usando a tecla Delete do teclado.


### Remoção de versões selecionadas de arquivos

À medida que você cria e mantém seu conteúdo, muitas versões podem ser criadas para seus arquivos DITA no repositório. O AEM Guides permite que você remova do repositório versões anteriores dos arquivos DITA e libere espaço em disco.

<img src="assets/preview-purge-report.png" alt="Visualizar relatório de limpeza" width="500">


O AEM Guides não exclui a primeira versão do arquivo ou uma versão que esteja incluída em uma linha de base ou tenha um rótulo aplicado a ela. A operação de limpeza nem mesmo exclui arquivos incluídos em uma tradução ou em um fluxo de trabalho de revisão. Você pode escolher o número de versões a serem mantidas e também decidir excluir os arquivos mais antigos que o número definido de dias.

Antes de iniciar a operação de expurgação, você pode visualizar o relatório para ver as versões que serão expurgadas. Você pode decidir iniciar ou cancelar a operação de expurgação.

<img src="assets/download-purge-report.png" alt="Relatório de limpeza de PDownload" width="500">

Quando a operação de expurgação estiver concluída, você poderá verificar o relatório de expurgação para ver os arquivos expurgados.

### Gerenciar predefinições de saída de perfil global e de pasta

O AEM Guides fornece o recurso para criar e gerenciar predefinições de saída para os Perfis global e de pasta. Em seguida, é possível usar facilmente essas predefinições de saída para gerar saída para todos os mapas relacionados a esse perfil Global ou de Pasta.

<img src="assets/add-global-output-preset.png" alt="Adicionar perfil global" width="400">

**Observação**: somente usuários administrativos no nível da pasta podem criar predefinições de Perfil Global e de Pasta.

Essas predefinições globais aparecem na guia **Saída** de todos os mapas relacionados. Você pode usá-los para gerar a saída para todos os mapas relacionados. É possível selecionar a predefinição como predefinição padrão do PDF para gerar a saída do PDF. Você também pode **Editar**, **Renomear**, **Duplicar** ou **Excluir** uma predefinição de saída existente do menu **Opções**.

### Coluna Rótulo da versão adicionada ao painel de tradução

No painel de tradução, também é possível ver a coluna Rótulo da versão. Isso exibe o Rótulo da versão selecionada do arquivo de origem. Isso pode ajudá-lo a selecionar todos os arquivos com um rótulo específico e traduzi-los de uma só vez.

<img src="assets/send-translation.png" alt="enviar para tradução" width="600">


### PDF nativo | PDF com barra de alterações mostrando a diferença entre versões de documentos

Agora você pode criar uma PDF que mostra as diferenças no conteúdo entre duas versões usando a barra de alteração. Você pode optar por comparar a versão atual com uma linha de base da versão anterior ou comparar entre as duas versões de linha de base selecionadas.

<img src="assets/pdf-change-version.png" alt="spdf-change-version" width="600">

Uma barra de alteração é exibida no PDF para indicar o conteúdo modificado, inserido ou excluído. Você também tem as opções para fazer o seguinte:
* Mostrar o conteúdo inserido em verde e sublinhado
* Mostrar o conteúdo excluído em vermelho e marcado com um tachado

### PDF nativo | Suporte de variável para caminho de saída e nome de arquivo PDF

Agora, você também pode usar as variáveis prontas para uso a seguir para definir o Caminho de saída e o Arquivo do PDF. Você pode usar uma única variável ou uma combinação de variáveis para definir essas opções:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (Somente para Caminho de Saída)
* `${path_after_langfolder}` (Somente para Caminho de Saída)


### PDF nativo | Gerar sumário para mapas DITA e reordenar layouts de página

Agora, também é possível gerar o índice em mapas DITA usando uma configuração avançada do PDF do modelo. Você pode optar por ativar ou desativar a exibição dos vários layouts de página e também reordenar sua posição.

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

* PDF nativo | `conkeyref` não é resolvido na saída gerada do PDF. (10564)
* PDF nativo | Problemas ao acessar metadados de um mapa na saída do PDF. (10556)
* PDF nativo | O estilo incorporado é usado para gerar tags em vez do nome da classe.  (10498)
* O Editor da Web carrega a página em branco intermitentemente. (10678)
* A publicação no PDF falhará se criarmos uma predefinição por meio da duplicação de uma predefinição existente. (10584)
* O botão **Exibir Log** não funciona quando a geração de PDF falha para uma predefinição. (10576)
* A observação dentro de uma tag para, que é um conref, não é exibida na pré-visualização. (10559)
* Acertar o espaço traseiro no final de um item de lista remove a lista inteira. (10540)
* Ao usar uma exportação nativa do PDF, os `<indexterm>` aninhados não são aninhados no índice. (10521)
* O botão **Recuo Automático** da barra de ferramentas está ausente na Exibição do Source. (10448)
* O primeiro caractere de um item de lista é perdido enquanto a lista está sendo criada no editor. (10447)
* Vários pop-ups são exibidos se qualquer versão de ativo DITA for alterada e salva na janela de edição da linha de base. (10399)
* Ocorre um erro de aplicativo ao clicar no botão **Editar** depois de selecionar todas as predefinições de Saída no painel Geração rápida. (10388)
* Os metadados personalizados para o tópico DITA não são retidos quando uma ação de copiar e colar é executada da interface do usuário do Assets. (10367)
* O pós-processamento está bloqueado para toda a pasta de idioma cujos ativos estão presentes em um projeto de tradução ativo. (10332)
* A guia Modelo no Editor de XML não está visível para administradores de perfil de pasta. (10266)
* Problemas de navegação ocorrem no Editor da Web após a atualização 4.0. (10159)
* Os arquivos do SVG não são exibidos no modo Visualização. (10010)
* Se a guia Saída do editor contiver mais predefinições, a seção predefinições não poderá ser rolada e todas as predefinições não serão exibidas. (9787)
* As opções **Editar** e **Anotar** para uma imagem não estão funcionando corretamente na exibição de coluna. (8758)
* O link peer não é resolvido e é exibido como um texto normal na saída gerada. (7774)
