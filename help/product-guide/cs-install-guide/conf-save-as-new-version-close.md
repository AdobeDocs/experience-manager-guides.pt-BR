---
title: Configurar o prompt para salvar como uma nova versão ao fechar
description: Saiba como Configurar o prompt para salvar como uma nova versão ao fechar
exl-id: 9029b671-8ff8-45eb-b27e-ab89bd09e7ed
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---

# Configurar o prompt para salvar como uma nova versão ao fechar {#id222HBI00XXA}

Quando o usuário tenta fechar um arquivo aberto no Editor da Web usando o botão **Fechar** na guia do arquivo ou a opção **Fechar** no menu Opções, uma caixa de diálogo é exibida se o arquivo tiver dados não salvos ou uma versão não salva. O usuário será solicitado a salvar o arquivo como uma nova versão se a versão não for salva.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar um prompt para salvar como uma nova versão ao fechar:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Booleano \( verdadeiro/ falso\). <br>  **Valor padrão**: verdadeiro |

Quando esta configuração está habilitada, a caixa de seleção **Salvar como uma Nova Versão** é marcada por padrão na caixa de diálogo.

Para obter mais detalhes, consulte a seção *Cenários de fechamento e salvamento de arquivos*, no Guia as a Cloud Service Uso do Adobe Experience Manager Guides.

**Tópico pai:**&#x200B;[ Personalizar editor da Web](conf-web-editor.md)
