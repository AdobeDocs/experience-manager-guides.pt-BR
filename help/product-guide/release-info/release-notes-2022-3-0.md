---
title: Notas de versão do [!DNL AEM Guides], versão de março de 2022
description: Lançamento de março do [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: 885edbb5-dfe4-4bdc-bb66-0df64addb094
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# Lançamento de março do [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Atualização para a versão de março

Atualize seu atual [!DNL Adobe Experience Manager Guides] as a Cloud Service (mais tarde referido como *[!DNL AEM Guides]as a Cloud Service*), executando as seguintes etapas:
1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
1. Atualizar `<dox.version>` propriedade no `/dox/dox.installer/pom.xml` arquivo do seu código Git Cloud Service para 2022.3.123.
1. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de março do [!DNL AEM Guides] as a Cloud Service.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software suportados pela [!DNL AEM Guides] Versão as a Cloud Service de março de 2022.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Não compatível | Atualização 4 e superior para 2020 |
| | |


### Conector de oxigênio

| [!DNL AEM Guides] Versão na nuvem | Janelas do conector Oxygen | Conector Oxygen Mac |
| --- | --- | --- |
| 2022.3.0 | 2.4.0 | 2.4.0 |
|  |  |  |

*A linha de base e as condições criadas no AEM são compatíveis com as versões do FMPS a partir de 2020.2.

## Novos recursos e melhorias

### Novo painel Linha de base

[!DNL AEM Guides] A versão as a Cloud Service de março fornece o recurso de linha de base integrado ao Editor da Web. Agora você pode criar linhas de base no Editor da Web e usá-las para publicar ou traduzir tópicos de diferentes versões.

Observação: para um sistema atualizado, atualize o mais recente **ui_config.json** para Perfil de pasta.

Use este recurso para criar uma linha de base com uma versão específica dos tópicos disponíveis em uma data e hora específicas. Além disso, você obtém o suporte da API para criar ou atualizar uma linha de base com um rótulo definido para uma versão de tópicos.

![guia gerenciar linha de base](assets/baseline-manage.png)

Você pode pesquisar os arquivos com base nos nomes ou no local dos arquivos. Você também pode filtrar os tópicos a serem exibidos na janela de edição da linha de base e classificá-los com base em colunas específicas.

![guia gerenciar linha de base](assets/baseline-filter.png)

O desempenho do processo de criação da linha de base foi melhorado. O processo para criar linhas de base é assíncrono, assim, você pode continuar editando outros arquivos no Editor da Web enquanto a linha de base está sendo criada. Para obter mais detalhes, consulte *Criar e gerenciar linhas de base no Editor da Web* no Guia do usuário.

Observação: A guia Linha de Base no painel de mapa fica oculta por padrão. O administrador pode habilitar a guia Linha de base no painel do mapa.

### Comportamento de atualização do Editor da Web aprimorado

Os seguintes aprimoramentos estão disponíveis com a operação de atualização do navegador no Editor da Web:

* Agora você obtém o suporte para atualizar o navegador enquanto edita seu conteúdo no Editor da Web. Se você clicar no ícone de atualização do navegador enquanto um ou mais arquivos com alterações não salvas estiverem abertos para edição, será solicitado que você salve os arquivos ou cancele a ação de atualização.

* Mesmo ao atualizar o navegador, as exibições do painel esquerdo e do painel direito são mantidas.

* O tópico ativo ou mapa DITA é reaberto na área de edição de conteúdo.

### Aprimoramentos de publicação

O processo de publicação foi melhorado com a versão de março do [!DNL AEM Guides] as a Cloud Service:

* Linhas de base foram honradas para os metadados de saída do site AEM. Você também pode processar as propriedades de uma versão de linha de base como metadados. Se nenhuma linha de base for definida, as propriedades da versão mais recente serão processadas como metadados.

* A variável **Nome do arquivo** e **Argumentos de linha de comando DITA-OT** foram adicionadas opções para predefinições de HTML5, EPUB e Saída personalizada. Agora você pode especificar o nome do arquivo com o qual deseja salvar a saída. Você também pode especificar os argumentos adicionais que deseja que o DITA-OT processe ao gerar saída.

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

* Não é possível adicionar elementos de primeiro plano e de segundo plano em um mapa usando a exibição Autor do Editor da Web. (7652)
* A árvore de referência é interrompida após a remoção de um tópico e a execução de uma operação de movimentação. (8804)
* Uma exceção é recebida ao visualizar o conteúdo após fazer upload de um ativo. (3638)
* O erro ocorre quando arquivos cuja pasta pai tem caracteres especiais no nome do arquivo são abertos no Oxygen (usando o **Editar no Oxygen** botão). (8918)
* A variável **Localizar No Repositório** A opção não localiza e realça o mapa DITA no Editor XML. (8796)
* A filtragem não mostra os resultados apropriados quando vários atributos são adicionados ao conteúdo no Editor de XML. (8795)
* Ocorre um erro ao adicionar um usuário como administrador no perfil da pasta quando a ID do usuário é numérica. (8908)

## Problemas conhecidos

A Adobe identificou o seguinte problema conhecido no [!DNL AEM Guides] Versão as a Cloud Service de março.

* A remoção de rótulos em referências diretas também remove os rótulos de referências indiretas.

* Não é possível refletir o título da linha de base atualizado sem atualizar manualmente o painel da linha de base.

* O recurso de visualização de versão no painel Histórico de Versões não mostra a visualização de um tópico selecionado.
