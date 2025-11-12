---
title: Perguntas frequentes sobre desempenho de publicação e escalabilidade no Adobe Experience Manager Guides
description: Saiba mais sobre as perguntas frequentes sobre desempenho de publicação e escalabilidade no Adobe Experience Manager Guides.
source-git-commit: d128860bdff78c100ba348b54a237b237171635f
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 0%

---

# Perguntas frequentes

Esta é uma lista de respostas para perguntas frequentes que fornece insights detalhados sobre como o Adobe Experience Manager Guides gerencia fluxos de trabalho de publicação, comportamento de dimensionamento e desempenho de infraestrutura. Destina-se a usuários corporativos, administradores e equipes de documentação que usam o Experience Manager Guides para publicação em larga escala. O diagrama explica o fluxo de trabalho geral da Experience Manager Guides Publishing Architecture.

![](images/IO_runtime.drawio.png){align="left"}


## Quantas solicitações de publicação o Experience Manager Guides pode executar por dia?

O número de solicitações de publicação que o Experience Manager Guides pode processar por dia depende do tamanho e do tipo do conteúdo. De acordo com a configuração, o sistema permite um trabalho de publicação por núcleo do processador. Na configuração atual, 20 trabalhos de publicação podem ser executados em paralelo (2 pods × 10 núcleos cada).

Conforme o ambiente de produção é dimensionado automaticamente, esse número pode aumentar para 40 trabalhos de publicação simultâneos quando os pods são dimensionados para até 4.

## Quantas solicitações de publicação podem ser executadas simultaneamente antes de serem enfileiradas?

- Mínimo (padrão): 20 trabalhos de publicação (2 pods)
- Máximo (em escala): 40 trabalhos de publicação (4 pods)

Esse número pode variar com base na carga geral do servidor. Se outros trabalhos de Sling em segundo plano estiverem em execução, eles compartilharão núcleos de processamento, reduzindo potencialmente a simultaneidade para menos de 20.

## A execução de várias solicitações de publicação afeta outras funcionalidades do aplicativo, como a edição de arquivos .dita?

Pode haver algum impacto no desempenho, mas geralmente é mínimo. A maioria do processamento pesado ocorre no tempo de execução de E/S (serviço de publicação sem servidor), enquanto a instância do AEM executa principalmente operações de E/S para geração de dependência e sondagem de status. Como resultado, a utilização do CPU no AEM permanece baixa e as experiências de criação/edição não são afetadas.

## Como o Experience Manager Guides gerencia arquivos e gráficos grandes, como arquivos SVG ou arquivos .dita com mais de 500 KB?

Todos os arquivos grandes são compactados e armazenados no JCR (Java Content Repository). O tempo de execução de E/S busca o pacote zip completo antes de iniciar a publicação. Mesmo ao manipular vários arquivos grandes (por exemplo, 500 KB cada), isso não afeta significativamente a velocidade de download ou de transferência devido ao empacotamento otimizado e ao manuseio de E/S paralela.

## Qual é a infraestrutura e a configuração de publicação usadas pelo Experience Manager Guides?

O Experience Manager Guides usa microsserviços sem servidor e em contêiner para publicação. Cada nova versão do serviço de publicação é lançada como uma imagem do Docker, implantada automaticamente no ambiente de nuvem do Adobe. Esse design garante:

- Sem manutenção de infraestrutura dedicada para os clientes
- Dimensionamento automático para lidar com a demanda de publicação
- Atualizações rápidas e tempo de inatividade mínimo

## Se a fila de publicação ou o sistema de gerenciamento travar devido à sobrecarga, outras funcionalidades do AEM serão afetadas?

Não, o Experience Manager Guides foi criado com uma arquitetura tolerante a falhas. Se a fila de publicação ficar sobrecarregada, as solicitações serão repetidas automaticamente e os pods serão dimensionados automaticamente para lidar com a carga adicional. Além de um determinado limite, a limitação de carga é aplicada para manter a estabilidade. Outras áreas de aplicativos (criação, revisão, gerenciamento de ativos) permanecem inalteradas.

## Há uma ferramenta de monitoramento ou acesso ao log disponível para identificar quando o Experience Manager Guides está sobrecarregado (semelhante ao monitoramento do Jenkins)?

Não, no momento você não tem acesso às ferramentas de monitoramento internas. Para equipes internas da Adobe, o monitoramento pode ser feito usando:

- Splunk para rastreamento de log e erros
- CLI Kubernetes (K8s) para verificar o desempenho em nível de pod e o comportamento de dimensionamento

Se ocorrer degradação de desempenho, os clientes devem entrar em contato com o suporte da Adobe para iniciar a investigação e a análise.

## Que processamento é feito antes de despachar uma solicitação de publicação para o microsserviço?

Ao acionar uma solicitação de publicação na guia Predefinições do console Mapa, as seguintes etapas ocorrem:

1. O sistema aceita a solicitação e valida as predefinições de linha de base e condicional.
2. A AEM agrega todos os ativos e dependências DITA qualificados.
3. Esses ativos são agrupados em um pacote zip.
4. O serviço de publicação sem servidor ativa um contêiner Docker, baixa os ativos, executa a operação de publicação e coloca os artefatos de saída gerados de volta no Experience Manager Guides.

Esse fluxo de trabalho garante a execução de publicação confiável, isolada e escalonável.

## Quanto tempo um mapa leva antes de começar a publicar no contêiner de microsserviço e quais são os fatores que definem esse tempo?

Uma solicitação de publicação geralmente leva alguns minutos antes de ser enviada para o container microsserviço. Esse tempo inicial é usado para agregação de dependência no AEM.

Depois que a solicitação é recebida no serviço de publicação sem servidor, o tempo total de publicação depende:

- Tamanho do mapa DITA
- Número de tópicos e ativos de mídia
- Complexidade do conteúdo condicional e das regras de formatação

Mapas maiores ou mais complexos podem levar proporcionalmente mais tempo para serem publicados.

## O Experience Manager Guides pode priorizar solicitações de publicação na fila (em vez de Primeiro a chegar, Primeiro a ser atendido)?

Atualmente, todos os trabalhos de publicação são tratados de forma igual e seguem um modelo First-Come, First-Serve (FCFS). Não há nenhum mecanismo de priorização disponível no momento.

No entanto, em versões futuras, a lógica de priorização (por exemplo, com base no tamanho da tarefa ou na importância dos negócios) poderá ser introduzida como parte das melhorias de otimização de fila.

## Como o Experience Manager Guides lida com o dimensionamento automático para solicitações de publicação?

A infraestrutura de publicação do Experience Manager Guides oferece suporte ao dimensionamento automático com base na carga. Ao publicar aumentos de demanda:

- Os pods (contêineres) adicionais são girados automaticamente.
- Cada pod pode processar vários trabalhos de publicação em paralelo.
- Quando a carga diminuir, os pods diminuem para otimizar o custo e o desempenho.

Isso garante alta disponibilidade, desempenho consistente e tempo mínimo de fila durante o pico de carga.

## O que acontece se um trabalho de publicação falhar ou atingir o tempo limite?

Se uma solicitação de publicação falhar devido a um problema transitório (por exemplo, interrupção da rede, tempo limite do serviço):

- ela é automaticamente repetida com base na lógica de repetição configurada no serviço de publicação.
- registros e mensagens de erro são capturados no back-end para fins de diagnóstico.
- você pode visualizar o status de falha e tentar publicar novamente manualmente no console Mapa, se necessário.

## É possível monitorar ou rastrear o progresso de um trabalho de publicação?

Sim, o Experience Manager Guides fornece atualizações de status de job em tempo real na guia Predefinições do console Mapa, incluindo:

- Início e hora de conclusão do trabalho
- Estágio atual (compactação, expedição, publicação ou upload de resultados)
- Notificações de erro (se houver)

Isso ajuda você a entender o progresso do trabalho e identificar possíveis atrasos.

## Quais práticas recomendadas podem melhorar o desempenho de publicação no Experience Manager Guides?

Para garantir a velocidade ideal de publicação, siga estas práticas recomendadas:

- Evite arquivos de imagem grandes desnecessários ou tópicos sem referência
- Usar linhas de base para limitar o escopo de publicação
- Manter hierarquias de mapa DITA gerenciáveis e bem organizadas
- Programar publicação pesada fora do horário de pico
- Usar filtros condicionais de maneira eficaz para reduzir a carga de processamento




