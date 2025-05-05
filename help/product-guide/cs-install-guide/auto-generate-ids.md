---
title: Gerar IDs de elemento automaticamente
description: Saiba como gerar IDs de elemento automaticamente
exl-id: a651db7f-228e-4de5-b569-3f1b4f86c418
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 1%

---

# Gerar IDs de elemento automaticamente {#id20CIL40016I}

O AEM Guides gera uma ID de documento para qualquer novo documento que você criar. Por exemplo, quando você cria um mapa DITA, uma ID como `map.ditamap_random_digits` é atribuída à ID do mapa. Você também pode definir elementos nos quais uma ID é gerada e atribuída automaticamente.

O AEM Guides fornece configurações fáceis, nas quais é necessário definir os elementos nos quais uma ID é gerada automaticamente e um padrão para a ID. Por padrão, alguns elementos como `section`, `table`, `ul`, `ol`, estão configurados para geração automática de ID. Você pode adicionar outros elementos a esta lista para que, sempre que esses elementos forem inseridos em um documento, o AEM Guides gere e atribua uma ID com base no padrão fornecido

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(property\) para configurar as IDs de elemento geradas automaticamente:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | Especifique uma lista de elementos separada por vírgulas. <br> **Valor padrão**: `"topic, section, table, simpletable, fig, image, ul, ol"` |

Para configurar um padrão para a ID gerada automaticamente, crie um arquivo de configuração com as seguintes propriedades:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | O valor padrão deste campo está definido como `${elementName}_${id}`. O valor `${elementName}` é substituído pelo nome do elemento. A variável `${id}` gera um número sequencial para o elemento. Por exemplo, se você atribuir o elemento de parágrafo para ter IDs geradas automaticamente, o primeiro parágrafo do tópico ou documento terá uma ID como p\_1, o próximo parágrafo terá p\_2 e assim por diante. No entanto, em um documento diferente, o processo de geração de ID é reiniciado. Isso significa que em um documento diferente, IDs como p\_1 e p\_2 podem ser atribuídas a elementos de parágrafo. **Valor padrão**: ``${elementName}_${id}`` |

**Tópico pai:**&#x200B;[ Personalizar editor da Web](conf-web-editor.md)
