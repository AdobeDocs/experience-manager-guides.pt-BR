---
title: Perguntas frequentes sobre a nova migração de linha de base no Adobe Experience Manager Guides
description: Saiba mais sobre as perguntas frequentes sobre a nova migração de linha de base no Adobe Experience Manager Guides.
TQID: https://experienceleague.adobe.com/hsiglBlwA8KOqUkkDck1RZb307TBuHfoVFb64DKTcXk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
  - id: f6b497f1-f8e0-42ce-8e95-56c28d94026e
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: 919
ht-degree: 0%

---

# Perguntas frequentes sobre a nova migração da linha de base

Estas perguntas frequentes abordam perguntas comuns relacionadas à Migração de nova linha de base, alterações de comportamento, considerações sobre a migração e resultados esperados ao atualizar para o novo modelo de linha de base.

## Quais são os principais benefícios de migrar para a nova linha de base?

O novo modelo de linha de base oferece várias melhorias, incluindo:

- Desempenho e escalabilidade aprimorados
- Melhor consistência da interface e do back-end
- Comportamento determinístico de edição e salvamento
- Recursos aprimorados de filtragem e navegação
- Visualizações de impacto de dependência
- Maior confiabilidade durante a criação e as atualizações da linha de base
- Melhor suporte à API e à automação

## A migração de linha de base cria novas linhas de base para todas as versões de um mapa?

Não, o processo de migração cria novas linhas de base somente para a **cópia de trabalho atual** do mapa. As linhas de base associadas a outras cópias de trabalho não são incluídas na migração.

## O que acontece quando um usuário reverte para uma versão anterior de um mapa?

Quando uma versão anterior de um mapa é restaurada ou acessada, as linhas de base associadas a essa versão são migradas automaticamente para o novo modelo de linha de base por um processo de migração assíncrono.

## As referências inválidas são migradas para a nova linha de base?

Não, referências inválidas são ignoradas durante a migração para manter a consistência da linha de base e garantir a confiabilidade da linha de base migrada.

## A migração da linha de base altera a linha de base?

A migração de linha de base retém todo o conteúdo de linha de base válido e faz referência exatamente como estão. No entanto, referências inválidas não são incluídas na linha de base migrada. Além da remoção de referências inválidas, a migração não introduz alterações em referências ou no comportamento da resolução de dependência.

Quaisquer outras alterações nas referências ou na resolução de dependência só podem ocorrer depois que a linha de base migrada é modificada, recriada ou recém-criada usando o novo modelo de linha de base.

Até que uma dessas ações seja executada, a linha de base migrada continuará a refletir a definição original.

## As referências `reltable` estão incluídas no novo modelo de linha de base?

Não, as referências originárias de elementos `reltable` são excluídas da resolução da linha de base, consistente com o comportamento do modelo de linha de base herdado.

## Como as referências DIRETAS são tratadas na nova linha de base?

No modelo Nova linha de base, as referências de mapa direto são classificadas explicitamente como referências **DIRECT**. Durante a migração e a resolução da linha de base, essas referências recebem a maior prioridade e são resolvidas antes de todos os outros tipos de referência.

## As referências `scope="peer"` estão incluídas na linha de base?

Não, referências com `scope="peer"` não estão incluídas no modelo de linha de base. Excluir essas referências melhora o desempenho de publicação e evita a resolução de dependências desnecessárias.

## As linhas de base ainda podem ser gerenciadas no Painel do mapa?

Não, o gerenciamento de linhas de base é suportado somente no **Console do Mapa** na Nova Linha de Base.Não há suporte para a criação e o gerenciamento de linhas de base no **Painel de Mapa**.

## É necessária alguma precaução durante a migração?

Sim, as modificações na linha de base devem ser evitadas enquanto a migração está em andamento, especialmente em cópias de trabalho. Fazer alterações em linhas de base durante a migração pode levar a falhas de migração e pode deixar linhas de base em um estado inconsistente.

## O que acontece se as versões estiverem ausentes após a migração?

Algumas linhas de base talvez precisem ser recriadas após a migração se as versões referenciadas por essas linhas de base não estiverem mais disponíveis ou acessíveis.


## Qual é o tempo aproximado necessário para migrar linhas de base para uma configuração no local?

O tempo de migração depende de vários fatores, incluindo:

- O número de linhas de base sendo migradas
- O número total de referências nessas linhas de base
- Tamanho e complexidade do repositório
- Configuração de hardware
- Recursos de sistema disponíveis

Com base em testes internos e observações de repositórios contendo aproximadamente 18.000 referências, a duração da migração pode variar bastante dependendo da estrutura do repositório e do ambiente operacional.

| Escopo da migração | Duração típica |
|-----------------|------------------|
| Linha de base única | Alguns segundos |
| 10-15 linhas de base | Algumas dezenas de segundos |
| 25-50 linhas de base | Aproximadamente 1-2 minutos |

>[!NOTE]
>
> Esses números são fornecidos apenas para referência e se baseiam em um ambiente no local. Os valores reais podem variar dependendo da complexidade do repositório, da capacidade de infraestrutura, da configuração de hardware e das condições gerais de operação.

## Podemos reverter para Linhas de Base Antigas novamente?

Sim. No entanto, quando uma reversão é executada, as linhas de base antigas são restauradas ao estado em que se encontravam no momento da migração. Quaisquer alterações feitas enquanto a antiga configuração de linha de base estava desativada e a nova configuração de linha de base estava ativa não são refletidas nas linhas de base restauradas.

Os objetos originais da linha de base antiga permanecem disponíveis no local original. Quando a nova configuração de linha de base é desativada, o sistema alterna automaticamente para o uso desses objetos originais.

## Como podemos migrar para Novas linhas de base?

Para migrar para a nova linha de base, siga as etapas em [Migrar para a Nova Linha de Base](./web-editor-baseline-v2.md#migrate-to-new-baseline).

## Podemos migrar para a nova linha de base a qualquer momento? Há algum pré-requisito?

Sim. Você pode ativar a nova linha de base a qualquer momento, desde que seu ambiente atenda aos requisitos mínimos de versão.

**Pré-requisitos:**

- AEM Guides (no local): versão 5.2 ou posterior
- AEM Guides (Cloud Service): versão 2026.05.0 ou posterior

Quando esses requisitos forem atendidos, você poderá migrar suas linhas de base antigas existentes para o novo modelo de linha de base e começar a usar seus recursos.

## É necessário fazer backup do estado atual do servidor antes de migrar para a nova linha de base?

Nenhum backup adicional é necessário especificamente para a migração para a nova linha de base.

No entanto, as linhas de base associadas à cópia de trabalho podem ser perdidas se um usuário executar posteriormente uma operação de reversão de versão. Esse comportamento não é exclusivo do novo modelo de linha de base. A reversão para uma versão anterior também pode remover os nós de cópia de trabalho da linha de base antigos correspondentes.

Se preservar as linhas de base da cópia de trabalho for importante, é recomendável fazer backup delas antes da migração. Depois da migração, os usuários trabalharão principalmente com novas linhas de base, mas uma reversão de versão subsequente ainda poderá resultar na perda das linhas de base da cópia de trabalho.


