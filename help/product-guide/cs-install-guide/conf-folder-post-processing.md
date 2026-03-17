---
title: Configurar nomes de arquivo
description: Saiba como desativar o pós-processamento para uma pasta carregada no Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
source-git-commit: 635206ca34db633a998b0156e2549d86a83f8131
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Desativar pós-processamento para uma pasta

Por padrão, todos os ativos carregados são processados usando o fluxo de trabalho Atualizar ativo do DAM. O Experience Manager Guides executa um processamento adicional, chamado pós-processamento, como parte desse fluxo de trabalho. Isso também ajuda a gerar as UUIDs

Ao carregar seus arquivos e pastas para o servidor do *Adobe Experience Manager Assets*, você também pode desabilitar o pós-processamento e a geração de UUIDs.

Use as instruções em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para desativar o pós-processamento em um determinado caminho ou ignorar o pós-processamento de uma pasta:

>[!NOTE]
>
> Você também pode usar expressões regulares (regex) para definir regras que se aplicam a várias pastas ou a uma hierarquia de pastas inteira. Para obter mais detalhes, exiba a seção [Usar regex para habilitar ou desabilitar o pós-processamento](#use-regex-to-enable-or-disable-post-processing).

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valor da cadeia para definir qualquer NODE_OPTIONS padrão (propriedade de vários valores, cadeias com caminho que omitem `/` no final ou regex) <br> **Valor Padrão**: `/content/dam/projects/translation_output` |

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valor da cadeia para definir qualquer NODE_OPTIONS padrão (propriedade de vários valores, cadeias com caminho que omitem `/` no final ou regex) <br> **Valor Padrão**: `/content/dam` |

## Regras para ativar ou desativar o pós-processamento

Por padrão, o pós-processamento é feito para cada caminho de pasta na pasta do Experience Manager DAM. As configurações são aplicadas a qualquer pasta de acordo com as seguintes regras:

* Se o pai for ignorado para pós-processamento, mas a pasta filho estiver habilitada, o filho e todos os seus sucessores serão considerados habilitados.
* Se o pai estiver ativado para pós-processamento, mas o filho for ignorado, o filho e todos os seus sucessores serão considerados ignorados.
* Se o mesmo caminho de pasta existir nas configurações `ignored.post.processing.paths` e `enabled.post.processing.paths`, ele será considerado ignorado para pós-processamento.

## Usar regex para ativar ou desativar o pós-processamento

Em vez de especificar caminhos de pastas individuais, você pode usar expressões regulares (regex) para definir regras que se aplicam a várias pastas ou hierarquias de pastas inteiras.

Os padrões Regex são avaliados em relação ao caminho completo do ativo durante o pós-processamento.

Quando expressões regulares (regex) são usadas para configurar caminhos de pós-processamento ignorados e ativados, o AEM Guides avalia ambas as configurações em relação ao caminho do ativo. Se um caminho corresponder a uma regra para ignorar e a uma regra para habilitar, as regras para ignorar sempre terão prioridade.

Os exemplos a seguir ilustram como as regras ignore e enable baseadas em regex são avaliadas.

## Cenários de avaliação de regex para pós-processamento

### Ignorar hierarquia pai, habilitar pasta específica

**Ignorar regex**

`regex:/content/dam/lang-test/.*`

**Habilitar regex**

`regex:/content/dam/lang-test/.*/parent1`

No exemplo acima, o pós-processamento será desabilitado para `/content/dam/lang-test/en/parent1`.

Embora o caminho corresponda ao regex habilitado, ele já é correspondido pelo regex ignorado. Ignorar regras tem prioridade, portanto, o pós-processamento não está ativado.

### Ignorar pasta específica, habilitar hierarquia mais ampla

**Ignorar regex**

`regex:/content/dam/lang-test/.*/parent1`

**Habilitar regex**

`regex:/content/dam/lang-test/.*`

No exemplo acima, o pós-processamento será desativado para `/content/dam/lang-test/en/parent1` e ativado para `/content/dam/lang-test/en/parent2`.

O caminho `parent1` é explicitamente ignorado e permanece desabilitado. Outras pastas que correspondem somente ao regex habilitado são processadas.

### Ignorar pasta pai, habilitar uma pasta filho

**Ignorar regex**

`regex:/content/dam/lang-test/.*/parent1`

**Habilitar regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

No exemplo acima, o pós-processamento será desativado para `/content/dam/lang-test/en/parent1` e `/content/dam/lang-test/en/parent1/child2` e ativado para `/content/dam/lang-test/en/parent1/child1`.

A pasta filho habilitada explicitamente pelo regex é processada. Outras pastas secundárias permanecem desativadas porque seu caminho principal corresponde ao regex ignorado.

### Ignorar pasta filho específica, habilitar hierarquia pai

**Ignorar regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

**Habilitar regex**

`regex:/content/dam/lang-test/.*/parent1`

No exemplo acima, o pós-processamento será desativado para `/content/dam/lang-test/en/parent1/child1` e ativado para `/content/dam/lang-test/en/parent1` e `/content/dam/lang-test/en/parent1/child2`.

Somente a pasta filho ignorada explicitamente é ignorada. A pasta pai e outras pastas filho são processadas porque correspondem ao regex habilitado e não correspondem ao regex ignorado.

