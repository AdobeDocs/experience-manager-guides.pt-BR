---
title: Integrar editores de XML baseados em desktop
description: Saiba como integrar editores XML baseados em desktop
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
exl-id: 86ba53fa-0e08-4791-9018-09fe974691da
TQID: https://experienceleague.adobe.com/4cejVcInzwcFBWgxobUvn7g2teizpQCCeTC2Z5CZ1K8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 368
ht-degree: 1%

---

# Integrar editores de XML baseados em desktop

Há muitos editores de XML disponíveis no mercado e você já pode estar usando um. O Adobe FrameMaker é um dos editores de XML mais eficientes, que vem com o AEM Connector. Usando o conector do AEM no FrameMaker, você pode se conectar facilmente ao repositório do AEM, aos arquivos de check-out e check-in e editar arquivos diretamente no FrameMaker. Você também pode configurar o Experience Manager Guides para iniciar o FrameMaker no Editor da Web. Após abrir o arquivo no FrameMaker, você pode editá-lo e fazer seu check-in no repositório do AEM.

## Ativar a edição de arquivos no FrameMaker a partir do Editor da Web

Você pode usar o FrameMaker ou qualquer outro editor DITA para criar e atualizar conteúdo DITA. No entanto, se sua organização usar o FrameMaker como editor DITA, você poderá dar aos usuários a opção de abrir documentos DITA diretamente no FrameMaker por meio do AEM.


Por padrão, seus usuários não veem o botão **Abrir no FrameMaker** na barra de ferramentas do AEM. Execute as seguintes etapas para adicionar esse botão à barra de ferramentas do AEM:

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para adicionar este botão na barra de ferramentas do AEM:


| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Booleano \(true/false\). Se você quiser mostrar o botão **Abrir no FrameMaker**, defina essa propriedade como verdadeira. <br> **Valor padrão**: falso |



Se você estiver usando a versão 2409 e a versão de setembro do FrameMaker 2022 - Atualização 3, será necessário habilitar a configuração do **FrameMaker Versão 2022 Atualização 3 ou superior** para que seus usuários transmitam os detalhes do servidor do Experience Manager Guides para o FrameMaker.  Por padrão, está desativado.


| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Booleano \(true/false\). Se você estiver usando a versão de setembro do FrameMaker 2022 - Atualização 3, defina essa propriedade como true. <br> **Valor padrão**: falso |



Ao definir a propriedade *openinframebuttonshow* como true, o botão **Abrir no FrameMaker** é exibido ao selecionar qualquer arquivo DITA no repositório do AEM. Quando esta propriedade não está definida como *true*, o botão **Abrir no FrameMaker** é exibido somente quando você seleciona um arquivo .fm ou .book no repositório.
