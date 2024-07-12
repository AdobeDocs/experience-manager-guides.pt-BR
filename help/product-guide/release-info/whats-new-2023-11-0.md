---
title: Notas de versão | Novidades na Adobe Experience Manager Guides, versão de novembro de 2023
description: Conheça os recursos novos e aprimorados da versão de novembro de 2023 do Adobe Experience Manager Guides as a Cloud Service.
exl-id: 83c04e01-92f1-41b0-8866-a202f4106b51
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# Novidades da versão de novembro de 2023 do Adobe Experience Manager Guides as a Cloud Service

Este artigo aborda os recursos novos e aprimorados da versão de novembro de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *Experience Manager Guides as a Cloud Service*).

Para obter mais detalhes sobre as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos nesta versão, consulte as [Notas de versão](release-notes-2023-11-0.md).

## Aprimoramentos de PDF nativo

Os seguintes aprimoramentos do PDF nativo foram feitos na versão de novembro de 2023:

### Usar e duplicar modelos de PDF prontos para uso

A Experience Manager Guides fornece modelos de PDF de fábrica ou prontos para uso. Duplique os modelos de PDF de fábrica para criar os modelos de PDF personalizados.

Agora, você também pode visualizar a imagem em miniatura de um modelo ao criar e duplicar um modelo. Também é possível editar ou excluir essa imagem. Esse recurso é útil para marcar ou distinguir templates com nomes semelhantes.
Saiba mais sobre o [modelo de PDF](../native-pdf/pdf-template.md).

![Caixa de diálogo de modelo de PDF duplicado](assets/duplicate-template.png){width="550" align="left"}

*Duplicar um modelo de PDF existente.*


### Alterar a ordem das páginas e publicar várias páginas por folha

Além de publicar as páginas de acordo com o documento de origem, você também pode alterar a ordem das páginas no PDF ao publicar um documento de várias páginas.  Isso oferece a flexibilidade de publicar as páginas em várias ordens, como todas ímpares ou todas as páginas pares primeiro. Você também pode publicar como um livreto e ler as páginas como um livro. Você também pode decidir o número de páginas que deseja publicar em uma única folha de papel. Para obter mais detalhes, consulte a seção [Organização da página](../native-pdf/components-pdf-template.md#page-organization).

### Classificar termos do glossário com base nas chaves de classificação

Agora, você também pode classificar os termos do glossário com base nas teclas de classificação. Você pode usar a tag ‘sort-as’ para definir uma chave de classificação para os termos do glossário. Em seguida, você pode classificá-los com base nas teclas de classificação no lugar dos termos. Isso permite classificar os termos do glossário de acordo com os termos usados em diferentes idiomas. Você também pode definir uma única chave de classificação para um termo do glossário com uma frase ou um grupo de palavras.
Para obter mais detalhes, consulte as [Configurações avançadas do PDF](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Gerenciamento de recursos aprimorado para modelos de PDF nativos

A Experience Manager Guides agora melhorou o gerenciamento de recursos para modelos de PDF nativo. Agora é possível compartilhar e reutilizar recursos, como imagens, arquivos CSS e arquivos de fontes, em vários modelos de PDF nativos. Com essa melhoria, gerenciar os recursos de um grande conjunto de modelos é muito mais simples. Não é necessário criar recursos duplicados para cada modelo, e você pode mantê-los em uma pasta compartilhada e usá-los em todos os modelos de PDF nativo.
Para obter mais detalhes, consulte [Modelo de PDF](../native-pdf/pdf-template.md).

## Aprimoramentos no Editor da Web

Os seguintes aprimoramentos do Editor da Web foram feitos na versão de novembro de 2023:


### Visualizar arquivos por título ou nome de arquivo

Agora você pode escolher a maneira padrão de exibir os arquivos no Editor da Web. Você pode visualizar a lista de arquivos por títulos ou nomes de arquivo dos vários painéis na visualização Autor.

![Caixa de diálogo Preferências do Usuário](assets/user-preferences-2311.png){width="550" align="left"}

*Altere a maneira padrão de exibir os arquivos na caixa de diálogo **Preferências do Usuário**.*


### Gerenciar predefinições de condição

Você pode definir atributos de condição em seus tópicos DITA. Em seguida, use os atributos de condição na predefinição de condição para publicar o conteúdo em um mapa DITA. O Experience Manager Guides agora também permite criar e gerenciar predefinições de condição no Editor da Web. Também é possível editá-los, duplicá-los ou excluí-los facilmente.

![Predefinições de condição da guia Gerenciar do editor da Web ](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

Para obter mais detalhes, consulte [Usar predefinições de condição](../user-guide/generate-output-use-condition-presets.md).

### Restaurar guias de arquivo ao atualizar o navegador

O Experience Manager Guides restaura o estado das guias de arquivo abertas no Editor da Web quando você atualiza o navegador. Para obter mais detalhes, exiba a seção **Atualizar navegador ao editar os arquivos** em [Editar tópicos no Editor da Web](../user-guide/web-editor-edit-topics.md).

### Decodificar um elemento facilmente

Agora é possível decodificar facilmente um elemento usando a opção do menu de contexto de um elemento no Editor da Web. Isso ajuda a mesclar facilmente o texto do elemento com seu elemento principal.
Para obter mais detalhes, exiba a seção **Decodificar um elemento** dos [outros recursos no Editor da Web](../user-guide/web-editor-other-features.md).

### Atalhos de teclado para mover o cursor

O Experience Manager Guides agora também permite usar atalhos de teclado para mover o cursor no Editor da Web. Você pode usar os atalhos de teclado para mover rapidamente uma palavra para a esquerda ou direita. Também é possível mover para o início ou o fim da linha com a ajuda de atalhos de teclado.
Agora, você também pode usar atalhos de teclado para mover o cursor para o início do próximo elemento ou para o fim do elemento anterior.
Saiba mais sobre os [atalhos de teclado no Editor da Web](../user-guide/web-editor-keyboard-shortcuts.md).
