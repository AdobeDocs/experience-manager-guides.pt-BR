---
title: Notas de versão para Adobe Experience Manager Guides 3.8 e 3.8.5
description: Principais novos recursos e aprimoramentos nas versões 3.8 e 3.8.5 do Adobe Experience Manager Guides (anteriormente conhecido como solução da XML Documentation).
source-git-commit: ff3d35832b80f6221f1261498934ab74261b282b
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 0%

---


# Notas de versão | Adobe Experience Manager Guides 3.8

**Isenção de responsabilidade**:

A *Adobe Experience Manager Guides* era anteriormente conhecida como *XML Documentation para Adobe Experience Manager*. Observe que algumas referências contidas na documentação ainda podem se referir a marcas anteriores, mas ainda se aplicam à oferta atual.

Estas notas de versão listam os novos recursos e aprimoramentos principais da versão 3.8.x do XML Documentation para Adobe Experience Manager.

## Novos recursos e melhorias na versão 3.8.5

### Correções de erros

Os bugs corrigidos na versão 3.8.5 estão listados abaixo:

- Falta o suporte de linha de base para a saída do PDF por meio do FrameMaker Publishing Server.
- A API de check-out e check-in do FrameMaker ou Oxygen não está funcionando corretamente se as permissões no nível da pasta tiverem sido configuradas para vários grupos no AEM.
- A visualização do conteúdo não é exibida na página da interface do usuário do Assets.
- O botão &quot;Source&quot; não está funcionando na página da interface do usuário do Assets.
- Quando uma imagem é inserida por meio do recurso Inserir imagem do Editor da Web, o caminho relativo da imagem inserida muda para seu caminho absoluto.
- A lista suspensa de predefinições FMPS não é exibida na interface do usuário com a versão mais recente 3.8.
- O painel Favoritos não é exibido quando contém um grande número de ativos no DAM e um novo item favorito é adicionado do Editor da Web XML.
- Redirecionamento interno *sling:mapping* que redireciona todos os links não está funcionando e exibe URLs longas (com caminhos internos) em vez de URLs curtas para as páginas da Web.
- Na Exibição em lista, a coluna Modificado exibe &quot;Usuário externo&quot; em vez do nome de usuário quando os ativos são carregados ou importados da página da interface do usuário do Assets (exceto por meio do Gerenciador de pacotes).
- O título não é exibido corretamente na guia Tópicos no Painel do mapa.
- Ao ativar o recurso de nivelamento de nó, alguns caracteres inválidos são armazenados na saída do HTML.
- As alterações no perfil de pasta nas preferências do usuário não são recarregadas automaticamente para um arquivo já aberto, mas o navegador precisa ser atualizado.
- A saída gerada por meio da opção Mapa de download tem alguns tópicos ausentes se houver alguns erros de validação.

## Novos recursos e melhorias na versão 3.8

### Atualizações de configuração de nomenclatura de arquivo

Ao criar tópicos DITA na solução XML Documentation, os usuários podem usar caracteres especiais como parte dos nomes de arquivo. Isso resultou em URLs codificados na geração de páginas de site do AEM. Para evitar essa conversão em URL, a versão 3.8 das soluções da XML Documentation permite que um administrador defina uma lista de caracteres especiais diferentes das configurações de nome de arquivo válido padrão (a-z A-Z 0-9 - _). Isso implica que, embora você possa configurar uma lista de caracteres especiais em um nome de arquivo incluindo um espaço, ela será substituída por um hífen (-).

### Alterações na geração do nome da página do site do AEM

Durante a criação, é possível ter o mesmo nome de arquivo para um ou mais arquivos em pastas diferentes. Durante o processo de publicação do site do AEM, os nomes de página eram anexados com um sufixo quando havia pelo menos um nome de arquivo duplicado. Com a versão 3.8 da solução XML Documentation, o processo de geração de nome de página do site do AEM foi corrigido. O sufixo é anexado ao nome de página gerado somente se houver um nome de arquivo duplicado.

### Novos recursos e melhorias

Foram introduzidos vários novos recursos e aprimoramentos nas seguintes áreas do produto.

#### Editor da Web

- Agora é possível escolher um rótulo em uma lista suspensa ao criar uma versão de um tópico no Editor da Web.

  ![Rótulos em uma lista suspensa](assets/labels-drop-down-saving-topic-res.avif)

- O painel Revisão no Editor da Web agora ficou mais eficiente, com a capacidade de reverter um tópico para uma versão que foi compartilhada para revisão. É possível incorporar facilmente comentários de revisão na versão revisada, sem precisar lembrar qual versão do tópico foi compartilhada para revisão.

  ![Reverter tópico para versão de revisão](assets/revert-review-topic.avif)

- Uma nova dica visual foi introduzida para indicar se você está trabalhando na versão mais recente de um tópico ou em uma versão anterior.

  ![Indicação de versão](assets/old-version-icon.avif)

- Um novo recurso Histórico de versão foi introduzido nesta versão. Use o recurso Histórico de versão para:
   - Exibir uma lista de todas as versões do tópico ativo no momento, juntamente com rótulos adicionados para cada versão.
   - Reverter para uma versão anterior do tópico.

  ![Histórico de Versões](assets/version-history.avif)

- Foi adicionado um novo recurso de Gerenciamento de rótulo de versão que permite aplicar rótulos às versões atuais ou anteriores de um tópico.

  ![Gerenciamento de Rótulos de Versão](assets/version-label-management.avif)

- Adição de um novo recurso: &quot;Aprovar para publicação&quot;, com o qual um autor pode marcar um ativo como aprovado e bloqueá-lo ainda mais para edição.
- Ao iniciar um processo de revisão, agora é possível filtrar tópicos com base em seu estado.

  ![Selecione tópicos de revisão com base em seu Estado](assets/review-select-topic-on-state.avif)

- O `<navtitle>` em um mapa é preenchido automaticamente com o título de um tópico adicionado ao arquivo de mapa. Você também pode atualizar o `<navtitle>` facilmente no Editor da Web.
- A visualização de uma tabela com um grande número de colunas agora é exibida na área da página.
- Você pode aplicar várias classes de saída de uma só vez no painel Propriedades (multiselect).
- Ao Visualizar um tópico, você também pode gerar uma saída PDF (incondicional) de um único tópico diretamente do Editor da Web.

  ![Saída do PDF da Visualização](assets/pdf-output-from-preview.avif)

- Bloqueie uma solicitação de publicação se a geração de saída da mesma predefinição estiver em andamento.
- Adição da capacidade de apenas um conjunto de usuários privilegiados excluir ativos que tenham referências retroativas ativas ativas.
- Adição de um recurso para exibir ou copiar o código XML da Exibição do Source na interface do usuário do Assets, mesmo que outro usuário tenha feito check-out do arquivo.

  ![modo de exibição XML do Source](assets/xml-source-view-from-assets-ui.avif)

- O nome do arquivo agora é substituído pelo título do arquivo na caixa de diálogo Salvar, no painel Conteúdo reutilizável e no painel Localizar e substituir.

#### Publicação

- **Permitir a Configuração de Regras de Limpeza para Páginas de Site Geradas**: Como administrador, você pode definir as regras de limpeza para os nomes de arquivo do Site AEM gerado ou saída DITA-OT. Sempre que você gerar uma saída ou saída de site do AEM usando o DITA-OT, poderá configurar as regras abaixo para limpar os URLs ou nomes de arquivo gerados pela saída:
   - Converter todos os caracteres em minúsculas.
   - Substituir caracteres especiais por um separador.
   - Restrinja um nome de arquivo longo a um número predefinido de caracteres.

- Envie facilmente a saída da instância do autor para a instância de publicação usando o Painel de ativação em massa. É possível trabalhar com um único mapa ou uma coleção de mapas e escolher a predefinição de saída que deseja usar para publicação.

  ![Painel de Publicação em Massa](assets/bulk-publish-dashboard.avif)

#### Melhorias de desempenho

- Nivelamento de nó para saída do AEM Sites: anteriormente, a estrutura do nó do site da saída do AEM Sites era muito profunda. Agora, você tem o controle para nivelar a estrutura do nó e melhorar o desempenho.
- Suporte para a versão mais recente do FrameMaker Publishing Server verão 2020.
- Os arquivos temporários gerados durante a tradução agora são removidos, o que melhora o processo de tradução.

#### Outras melhorias

- A dependência do fluxo de trabalho do Ativo de atualização do DAM durante o pós-processamento do conteúdo DITA foi removida. Se houver etapas de processo personalizadas definidas no fluxo de trabalho Atualizar ativo do DAM, você deverá atualizá-las para serem executadas após a conclusão do pós-processamento.
- O iniciador do processo de tradução agora recebe uma notificação em sua Caixa de entrada quando o trabalho de tradução é criado com êxito.

### Correções de erros

Os bugs corrigidos na versão 3.8 estão listados abaixo:

- Os objetos de áudio não são exibidos na saída do HTML.
- A janela Forçar Exclusão exibida ao excluir um tópico DITA mostra vários botões &quot;Forçar Exclusão&quot;.
- A transferência da linha de base para cópias de idioma não funciona para a linha de base criada usando a exibição do lado do servidor.
- Às vezes, a versão 3.0 de um tópico aparece como 3 na exibição lado a lado, não permitindo que comentários de revisão sejam importados.
- Carregamento lento de detalhes de conteúdo referenciado na guia Linhas de Base para o mapa DITA movido.
- A reversão para uma versão anterior não funciona para ativos que não são ditas.
- Muitos nós de _texto vazios estão sendo criados com a geração de saída do AEM Sites.
- Editor XML - A resolução do link em mapas de imagem após a geração da página não está funcionando.
- Aplicar rótulos da guia Linhas de base não adiciona rótulos no conteúdo referenciado como imagens.
- Os arquivos do SVG estão sendo baixados no formato incorreto por meio da opção Baixar mapa.
- Não é possível editar o fragmento de conteúdo em uma Exibição de lista.
- Não é possível fazer check-out e abrir arquivos no Oxygen XML Author usando o conector.
- O texto do elemento `<alt>` não está visível no modo de exibição Criação.
- O ativo de imagem é sempre exibido como Desatualizado mesmo quando existe uma cópia traduzida.
- O título personalizado do modelo de mapa está incorreto e a miniatura não é exibida.
- Elementos de marca aplicados não exibidos na visualização de criação do editor da Web.
- As notas de rodapé vinculadas não estão visíveis no conteúdo.
- A codificação de cores no Editor da Web não funciona com atributos condicionais especializados.
- A lista suspensa de @keyref não é amigável, considerando-a quase inutilizável para clientes com um grande número de @keyref.
- O texto da variável referenciado por @keyref não é renderizado.
- Conector de oxigênio || O botão &quot;Editar no Oxygen&quot; agora abre o arquivo no modo de edição mesmo se não for feito o check-out do arquivo.
- As predefinições de saída personalizadas não estão sendo criadas com um modelo de mapa personalizado.
- A conversão do Microsoft Word (.docx) em DITA não está criando o nó jcr:content e permitindo caracteres especiais para nomes de pastas.
- Quando um MAP é movido (com mais de 150 referências), as referências são interrompidas e os erros são observados ao abrir tópicos.
- A resolução de uma imagem é calculada incorretamente quando a largura da imagem é alterada.
- Quando uma imagem é adicionada em um `<codeblock>`, espaços em branco indesejados são encontrados na saída do site do AEM.

