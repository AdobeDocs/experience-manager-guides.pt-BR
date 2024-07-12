---
title: Gerar IDs de elemento automaticamente
description: Saiba como gerar IDs de elemento automaticamente
exl-id: 8d09ab89-4be5-49f1-9831-9f01c92dc472
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Gerar IDs de elemento automaticamente {#id20CIL40016I}

O AEM Guides gera uma ID de documento para qualquer novo documento que você criar. Por exemplo, quando você cria um mapa DITA, uma ID como `map.ditamap_random_digits` é atribuída à ID do mapa. Você também pode definir elementos nos quais uma ID é gerada e atribuída automaticamente.

O AEM Guides fornece configurações fáceis, nas quais é necessário definir os elementos nos quais uma ID é gerada automaticamente e um padrão para a ID. Por padrão, alguns elementos como `section`, `table`, `ul`, `ol`, estão configurados para geração automática de ID. Você pode adicionar outros elementos a esta lista para que, sempre que esses elementos forem inseridos em um documento, o AEM Guides gere e atribua uma ID com base no padrão fornecido

Execute as seguintes etapas para configurar elementos para que tenham uma ID gerada automaticamente:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nas configurações de *XmlEditorConfig*, especifique um ou mais elementos no campo **Gerar IDs Automaticamente para Marcas de Elemento**.

   >[!NOTE]
   >
   > Marcas de elemento são nomes de elementos DITA como `body`, `title`, `codeblock` e assim por diante. Para especificar vários elementos, separe os nomes dos elementos com uma vírgula.

1. No campo **Padrão para Gerar IDs**, especifique um padrão para gerar uma ID.

   O valor padrão deste campo está definido como `${elementName}_${id}`. O valor `${elementName}` é substituído pelo nome do elemento. A variável `${id}` gera um número sequencial para o elemento. Por exemplo, se você atribuir o elemento de parágrafo para ter IDs geradas automaticamente, o primeiro parágrafo do tópico ou documento terá uma ID como p\_1, o próximo parágrafo terá p\_2 e assim por diante. No entanto, em um documento diferente, o processo de geração de ID é reiniciado. Isso significa que em um documento diferente, IDs como p\_1 e p\_2 podem ser atribuídas a elementos de parágrafo.

   Se o documento já contiver IDs no padrão especificado, o processo de geração automática não atribuirá essas IDs aos novos elementos.

1. Clique em **Salvar**.


**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
