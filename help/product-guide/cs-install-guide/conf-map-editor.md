---
title: Definir o Editor de mapa avançado como padrão
description: Saiba como definir o Editor de mapa avançado como padrão
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/xTRMho5Nhc9KScSAzQIXy5Z6bMAe-ERLjhZMItRyj4k
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 0%

---

# Definir o Editor de mapa avançado como padrão {#id181AI0003PN}

>[!NOTE]
>
> O Editor de mapa básico, anteriormente disponível no Experience Manager Guides, foi descontinuado a partir da versão 4.3 e 2307. Não é possível acessar o Editor de mapa básico para criar e gerenciar mapas DITA.
>É recomendável usar o Editor de mapa avançado. O Editor de mapa avançado oferece recursos aprimorados e melhores opções de personalização. Saiba mais sobre como trabalhar com o [Editor de mapa avançado](../user-guide/map-editor-advanced-map-editor.md).

Para versões anteriores à 4.3 e 2307, o Experience Manager Guides vem com um Editor de mapa básico e um Editor de mapa avançado. O Editor de mapa básico fornece todos os recursos necessários para criar seu arquivo de mapa. O Editor de mapa avançado possui muito mais recursos e está integrado ao Editor da Web. O Editor de mapa avançado permite que os autores criem e editem arquivos de mapa DITA com uma interface fácil de usar.

Por padrão, sempre que um novo arquivo de mapa é criado, ele é aberto no Editor de mapa básico. Você pode alterar esse comportamento ativando a configuração para abrir o Editor de mapa avançado por padrão.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para ativar o Editor de mapa básico:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Booleano \(true/false\). Se você quiser usar o Editor de Mapa Avançado como padrão, defina esta propriedade como verdadeira.<br> **Valor padrão**: falso |

>[!NOTE]
>
> Por padrão, quando um autor cria um arquivo de mapa e opta por abri-lo para edição, o Editor de mapa básico é iniciado. Quando a opção Editar é selecionada para um arquivo de mapa na interface do usuário do Assets, ela também é aberta no Editor de mapa básico.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
