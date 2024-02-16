---
title: Notas de versão | Guias do Adobe Experience Manager as a Cloud Service, versão de abril de 2022
description: Versão de abril do Adobe Experience Manager Guides as a Cloud Service
exl-id: c735ba24-a803-454b-8723-57dacf90061b
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---

# Versão de abril do Adobe Experience Manager Guides as a Cloud Service

## Atualização para a versão de abril

Atualize seu atual [!DNL Adobe Experience Manager Guides] as a Cloud Service (mais tarde referido como *[!DNL AEM Guides]as a Cloud Service*), executando as seguintes etapas:
1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
1. Atualizar `<dox.version>` propriedade no `/dox/dox.installer/pom.xml` arquivo do seu código Git Cloud Service para 2022.4.133.
1. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de abril do [!DNL AEM Guides] as a Cloud Service.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software suportados pela [!DNL AEM Guides] Versão as a Cloud Service de abril de 2022.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Não compatível | Atualização 4 e superior para 2020 |
| | |


### Conector de oxigênio

| Versão do AEM Guides Cloud | Janelas do conector Oxygen | Conector Oxygen Mac |
| --- | --- | --- |
| 2022.4.0 | 2.5.6 | 2.5.6 |
|  |  |  |

*A linha de base e as condições criadas no AEM são compatíveis com as versões do FMPS a partir de 2020.2.

## Novos recursos e melhorias

Muitos aprimoramentos e novos recursos foram adicionados ao Editor da Web:

### Resolução de chave aprimorada

Uma referência de chave de conteúdo DITA insere uma parte do conteúdo de um tópico em outro. Ele usa uma chave para localizar o conteúdo. As principais referências associadas a um tópico DITA precisam ser resolvidas. O mapa raiz selecionado tem a precedência mais alta para resolver referências principais.

![caixa de diálogo preferências do usuário](assets/user-preferences.png)

Agora, as principais referências são resolvidas com base no mapa raiz definido na seguinte ordem de prioridade:

1. Preferências de usuário
1. Painel Exibição de mapa
1. Perfil da pasta

Para obter mais detalhes, consulte *Resolver referências de chave* no Guia do usuário.

### Adicionar um painel personalizado no painel esquerdo

Agora é possível adicionar um painel personalizado no painel esquerdo do Editor da Web. Você pode usar um painel personalizado para várias finalidades, como fornecer ajuda ou fazer o teste de um projeto. Se um painel personalizado tiver sido configurado, ele também aparecerá na lista de painéis dentro do **Configurações do editor**. Você pode alternar o botão para mostrar ou ocultar o painel personalizado.

### Capacidade de alterar o estado do documento de tópicos em um mapa DITA

Agora é possível alterar facilmente o estado do documento de tópicos selecionados em um mapa DITA. Também é possível abrir e editar as propriedades de tópicos selecionados em um mapa DITA na **Mais opções** na parte inferior do painel Exibição de mapa.

![propriedades do tópico selecionado](assets/map-view-properties.png)

### Informações de versão exibidas no modo de Visualização

O Editor da Web ajuda você a gerenciar suas versões. Agora você também pode ver a versão do tópico ativo ou o mapa DITA no canto superior direito da guia Arquivo do tópico no modo Visualização de um tópico.

![versão de visualização](assets/preview-version.png)

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

* Os novos rótulos não são refletidos automaticamente na lista suspensa Adicionar/remover rótulo. Em vez disso, é necessário atualizar a linha de base. (9249)
* Não é possível editar o título da linha de base se uma linha de base for criada por critérios de rótulo. (9171)
* A publicação de um trabalho usando uma linha de base fica paralisada no estado &quot;aguardando&quot; se o status da linha de base for alterado para &quot;falha&quot;. (9194)
* A remoção de rótulos em referências diretas também remove os rótulos de referências indiretas. (9257)
* A pesquisa à medida que você digita faz com que solicitações de pesquisa indesejadas sejam exibidas na exibição Repositório. (9307)
* Problemas ocorrem quando qualquer palavra-chave é usada no título da guia. (9318)
* A linha de base falha ao adicionar um rótulo com espaços. (9362)
* A saída do site AEM não exibe o elemento glossusage corretamente. (8936)
* Ocorre um erro de console ao abrir o **Output** no Editor da Web. (8715)
* A mensagem de erro exibida ao publicar um tipo de registro manual por meio do Salesforce não é intuitiva. (8952)
* A configuração Validar com atributos de condição não é aberta imediatamente. Em vez disso, o usuário precisa reabrir o arquivo para ver as validações. (9300)
* Os metadados não podem ser removidos uma vez que um mapa DITA é publicado com metadados.  (9178)
* O painel Tradução fica visível mesmo ao abrir o mapa DITA no Editor de mapa. (9053)
* O DTD personalizado definido pelo usuário não tem precedência sobre o DTD DITA padrão incorporado no DITA-OT. (9104)
* No recurso PDF nativo, o upload nos modelos falha para arquivos não DITA e não de imagem. (9070)
* O mecanismo de autorização executa duas consultas em vez de uma, em alguns cenários especializados. (9221)
* A publicação da saída do site AEM falha ao usar DTD personalizado. (9243)
* A nota de rodapé de uso por referência não rola até a seção de nota de rodapé na saída do site AEM. (9234)

## Problemas conhecidos

A Adobe identificou o seguinte problema conhecido no [!DNL AEM Guides] Versão as a Cloud Service de abril.

* O Editor da Web não relata um erro quando duas ou mais linhas de base são criadas com o mesmo nome, mas têm diferenças de espaço ou caixa. Por exemplo, &quot;adobe&quot; e &quot;Adobe &quot; ou &quot;Adobe&quot;.
* O conector Oxygen trava intermitentemente ao fazer login ou logout frequentes ou alternar entre diferentes tipos de autenticação.
