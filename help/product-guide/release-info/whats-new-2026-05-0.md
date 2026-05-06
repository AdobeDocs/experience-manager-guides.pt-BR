---
title: Notas de versão | Novidades na versão 2026.05.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2026.05.0 do Adobe Experience Manager Guides
role: Leader
source-git-commit: 3f38264b6ce09366d07cdd302c9c53e8abcf4b7c
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 0%

---

# Novidades da versão 2026.05.0 (maio de 2026)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2026.05.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2026.05.0](fixed-issues-2026-05-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.05.0](../release-info/upgrade-instructions-2026-05-0.md).

## Introdução ao Editor 2.0

O Editor 2.0 (também conhecido como Novo editor) oferece criação simplificada, permitindo que você crie conteúdo com mais eficiência nos modos de tag e não tag por meio de uma experiência mais intuitiva. A versão traz melhor desempenho, com carregamentos de página mais rápidos e edição mais suave, mesmo para tópicos grandes e complexos. Ele também oferece estabilidade aprimorada ao solucionar as principais lacunas de criação, especialmente em relação à navegação e ao comportamento do cursor. Além disso, uma interface moderna oferece uma interface do usuário atualizada e fácil de usar que equilibra a funcionalidade com a facilidade de uso. Para obter detalhes, consulte [Introdução ao Editor](../user-guide/web-editor.md).

Veja um vídeo de visão geral destacando os recursos do Editor 2.0.

>[!VIDEO](https://video.tv.adobe.com/v/3484007)


>[!NOTE]
>
> Entre em contato com a equipe de Sucesso do cliente da AEM Guides para ativar o Editor 2.0 em seu ambiente.

Veja a seguir as melhorias que tornam a criação mais fácil e eficiente.

### Interface e experiência do usuário reprojetadas

Uma interface atualizada melhora a usabilidade geral, tornando a navegação e a criação de conteúdo mais intuitivas e consistentes.

- **CSS mais avançado para elementos no modo Autor e Visualização**: o CSS padrão aprimorado para elementos fornece estilo aprimorado e melhor consistência visual em ambos os modos, de criação e de visualização.

  ![](assets/rich-css.png){width="650"}

- **Suporte para temas escuros**: o suporte para um tema escuro na área de edição de conteúdo aprimora a experiência de criação para usuários que preferem trabalhar com uma interface escura.

  ![](assets/dark-theme.png){width="650"}

- **Configurações consolidadas do Editor em nível de usuário**: um novo painel de configurações centralizado que oferece aos Autores um melhor controle sobre o comportamento do editor, permitindo que os usuários gerenciem preferências com mais facilidade a partir de um único local. As opções de configuração incluem, capacidade de ativar/desativar:

   - Espaços ininterruptos no modo Autor
   - Configurações de visibilidade de tag com ou sem atributos
   - Comentários XML no modo Autor
   - Menu de inserção rápida para inserção de elemento no editor

  ![](assets/editor-settings-dialog.png){width="350"}


  Para obter mais informações sobre como definir as configurações do Editor, consulte [Configurações do Editor](../user-guide/config-editor-settings.md).

- **Melhor representação do conteúdo condicional no modo Autor**: o conteúdo condicional é exibido com mais clareza no modo Autor, ajudando os autores a identificar e gerenciar variações com mais eficiência. Para obter detalhes, consulte [Condições](../user-guide/web-editor-left-panel.md#conditions) no painel esquerdo do Editor.

  ![](assets/multiple-conditions-applied_cs-editor-2-0.png){width="650"}

### Recursos de criação aprimorados

Fornece ferramentas aprimoradas e flexibilidade para simplificar a criação e edição de conteúdo nos fluxos de trabalho.

- **Exibir atributos junto com elementos no modo de marca**: os autores agora podem exibir atributos de elemento com o modo de marca, oferecendo melhor visibilidade e controle sobre o conteúdo estruturado. Para configurar este recurso, exiba [Configurações do editor](../user-guide/config-editor-settings.md).

  ![](assets/config-tags-attributes.png){width="650"}

- **Menu de inserção rápida**: permite adicionar elementos diretamente ao editar no modo Autor, na posição do cursor, sem navegar até a barra de ferramentas. Os elementos usados com frequência também podem ser configurados na seção Favoritos por meio das configurações do Editor para agilizar o acesso. Para obter detalhes, exiba [Editar tópicos](../user-guide/web-editor-edit-topics.md).

  ![](assets/quick-insert-menu.png){width="650"}

- **Capacidade de exibir, editar e inserir comentários XML no modo Autor**: permite que os autores exibam, editem e insiram comentários XML diretamente no modo Autor, para melhor visibilidade do conteúdo. Para configurar este recurso, exiba [Configurações do editor](../user-guide/config-editor-settings.md).

  ![](assets/config-xml-comments.png){width="650"}

- **Modo lado a lado**: permite a exibição simultânea dos modos Autor e Source, com ambas as exibições permanecendo em perfeita sincronização para facilitar a comparação, edição e validação de alterações de conteúdo. Para obter detalhes, consulte [Exibições do editor](../user-guide/web-editor-views.md).

  ![](assets/side-by-side-editor-2-0.png){width="650"}

- **Criação de tabela aprimorada**: melhora a experiência geral de criação de tabela com interações mais intuitivas e eficientes para criar e gerenciar tabelas.

   - Interações fluidas e intuitivas: insira facilmente linhas e colunas, juntamente com suporte de arrastar e soltar para reordenar linhas e colunas.
   - Barra de ferramentas contextual: Acesse ações específicas da tabela, como formatação, alinhamento, mesclagem e outras ações adicionais diretamente na tabela.
   - Configuração de tabelas: adicione várias linhas ou colunas em uma única ação, reduzindo etapas repetitivas e melhorando a eficiência.

  ![](assets/config-table.png){width="650"}

  Para obter detalhes, exiba [Trabalhar com tabelas](../user-guide/web-editor-other-features.md#work-with-tables-in-the-new-editor).

### Desempenho aprimorado para tópicos grandes

O novo editor aprimora a experiência de trabalhar com tópicos grandes e complexos fornecendo renderização mais rápida do conteúdo, funcionalidade de desfazer e refazer mais confiável e um marcador sujo para indicar claramente as alterações não salvas.

## Acesse o Caminho e a UUID das referências nos arquivos a partir do painel Propriedades de conteúdo

Agora você pode usar o **Caminho do link** para exibir o caminho relativo da referência selecionada e o **UUID do link** para exibir seu identificador exclusivo no painel Propriedades de conteúdo. Também é possível copiar o caminho absoluto completo e a UUID associada diretamente da interface usando os ícones ao lado de Caminho do link e UUID do link, facilitando o rastreamento e a reutilização de ativos vinculados.

Para obter detalhes, exiba [Propriedades do conteúdo](../user-guide/web-editor-right-panel.md#content-properties).

## Revisar melhorias

Os seguintes aprimoramentos de revisão foram feitos como parte desta versão:

- Agora você pode habilitar **Lembretes automatizados** para agendar notificações do AEM e lembretes de email para revisores, antes da data de vencimento de uma tarefa de revisão e depois dela se tornar vencida. Você pode configurar vários lembretes em cada caso, com lembretes de atraso enviados em uma sequência definida e lembretes de atraso acionados depois que a tarefa é marcada como vencida, com base no agendamento de lembrete configurado. Para obter detalhes sobre como configurar os lembretes para tarefas de revisão, exiba [Enviar um ou mais tópicos para revisão](../user-guide/review-send-topics-for-review.md#send-one-or-more-topics-for-review).

- Os revisores agora podem acessar o Histórico de versão para tópicos em revisão, permitindo visualizar e comparar versões revisadas e atualizadas anteriormente do mesmo tópico em tarefas de revisão anteriores. Isso ajuda os revisores a validar as alterações feitas desde ciclos de revisão anteriores e manter a continuidade, revisando comentários, rótulos e outros detalhes relacionados no contexto de revisão atual. Para obter detalhes, exiba o [Histórico de versões do Revisor](../user-guide/review-topics.md#version-history-for-the-reviewer).

## Nova experiência de linha de base introduzida no Experience Manager Guides

>[!NOTE]
>
> Entre em contato com a equipe de Sucesso do cliente da AEM Guides para ativar a Nova linha de base em seu ambiente.

O gerenciamento de linhas de base grandes e complexas agora é mais rápido, estável e fácil de dimensionar com a **nova experiência de linha de base**, criada em uma arquitetura de linha de base reprojetada. Essa atualização soluciona desafios de desempenho e confiabilidade duradouros, preservando os fluxos de trabalho existentes.

Disponível como um aprimoramento beta, essa atualização fornece solução para pontos problemáticos comuns, como carregamento lento, estados de linha de base inconsistentes e capacidade de gerenciamento limitada, fornecendo uma experiência de linha de base mais rápida, estável e previsível, com suporte adicional para operações de automação e linha de base em grande escala. As principais melhorias são:

- Desempenho e escalabilidade aprimorados
- Interface de usuário e consistência de back-end mais fortes
- Visibilidade de filtragem, navegação e dependência ampliada

Para obter detalhes, exiba [Nova experiência de linha de base (Beta) no Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).






