---
title: Criar e gerenciar uma nova linha de base (Beta) no console Mapa
description: Crie e gerencie uma nova linha de base (Beta) no console de mapa no Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: d5d1d66daaecb0e573f12abe0ddeef173038739b
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 0%

---

# Nova linha de base (Beta) no Experience Manager Guides

>[!NOTE]
>
> Este artigo se aplica à nova linha de base, atualmente disponível como um recurso do *Beta*, que oferece melhor desempenho e estabilidade disponíveis na versão Experience Manager Guides 2026.03.0. Para habilitar o novo recurso de linha de base em sua configuração, entre em contato com a Equipe de sucesso do cliente.

O novo recurso básico trata dos problemas críticos de confiabilidade e desempenho associados a mapas grandes e complexos. Ela vem com uma arquitetura de linha de base reprojetada que oferece uma experiência de linha de base mais rápida, estável e consistente.

O novo modelo de linha de base fortalece o manuseio da linha de base ao abordar os pontos problemáticos comuns:

- Carregamento lento e resposta ruim ao trabalhar com linhas de base grandes
- Estados de linha de base inconsistentes causados por atualizações parciais ou validações com falha
- Visibilidade e controle limitados ao gerenciar conteúdo básico abrangente
- Gargalos de desempenho durante a criação, atualizações ou recriações da linha de base

As seções a seguir descrevem o novo modelo de linha de base, incluindo as melhorias introduzidas, as principais alterações de comportamento a serem consideradas antes da migração e as instruções para migrar para a nova linha de base e usá-la:

- [Principais melhorias introduzidas na nova linha de base](#key-enhancements-introduced-in-the-new-baseline)
- [Alterações de comportamento a serem conhecidas antes de migrar para a nova linha de base](#behavior-changes-to-know-before-migrating-to-the-new-baseline)
- [Migrar para a nova linha de base](#migrate-to-new-baseline)
- [Usar a nova linha de base](#use-the-new-baseline)

## Principais melhorias introduzidas na nova linha de base

A nova linha de base apresenta melhorias significativas que tornam o gerenciamento mais rápido e fácil de dimensionar sem alterar a forma como você trabalha. Considere mudar para a nova linha de base para:

- **Desempenho e escalabilidade aprimorados:** O modelo de dados de linha de base e o comportamento de renderização foram otimizados para serem escalonados com eficiência com linhas de base grandes, usando carregamento incremental e uma estrutura de dados simplificada para melhorar a capacidade de resposta.
- **Interface do usuário mais forte e consistência de back-end:** Quaisquer alterações feitas em uma linha de base (como atualizações de versão ou dependência) agora serão refletidas na interface do usuário somente após a validação bem-sucedida do back-end, impedindo a criação de linhas de base inválidas.
- **Filtragem, classificação e navegação:** As linhas de base oferecem suporte à filtragem abrangente em vários atributos, incluindo estado do documento, rótulos, tipo de arquivo, tipo de referência e pesquisa baseada em GUID em toda a linha de base. A paginação é compatível com linhas de base grandes, com uma opção para incluir arquivos que não têm rótulos.
- **Visibilidade clara do impacto da dependência:** O impacto da dependência (para dependências adicionadas ou removidas) é exibido como uma visualização antes da aplicação das alterações de versão, permitindo que você revise as alterações antes de aplicá-las.
- **Gerenciamento mais flexível de rótulos:** os rótulos podem ser movidos entre versões em uma linha de base, proporcionando maior flexibilidade ao gerenciar rótulos em diferentes versões de tópico.
- **Comportamento determinístico de edição e salvamento:** as edições de linha de base oferecem suporte a atualizações em nível de linha, carregam dados com muitos recursos (como árvores de versão e diferenças de dependência) somente durante atualizações de versão e concluem as operações de salvamento de forma determinante em uma única etapa - reduzindo falhas inesperadas de salvamento e atualizações parciais.
- **Criação de linha de base mais confiável:** linhas de base são criadas usando dados de referência armazenados em vez de análise em tempo de execução, com informações de versão necessárias validadas antecipadamente para evitar linhas de base incompletas ou inválidas.
- **Suporte a API e automação:** O novo modelo de linha de base é totalmente suportado por meio das APIs REST e do Java SDK, permitindo automação e integração com fluxos de trabalho externos.


## Alterações de comportamento a serem conhecidas antes de migrar para a nova linha de base

Antes de migrar para o novo modelo de linha de base, analise as alterações de comportamento a seguir. Essas alterações afetam como as linhas de base são criadas, atualizadas e gerenciadas, e podem influenciar os workflows existentes.

| Área | Alteração (descrição) |
|------|-------------|
| **Resolução de referência** | As referências de mapa direto são classificadas como **DIRECT**. Referências inválidas são ignoradas, e as referências de `reltable` continuam a ser excluídas. |
| **Escolher Automaticamente** | A seleção da versão é avaliada imediatamente antes da resolução de referências diretas, garantindo uma resolução de versão precisa. |
| **Regras de criação da linha de base** | A versão **1.0** é obrigatória. Linhas de base com versões ausentes ou ambíguas podem resolver de forma diferente após a migração. |
| **Manipulação de migração** | Referências inválidas são ignoradas. As referências **DIRECT** têm prioridade, as referências desafixadas são movidas para a versão mais recente e metadados adicionais são adicionados a partir da versão **5.0**. |
| **Modelo de dados de linha de base** | O novo modelo de linha de base baseado em gráfico remove campos mutáveis e não é compatível com o modelo de linha de base anterior. |
| **Uso da API** | As operações de linha de base são suportadas por meio das APIs REST e do Java SDK. Os objetos de linha de base bruta não são mais expostos. |
| **Limpeza de versão** | Após a migração, a limpeza de versão considera somente as linhas de base armazenadas no novo repositório de linhas de base. |

## Migrar para nova linha de base

Depois de habilitar o recurso da Equipe de sucesso do cliente, é necessário migrar as linhas de base existentes para a nova linha de base.

Execute as etapas a seguir para migrar a linha de base existente para a nova.

1. Selecione o logotipo do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. No painel **Ferramentas**, selecione **Guias**.
1. Selecione o bloco **Processador em Massa**.

   ![processador-ativo-fluxo](images/flow-asset-processor.png){align="left"}

   A página **Processador de Lote de Guias** é exibida.

1. Selecione **Novo Processo** no canto superior direito da página para iniciar uma nova tarefa de processamento.

   A caixa de diálogo **Novo processo** é exibida.

1. Forneça os seguintes detalhes na caixa de diálogo:

   1. **Tipo de recurso**: selecione **Linha de Base** na lista suspensa.
   1. **Selecionar pasta(s) e arquivo(s)**: navegue e escolha uma ou várias pastas e arquivos para processar.
   1. **Selecione as pastas a serem ignoradas**: como opção, selecione as subpastas dentro da pasta pai escolhida para excluir da migração.

   ![nova-linha-de-base-de-processo](images/new-process-baseline.png){align="left"}

1. Selecione **Criar**.

Um pop-up mostrando **o processamento de ativos foi acionado com êxito** é exibido. Você pode visualizar o status da tarefa de processamento na página.

Você também pode selecionar **Exibir logs** para verificar e baixar os logs da tarefa de migração.

![view-logs-baseline](images/view-logs-baseline.png){align="left"}

O relatório de log fornece detalhes da migração, incluindo o número de mapas migrados, linhas de base migradas com êxito e detalhes relacionados.

![logs-detail-baseline](images/logs-detail-baseline.png){align="left"}

>[!NOTE]
>
> Nenhuma edição de linha de base deve ser feita durante a migração, especialmente em cópias de trabalho, para evitar falhas. Após a migração, algumas linhas de base podem exigir reconstrução se as versões estiverem ausentes.

## Usar a nova linha de base

O novo modelo de linha de base usa os mesmos workflows e interface do usuário que o recurso de linha de base existente no Experience Manager Guides. Você pode continuar a [Criar e gerenciar linha de base do Console de mapa](./web-editor-baseline.md) usando as opções disponíveis.

>[!NOTE]
>
> O novo modelo de linha de base não oferece suporte à criação e ao gerenciamento de linhas de base no painel Mapa.

Esta seção descreve apenas as alterações e as melhorias introduzidas no novo modelo de linha de base. Os workflows de linha de base comuns permanecem inalterados, a menos que sejam explicitamente mencionados.

**Opções novas/aprimoradas disponíveis na nova interface de linha de base**

As seguintes atualizações se aplicam ao trabalhar com linhas de base criadas usando o **novo modelo de linha de base**:

- A opção **Exportar linha de base** do menu Opções foi renomeada para **Download** para linhas de base criadas com atualizações Manuais e Automáticas.

  ![](images/baseline-v2-options-menu.png)

- As linhas de base dinâmicas podem ser abertas diretamente do painel **Linha de Base** e gerenciadas usando as ações disponíveis no menu Opções.

  ![](images/baseline-v2-dynamic-baseline-new.png)

  Você também pode usar as novas opções introduzidas para linhas de base dinâmicas criadas usando o novo modelo de linha de base:
   - **Editar propriedades**: permite editar as propriedades de uma linha de base existente.
   - **Recompilar**: permite que você recompile uma linha de base dinâmica sempre que ocorrerem alterações.

     ![recompilar-linha-de-base](images/rebuild-baseline.png){align="left"}

- A ação **Download** dá suporte a downloads paginados. Todo o conteúdo de linha de base que corresponde aos filtros aplicados é incluído no download, não apenas o conteúdo visível na página atual.
- Filtre arquivos por GUID, além dos nomes ou do local dos arquivos. Uma opção adicional para **Filtrar arquivos sem rótulos** também está disponível.

  ![](images/baseline-v2-filters.png)
- O novo modelo de linha de base oferece suporte à edição determinística, permitindo atualizar uma referência de cada vez com resolução de dependência validada.

  +++Etapas para editar as referências de uma nova linha de base

  Execute as seguintes etapas para fazer edições em uma linha de base:

   - Abra a linha de base no painel **Linha de Base**.

     A exibição em tabelas das referências das linhas de base é exibida.

   - Navegue até o arquivo que deseja editar e passe o mouse sobre ele.
   - Selecione o ícone **Editar**.

     ![ícone-da-linha-de-base](images/edit-baseline-icon.png){align="left"}

     A caixa de diálogo **Editar versão** é exibida.
   - Selecione a versão necessária na lista suspensa **Versão** (por exemplo, altere da versão 1.0 para 1.1).


     ![edit-version-baseline](images/edit-version-baseline.png){align="left"}

     As dependências adicionadas e removidas são avaliadas e exibidas como pré-visualização. Revise as alterações antes de aplicá-las.

     ![](images/baseline-v2-version-added.png)

     Se nenhuma alteração de dependência for detectada, uma mensagem de estado vazio será exibida.

   - Selecione **Atualizar** para aplicar as alterações.

  A linha de base é atualizada com a versão selecionada.
+++
