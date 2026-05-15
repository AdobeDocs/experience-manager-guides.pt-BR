---
title: Configurar prompt para fazer check-in de um arquivo ao fechar
description: Saiba como configurar o prompt para fazer check-in de um arquivo ao fechar
exl-id: 5b09ec46-aea4-4a3f-8bab-42414e31e37d
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/Obg0rrng-HngZvxc2mtVt16YUylMAR7mIUgC9yKn-qU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 172
ht-degree: 1%

---

# Configurar prompt para fazer check-in de um arquivo ao fechar {#id222HC040PE8}

Quando o usuário tenta fechar um arquivo aberto no Editor da Web usando o botão **Fechar** na guia do arquivo ou a opção **Fechar** no menu Opções, uma caixa de diálogo é exibida se o arquivo tiver dados não salvos ou uma versão não salva. O usuário será solicitado a desbloquear o arquivo se ele estiver bloqueado.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar um prompt para fazer check-in de um arquivo ao fechar:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booleano\ ( true/ false\).<br> **Valor padrão**: falso |

Quando esta configuração está habilitada, a caixa de seleção **Desbloquear o Arquivo** é marcada por padrão na caixa de diálogo.

Para obter mais detalhes, consulte a seção *Cenários de fechamento e salvamento de arquivos* no guia Uso do Adobe Experience Manager Guides as a Cloud Service.

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](conf-web-editor.md)
