---
title: Notas de versão | Novidades no Adobe Experience Manager Guides, versão de junho de 2023
description: Conheça os recursos novos e aprimorados da versão de junho de 2023 do Adobe Experience Manager Guides as a Cloud Service
exl-id: 625f9702-2b91-4622-9fec-282f47f1d7a6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# Novidades da versão de junho de 2023 do Adobe Experience Manager Guides as a Cloud Service

Este artigo aborda os recursos novos e aprimorados da versão de junho de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *Guias de AEM as a Cloud Service*).

Para obter mais detalhes sobre as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos nesta versão, consulte [Notas de versão](release-notes-2023.6.0.md).

## Relatório de Links quebrados no Editor da Web

O Guia AEM permite verificar a integridade geral de seus documentos técnicos e gerar relatórios do Editor da Web. Agora, na versão de junho de 2023, o Guia AEM fornece o recurso para visualizar e corrigir links com falha. Esse é um relatório útil que ajuda a gerenciar links com falha. É possível visualizar facilmente os links corrompidos presentes no mapa DITA e corrigi-los.
![](assets/broken-link-report.png){width="800" align="left"}

Depois de corrigir um link, ele não é exibido abaixo da lista de links quebrados.

Para obter mais detalhes, consulte [Exibir e corrigir links corrompidos](../user-guide/reports-web-editor.md#report-broken-links).

## Renomear e mover arquivos na visualização Repositório

Agora, você também pode renomear ou mover um arquivo do painel do repositório. Esse recurso é útil e ajuda a gerenciar os arquivos facilmente no painel Repositório. É possível selecionar um arquivo e renomeá-lo ou movê-lo usando a **Opções** para o arquivo selecionado. O Guias do AEM exibe uma mensagem de sucesso quando você move ou renomeia um arquivo.

![](assets/rename-move-assets.png){width="650" align="left"}

Para obter mais detalhes sobre o menu Opções de um arquivo, consulte **Exibição de repositório** descrição do recurso na [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS) seção.

## Aprimoramentos de PDF nativo

### Adicionar uma marca d&#39;água à saída do PDF para documentos de rascunho

Agora você pode adicionar uma marca d&#39;água à saída em PDF do documento que ainda não foi aprovado. Essa marca d&#39;água não aparecerá se você gerar o PDF para o documento no estado de documento ‘Aprovado’. Por exemplo, você pode adicionar um Rascunho de marca d&#39;água para a saída de PDF.

Para obter mais detalhes, consulte [Adicionar uma marca d&#39;água à saída do PDF para documentos de rascunho](../native-pdf/use-javascript-content-style.md#watermark-draft-document).

### Suporte para variáveis de idioma

Os Guias do AEM fornecem suporte para variáveis de idioma. Você pode usar variáveis de idioma para definir uma versão localizada dos rótulos prontos para uso como Observação, Cuidado e Aviso ou texto estático na saída de PDF.
Você pode adicionar as variáveis de idioma ou a versão localizada dos rótulos às seções apropriadas na saída de PDF e nos modelos de saída.

#### Variáveis de linguagem na saída do PDF

Você pode usar as variáveis de idioma para definir rótulos localizados para elementos como Nota, Cuidado e Aviso. Você pode atualizar o valor dessas variáveis em um ou mais idiomas e, em seguida, o valor localizado é escolhido automaticamente na saída do PDF.
Por exemplo, você pode apresentar o rótulo Observação na saída de PDF das seguintes maneiras:

* Inglês: Note
* Francês: Remarque
* Alemão: Hinweis

#### Variáveis de idioma nos modelos de saída

Se você quisesse criar a saída de PDF em vários idiomas, seria necessário criar diferentes modelos de PDF contendo texto localizado para cada idioma. Agora, com o recurso de variáveis de idioma, é necessário criar o modelo apenas uma vez. Em seguida, para qualquer texto estático que precise localizar, é possível criar variáveis de idioma correspondentes e usá-las no modelo.
É possível criar variáveis de idioma para textos mais longos, como uma frase inteira ou até mesmo um parágrafo. Também é possível aplicar estilos e usar a marcação HTML para formatar essas variáveis de idioma.

Para obter mais detalhes, consulte [Suporte para variáveis de idioma](../native-pdf/native-pdf-language-variables.md).

### Capacidade de usar metadados de AEM em layouts de PDF

Os metadados são a descrição ou definição do seu conteúdo. Esses metadados são armazenados no conteúdo do mapa DITA de origem.

Agora, em Guias AEM, você também pode selecionar as propriedades de metadados de seus ativos e adicioná-los ao layout da página. Em seguida, o AEM Guides escolhe essas propriedades de metadados de seus ativos e as publica na saída de PDF.


![](assets/native-pdf-metadata-asset.png){width="550" align="left"}

>[!NOTE]
>
> O Guia AEM também é compatível com as propriedades de metadados dos mapas DITA.

Para obter mais detalhes, consulte [Adicionar campos e metadados](../native-pdf/design-page-layout.md#add-fields-metadata).


## Aprimoramentos do esquema

### Usar instruções de relatório para verificar regras no Schematron

Os Guias do AEM agora também oferecem suporte às instruções de relatório com o Schematron. Uma instrução de relatório gera uma mensagem quando uma instrução de teste é avaliada como verdadeira. Por exemplo, se você quiser que a descrição curta tenha 150 caracteres ou menos, poderá definir uma instrução de relatório para verificar os tópicos em que a descrição curta tem mais de 150 caracteres.

Para obter mais detalhes, consulte [Usar instruções assert e report para verificar regras](../user-guide/support-schematron-file.md#schematron-assert-report).

### Usar expressões Regex

Também é possível usar expressões Regex para definir uma regra com a função matches() e executar a validação usando o arquivo Schematron.

Para obter mais detalhes, consulte [Usar expressões Regex](../user-guide/support-schematron-file.md#schematron-assert-report).


### Definir padrões abstratos

Guias AEM também suporta padrões abstratos no Schematron. Você pode definir padrões abstratos genéricos e reutilizar esses padrões abstratos. Padrões abstratos podem simplificar seu esquema Schematron e também ajudar a gerenciar e atualizar sua lógica de validação.


Para obter mais detalhes, consulte [Definir padrões abstratos](../user-guide/support-schematron-file.md#schematron-abstract-patterns).

## Navegar do Editor da Web para a página inicial do AEM

Agora você pode navegar facilmente do Editor da Web para a página inicial do AEM.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* Clique em **Guias** ícone (![](assets/aem-guides-icon.png) ), para voltar à página de Navegação por AEM.


Para obter mais detalhes, consulte [Página de navegação do AEM](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Lidar com definições hierárquicas de definições e enumerações de assunto

Guias AEM vêm com o recurso poderoso para criar mapas de esquema de sujeito que são uma forma especializada de mapas DITA que são usados para definir sujeitos taxonômicos e valores controlados. Agora, o AEM Guides também permite definir a definição do assunto em um mapa e as definições de enumeração em outro mapa. Em seguida, você pode adicionar a referência do mapa e usar o esquema de assunto.
As referências de enumeração de assunto são resolvidas no mesmo mapa ou no mapa referenciado.

Para obter mais detalhes sobre como lidar com definições hierárquicas de definições de assunto e enumerações, consulte **Esquema do assunto** descrição do recurso na [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS) seção.

## Suporte para o formato XLIFF na tradução

Guias do AEM também oferecem suporte para o formato XML Localization Interchange File Format (XLIFF) na tradução. Agora você também pode optar por **Criar um novo projeto de tradução XLIFF** para converter o conteúdo XML no formato XLIFF.
Usando esse formato, você pode exportar o conteúdo para o formato XLIFF padrão do setor e, em seguida, fornecer o mesmo aos fornecedores de tradução. Para obter mais detalhes, consulte [Criar um projeto de tradução](../user-guide/translate-documents-web-editor.md#create-translation-project).

![](assets/translation-project-types.png){width="350" align="left"}



## Painel Favoritos aprimorado

O Guia AEM ajuda você a criar uma coleção ou lista de favoritos de seus arquivos e pastas e usá-los facilmente. Agora **Opções** O menu também está disponível no **Favoritos** painel. É possível renomear a coleção selecionada ou excluí-la da **Opções** menu. É possível selecionar a variável **Atualizar** opção para obter uma nova lista de arquivos ou pastas do repositório. Também é possível exibir o conteúdo da pasta na interface do usuário do Assets.

![](assets/favorites-options.png){width="650" align="left"}

>[!NOTE]
>
> Também é possível atualizar a lista usando o **Atualizar** ícone na parte superior.

Para obter mais detalhes sobre o **Opções** de uma coleção Favoritos, consulte a seção **Favoritos** descrição do recurso na [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS) seção.

## Mudar para o tema do sistema

Agora, também é possível usar o tema do dispositivo. Usar o **Preferências do usuário**, você pode configurar o AEM Guides para alternar automaticamente entre temas claros e escuros com base no tema do seu dispositivo.

![](assets/device-theme-user-preferences.png){width="550" align="left"}

Para obter mais detalhes, consulte **Preferências do usuário** descrição do recurso na [Barra de ferramentas principal](../user-guide/web-editor-features.md#id2051EA0G05Z) seção.
