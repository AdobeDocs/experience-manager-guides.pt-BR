---
title: Notas de versão | Instruções de atualização da versão 5.1.0 do Adobe Experience Manager Guides
description: Saiba mais sobre a matriz de compatibilidade e como atualizar para a versão 5.1.0 do Adobe Experience Manager Guides.
exl-id: 4b7b6756-d260-4baf-a9cb-d99fc02f020f
source-git-commit: 6bcfed792036a51aa0c11498e4cb489199280a56
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 4%

---

# Instruções de atualização da versão 5.1.0 (setembro de 2025)

Este artigo aborda as instruções de atualização e a matriz de compatibilidade da versão 5.1.0 do Adobe Experience Manager Guides.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 5.1.0](../release-info/whats-new-5-1-0.md).

Para obter a lista de problemas que foram corrigidos nesta versão, consulte [Problemas corrigidos na versão 5.1.0](../release-info/fixed-issues-5-1-0.md).

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade para os aplicativos de software compatíveis com a versão Experience Manager Guides 5.1.0.

| Guias do AEM | Versão do AEM | Pacote de serviços |
| --- | --- | --- |
| 5.1.0 (UUID) | 6.5 LTS | 1 |
| 5.1.0 (UUID) | 6,5 | 23, 22, 21 |

Para obter mais detalhes, consulte a seção [Requisitos técnicos](../install-guide/download-install-technical-requirements.md) no Guia de Instalação e Configuração no Local.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão | FMPS | FM |
| --- | --- | --- |
| 5.1.0 (UUID) | Compatível | 2022 ou superior |

### Conector de oxigênio

| Versão | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.1.0 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Versão do modelo da knowledge base

| Nome do pacote de componentes | Versão dos componentes | Versão do modelo |
|---|---|---|
| Pacote de conteúdo dos componentes do Experience Manager Guides para Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Nova versão do modelo de site do AEM


| Guias do AEM | Versão do AEM | Versão dos componentes | Versão do site |
|---|---|---| ---|
| UUID 5.1.0 | 6.5 LTS | guides-components.all-1.4.1 | aemg-docs.all-1.2.0 |
| UUID 5.1.0 | 6,5 | guides-components.all-1.4.0 | aemg-docs.all-1.2.0 |

## Atualização para o Experience Manager Guides 5.1.0

Você pode atualizar facilmente sua versão atual do Experience Manager Guides para a versão 5.1.0 no **AEM 6.5** ou **AEM 6.5 LTS**.

>[!NOTE]
>
> Se você estiver usando o AEM 6.5 e planeja migrar para o AEM 6.5 LTS, conclua a atualização do AEM primeiro antes de prosseguir com a atualização do Experience Manager Guides 5.1.0. Para obter detalhes, consulte [Atualização para o Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/pt-br/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Antes de prosseguir com a atualização para a versão 5.1.0 do Experience Manager Guides, você deve considerar os seguintes pontos:

- Se você estiver usando a versão 4.6.3, 4.6.4, 5.0.0 ou 5.0.0 do Service Pack 1, é possível atualizar diretamente para a versão 5.1.0.
- Se você estiver usando a versão 4.6.0, 4.6.1, será necessário atualizar para a versão 4.6.3, 4.6.4 ou 5.0.0 antes de atualizar para a versão 5.1.0.
- Se você estiver usando a versão 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 ou 4.1.x, será necessário atualizar para a versão 4.4 antes de atualizar para a versão 5.1.0.
- Se você estiver usando a versão 4.0, será necessário atualizar para a versão 4.2 antes de atualizar para a versão 4.3.x.
- Se você estiver usando a versão 3.8.5, será necessário atualizar para a versão 4.0 antes de atualizar para a versão 4.2.
- Se você estiver usando uma versão anterior à 3.8.5, consulte a seção Atualizar Experience Manager Guides no guia de instalação específico do produto, disponível no [arquivo PDF de ajuda do Adobe Experience Manager Guides](https://helpx.adobe.com/br/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Você deve instalar o service pack do AEM antes de atualizar a versão do Experience Manager Guides.

Para obter detalhes, consulte [Instruções de atualização para as versões no local](../install-guide/upgrade-xml-documentation.md) do Experience Manager Guides.


