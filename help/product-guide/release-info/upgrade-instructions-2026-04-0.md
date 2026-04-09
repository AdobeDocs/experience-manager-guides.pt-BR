---
title: Notas de versão | Instruções de atualização e problemas corrigidos no Adobe Experience Manager Guides, versão 2026.04.0
description: Saiba mais sobre a matriz de compatibilidade e como atualizar para a versão 2026.04.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: ce2c9da0d9beb05a15f7cefcf9483e0c93abbf37
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Instruções de atualização para a versão 2026.04.0

Este artigo aborda as instruções de atualização e a matriz de compatibilidade da versão 2026.04.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2026.04.0](whats-new-2026-04-0.md).

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2026.04.0](fixed-issues-2026-04-0.md).

## Matriz de compatibilidade

Esta seção aponta a matriz de compatibilidade dos aplicativos de software compatíveis com a versão 2026.04.0 do Experience Manager Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão do Experience Manager Guides as a Cloud | FMPS | FrameMaker | Oxygen Author |
| --- | --- | --- | --- |
| 2026.04.0 | Não compatível | 2022 ou superior | 26,1 |


### Conector de oxigênio

| Versão do Experience Manager Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2026.04.0 | 3.8 -uuid 1 | 3.8 -uuid 1 | 2,3 | 2,3 |


### Versão do modelo de site do AEM

| Versão dos componentes | Versão do site |
|---|---|
| guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| Pacote de conteúdo dos componentes do Experience Manager Guides para Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

## Atualização para a versão 2026.04.0

O Experience Manager Guides é atualizado automaticamente após a atualização para a versão mais recente do Experience Manager as a Cloud Service.

>[!IMPORTANT]
>
> Esta versão inclui atualizações nas configurações de perfil da pasta (ui_config.json). Se você estiver usando configurações personalizadas, certifique-se de fazer um backup delas antes da atualização. Após a atualização, revise e ajuste suas configurações para alinhar-se às alterações introduzidas na versão mais recente.

Revise e valide as configurações de configuração para confirmar se elas estão implementadas corretamente. Se você tiver introduzido alterações na configuração personalizada, exiba [Configuração adicional para atualizar o Cloud Service](../cs-install-guide/additional-config-for-cloud-service.md) para quaisquer procedimentos adicionais aplicáveis à versão da qual você está atualizando.
