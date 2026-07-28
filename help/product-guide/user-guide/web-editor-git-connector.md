---
title: Visão geral do Conector Git no Experience Manager Guides
description: Saiba o que o Conector Git no Experience Manager Guides faz, seus principais recursos e como o conteúdo se move de um repositório Git para o fluxo de trabalho do AEM Guides.
feature: Authoring, Features of Web Editor
role: User
TQID: https://experienceleague.adobe.com/DDAXW8cUFjvHUeJIbtL6FaHYSU7NW5fkzTai-7n90ms
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: eb30be6342a50ba52e8afd8b4a31148b3ad9c340
workflow-type: tm+mt
source-wordcount: 1352
ht-degree: 0%

---

# Importar conteúdo usando o conector Git

>[!NOTE]
>
> Esse recurso está desativado por padrão. Para ativá-lo em seu ambiente, entre em contato com a equipe de sucesso do cliente.

O Conector Git permite [importar conteúdo de repositórios Git conectados para o Experience Manager Guides](#import-content-from-the-connected-git-repository). Depois que o conteúdo for importado, você poderá usar os recursos de criação, revisão, tradução e publicação do Experience Manager Guides para desenvolver e entregar a documentação.

Quando o conteúdo é alterado no repositório de origem, você pode buscar novamente as atualizações, revisar os conflitos e sincronizar as alterações mais recentes com o Experience Manager Guides.

## Principais recursos

O Conector Git permite que os autores extraiam conteúdo diretamente de um repositório Git para o Experience Manager Guides, sem transferências manuais de arquivos. Após a configuração, os autores têm acesso aos seguintes recursos.

**Assimilação de conteúdo**

- Sincroniza arquivos de qualquer repositório Git (público ou privado) no Experience Manager Guides.
- Filtra por caminho da pasta de origem para assimilar um único subdiretório em vez de um repositório inteiro.
- Usa um mecanismo de regra `gitignore-aware` para ignorar automaticamente os arquivos excluídos por `.gitignore` padrões ou regras personalizadas.
- Preserva os GUIDs na ressincronização para manter as referências cruzadas DITA existentes intactas após uma atualização.

**Sincronização incremental (delta)**

- Rastreia a última confirmação sincronizada e busca somente os arquivos que foram adicionados, modificados ou excluídos em sincronizações subsequentes, em vez de reimportar todo o repositório.
- Produz um relatório delta listando cada arquivo alterado e seu tipo de alteração antes da importação.
- Mantém tempos de busca consistentes, independentemente do tamanho do repositório. Para obter dados de benchmark, consulte [Benchmarks de desempenho](#performance-benchmarks).

## Como o Conector Git funciona

O diagrama a seguir mostra como o Conector Git move o conteúdo de um repositório de origem para o Experience Manager Guides.

![](./images/git-connector-arch.png)

O Conector Git move o conteúdo de um repositório Git para o Experience Manager Guides em quatro estágios:

1. **Rastrear e sincronizar**: um rastreador se conecta ao seu perfil e repositório Git configurados e sincroniza o conteúdo no conector sob demanda.
1. **Assimilar e detectar conflitos**: os arquivos de entrada são verificados e submetidos a hash em relação ao que já está no Experience Manager Guides. Os arquivos sem alterações conflitantes são movidos automaticamente; os arquivos com alterações conflitantes são sinalizados para resolução manual.
1. **Persistir**: o conteúdo resolvido é processado e salvo no AEM, junto com seu outro conteúdo do Experience Manager Guides.
1. **Fluxo de trabalho do Experience Manager Guides**: depois de mantido, o conteúdo fica disponível como qualquer outro conteúdo do Experience Manager Guides para criação, revisão, tradução e publicação.

## Benchmarks de desempenho

Os benchmarks a seguir mostram os tempos de sincronização completos (não incrementais) do **Importador em massa** no Experience Manager as a Cloud Service, aumentando a escala do repositório.

| Escala | Tempo de busca | Tempo de importação | Tempo total | Lotes | Taxa de transferência |
|---|---|---|---|---|---|
| 1.000 arquivos | 1 m 53 s | 3m 30s | 5m29s | 10 × 100 | ~286 arquivos/min |
| 5.000 arquivos | 1 m 55 s | 18m21s | 20m27s | 20 × 250 | ~273 arquivos/min |
| 10.000 arquivos | 1m 39s | 36m22 | 37m24s | 40 × 250 | ~267 arquivos/min |
| 50.000 arquivos | 1m25s | 2h43m | 2h 58m | 200 × 250 | ~270 arquivos/min |

## Importar conteúdo usando o Conector Git

Depois que o administrador configurar o Conector Git no Experience Manager Guides, você poderá usá-lo no Editor para importar conteúdo de um repositório Git.

## Pré-requisitos

Antes de começar a usar esse recurso, verifique se:

- O recurso Conector Git deve estar habilitado para o seu ambiente.
- (*Se habilitado*) o administrador configurou o Conector Git no seu ambiente. Para obter detalhes, consulte [Criar e configurar o Conector Git na interface do usuário](../install-conf-guide/conf-git-connector.md).
- Você tem acesso de *Leitura* ao repositório Git que contém o conteúdo que deseja importar.
- Você sabe qual ramificação de repositório e pasta de origem deseja importar.
- Você sabe a pasta de destino no Experience Manager Guides onde o conteúdo importado será armazenado.

## Importar conteúdo do repositório Git conectado

Execute as seguintes etapas para importar conteúdo de um repositório Git:

1. No Editor, abra o painel esquerdo.
1. Selecione **Fontes de dados**.

   As fontes de dados conectadas são exibidas.

1. Selecione o bloco **Conector Git**.

1. Selecione o ícone + e selecione **Importador em massa**.

   A caixa de diálogo **Importador em massa** é exibida.

   ![](images/git-bulk-importer-dialog.png)

1. Na caixa de diálogo **Importador em massa**, forneça um nome para a importação, selecione uma subpasta do repositório Git configurado e selecione **Salvar e Buscar**.  A lista de arquivos disponíveis para importação é exibida no diálogo. Revise a lista e valide o conteúdo antes de continuar.

   ![](images/git-bulk-importer-import-all.png)

1. Depois de revisar os arquivos, selecione **Importar tudo** para importar o conteúdo para o Experience Manager Guides.

   >[!NOTE]
   >
   > Você pode habilitar a **Sincronização automática** para sincronizar e importar automaticamente o conteúdo do seu repositório Git para o Experience Manager Guides. Se algum erro for detectado, a Sincronização Automática não será acionada e o Autor deverá importar o conteúdo manualmente selecionando **Importar tudo**. Depois de habilitada, a Sincronização automática não pode ser desabilitada para o importador.

Depois que o conteúdo é importado, ele é armazenado no **caminho raiz do AEM de destino** configurado ao configurar o Conector Git.

## Gerenciar conteúdo importado do Git

Depois que o conteúdo for importado para o Experience Manager Guides, você poderá usar as ações disponíveis para gerenciar o conteúdo e mantê-lo sincronizado com as alterações no repositório de origem.

![](images/git-connector-imported-content-options.png){width="600"}

- **Visualizar**: visualizar conteúdo importado. Se o repositório de origem tiver atualizações, revise as diferenças e use a opção **Rebuscar** para importar as alterações mais recentes. Se as diferenças exigirem mesclagem, exiba [Resolver conflitos do Conector Git](#review-and-resolve-content-conflicts).
- **Excluir**: remova o importador que não é mais necessário.
- **Renomear**: renomeie o importador para facilitar a identificação.
- **Exibir log**: exiba o log de importação para examinar os detalhes da operação de importação.
- **Exibir Relatório**: exiba e baixe o **Relatório de importação em massa**, que inclui detalhes como:

  - número total de arquivos importados
  - número de importações com êxito
  - número de importações com falha

  ![](images/git-connector-view-report.png){width="600"}

  Você também pode baixar o relatório detalhado. Se não for possível importar alguns arquivos, use **Repetir importações com falha** para tentar importá-los novamente.

## Revisar e resolver conflitos de conteúdo

Ao buscar novamente o conteúdo de um repositório Git, as diferenças no conteúdo entre a versão do repositório e o conteúdo correspondente disponível no Experience Manager Guides são exibidas como conflitos. Você deve resolver e mesclar esses conflitos antes de importar os dados para o Experience Manager Guides.

Execute as seguintes etapas para resolver e mesclar conflitos:

1. Abra a caixa de diálogo Importador em massa e selecione **Rebuscar**.
1. Se forem detectados conflitos, a guia **Mesclagem necessária** será exibida e listará os arquivos que contêm conflitos. Selecione a guia **Mesclagem necessária** e selecione um arquivo da lista para examinar e resolver os conflitos.
1. Para arquivos com conflitos, é exibida uma visualização de mesclagem de três vias.

   ![](images/git-connector-resolve-conflicts.png)

   O painel esquerdo (**AEM**) exibe o conteúdo atual do repositório do AEM, enquanto o painel direito (**GIT**) mostra o conteúdo de entrada do repositório Git remoto. O painel do meio (**Result**) é preenchido inicialmente com o conteúdo do repositório do AEM e serve como editor de mesclagem, onde os conflitos são resolvidos. O resultado mesclado final é produzido e exibido nesse painel do meio.

1. Revise as diferenças destacadas no editor e resolva os conflitos usando os controles de mesclagem:

   - Se quiser usar as alterações mais recentes do repositório Git, verifique se a caixa de seleção do conflito na seção **GIT** está marcada e selecione o controle `<<<` correspondente. O conteúdo Git selecionado substitui o conteúdo conflitante na seção **Resultado**.

     ![](images/git-connector-replace-with-git.png)

   - Se quiser manter o conteúdo de ambas as versões, desmarque a caixa de seleção para o conflito e use o controle `<<<` para adicionar o conteúdo necessário à seção **Resultado** sem substituir o conteúdo existente.

     ![](images/git-connector-keep-both-versions.png)

   - Da mesma forma, você pode usar o controle `>>>` na seção AEM para manter a versão disponível no momento no Experience Manager Guides.


1. Depois de revisar o conteúdo mesclado, execute uma das seguintes ações:

   - Use **Aceitar AEM** para substituir o conteúdo da seção **Resultado** inteiramente pela versão da seção **AEM**, mantendo suas alterações locais.
   - Use **Aceitar GIT** para substituir o conteúdo da seção **Resultado** inteiramente pela versão da seção **GIT**, mantendo as alterações do repositório.

**A mesclagem completa** é necessária, independentemente da opção usada acima. Selecionar esse arquivo bloqueia o conteúdo atual de **Resultado** como a versão resolvida para esse arquivo e marca o arquivo como mesclado.

Depois que todos os arquivos contendo os conflitos forem marcados como mesclados, o botão **Importar tudo** será habilitado. Selecione **Importar tudo** para concluir o processo de resolução de conflitos.

Se um arquivo tiver sido alterado no repositório Git, mas não tiver sido modificado no Experience Manager Guides, nenhuma mesclagem será necessária. Esses arquivos são incluídos automaticamente em **Limpar atualizações** e podem ser importados diretamente.

![](images/git-connector-clean-updates.png){width="600"}