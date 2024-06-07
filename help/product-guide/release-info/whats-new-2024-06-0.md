---
title: Notas de versão | Novidades nos Guias da Adobe Experience Manager, versão 2024.06.0
description: Saiba mais sobre os recursos novos e aprimorados da versão 2024.06.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: cf60d11f483fdd663bd5decccb63f8ed7d6fff51
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 0%

---

# Novidades da versão 2024.06.0

Este artigo aborda os recursos novos e aprimorados da versão 2024.06.0 dos Guias do Adobe Experience Manager.

Para obter a lista de problemas corrigidos nessa versão, consulte [Correção de problemas na versão 2024.06.0](fixed-issues-2024-06-0.md).

Saiba mais sobre [instruções de atualização da versão 2024.06.0](upgrade-instructions-2024-06-0.md).


## Publicar um tópico ou seus elementos em um fragmento de experiência

Um Fragmento de experiência é uma unidade de conteúdo modular no Adobe Experience Manager que integra conteúdo e layout. Fragmentos de experiência são fundamentais para criar experiências consistentes e envolventes, que podem ser reutilizadas em vários canais.


Os Guias do Experience Manager agora permitem publicar um tópico ou seus elementos em um Fragmento de experiência. Você pode criar um mapeamento baseado em JSON entre um tópico e seus elementos em um Fragmento de experiência. Por exemplo, você pode criar fragmentos de experiência para cabeçalhos ou rodapés com elementos de marca, banners promocionais, depoimentos de clientes e promoções de eventos.




Para obter mais detalhes, consulte [Publicar fragmentos de experiência](../user-guide/publish-experience-fragment.md).


## Melhorias na publicação do fragmento de conteúdo

Os Guias de Experience Manager também fornecem algumas melhorias úteis nos Fragmentos de conteúdo:

- Você pode filtrar facilmente o conteúdo com condições ao publicar em um fragmento de conteúdo, usando um arquivo DITAVAL ou atributos condicionais.

- Também é possível publicar e exibir os Fragmentos de conteúdo de um tópico do **Saídas** na seção **Propriedades do arquivo**.

![guia opções de propriedades do arquivo](./assets/file-properties-outputs-tab.png){width="300" align="left"}

Para obter mais detalhes, consulte [Publicar fragmentos de conteúdo](../user-guide/publish-content-fragment.md).


## Capacidade de transmitir metadados das propriedades do arquivo de tópico para a saída do PDF nativo

Agora, o Experience Manager Guides permite adicionar os metadados das propriedades de um arquivo de tópico aos layouts de página ao gerar a saída de PDF nativo. Use esse recurso para adicionar metadados específicos do tópico, como título, tags e descrição aos layouts de página. Você também pode personalizar o PDF publicado com base nos metadados do tópico, como adicionar uma marca d&#39;água ao plano de fundo do tópico com base no estado do documento do tópico.

![adicionar pdf nativo de metadados](./assets/add-metadata-native-pdf.png) {width="300" align="left"}

*Adicione metadados aos campos nos layouts de página.*

Saiba como [adicionar campos e metadados](../native-pdf/design-page-layout.md#add-fields-metadata) em um layout de página.

## Selecionar conteúdo parcial entre elementos para operações

O Experience Manager Guides aprimora sua experiência de seleção do conteúdo nos elementos no Editor da Web. É possível selecionar facilmente o conteúdo em diferentes elementos e executar operações, como negrito, itálico e sublinhado. Esse recurso permite aplicar ou remover facilmente a formatação do conteúdo parcialmente selecionado. Você também pode excluir rapidamente o conteúdo selecionado entre os elementos. Depois que o conteúdo for excluído, se necessário, o conteúdo restante será mesclado automaticamente em um único elemento válido.

Você também pode selecionar um conteúdo parcial entre elementos e cercá-lo com um elemento DITA válido.
![caixa de diálogo surround element](./assets/surround-element.png) {width="300" align="left"}

*Marque o conteúdo selecionado com um elemento válido.*

Em geral, esses aprimoramentos fornecem uma experiência melhor e ajudam a melhorar a eficiência na edição de documentos.

Para obter mais detalhes, consulte [Seleção parcial de conteúdo ao longo do elemento](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).

## Suporte para documentos do Markdown na publicação de PDF nativo

Os Guias de Experience Manager também são compatíveis com documentos do Markdown na publicação de PDF nativo. Esse recurso é útil e ajuda a gerar PDF para os arquivos do Markdown no mapa DITA. O suporte ao Markdown na publicação de PDF nativo ajuda você a criar, gerenciar e compartilhar facilmente seus documentos.

Para obter mais detalhes, consulte [suporte para documentos do Markdown](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


## Desempenho e escalabilidade aprimorados para grandes projetos de tradução

O recurso de tradução é mais rápido e escalável do que nunca. Ele vem com uma nova arquitetura que oferece desempenho aprimorado. O tempo de criação do projeto agora é mais rápido do que antes, e os conflitos durante o processo são quase inexistentes. Esse desempenho aprimorado ajuda com traduções mais rápidas, garantindo uma operação tranquila mesmo para projetos de tradução grandes.

Essa melhoria é muito benéfica, pois melhora a produtividade e a experiência geral.

Saiba como [traduzir documentos a partir do Editor da Web](../user-guide/translate-documents-web-editor.md).
