---
title: Configurar filtros de visualização SCORM
description: Saiba como configurar filtros de visualização SCORM
feature: Configuration
role: Admin
level: Experienced
source-git-commit: f5b7ae41fe63b31a3b45b38fc73976987a2a5ebe
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 3%

---

# Configurar visualização de SCORM

Este artigo explica como configurar a pré-visualização do Experience Manager Guides SCORM para gerenciar quais domínios externos têm permissão para fornecer folhas de estilos, imagens, fontes, mídia e conteúdo incorporado na saída de pré-visualização do SCORM. As etapas a seguir explicam como configurar vários filtros para visualização de SCORM, dependendo da configuração que você estiver usando:

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Use as instruções fornecidas em [Substituições de configuração](../install-conf-guide/download-install-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes de propriedade:

   | PID | Chave de propriedade | Valor padrão |
   |---|---|---|
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.style.src` | `https://fonts.googleapis.com` |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.img.src` | - |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.font.src` | `https://fonts.gstatic.com` |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.media.src` | - |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.frame.src` | `https://www.youtube-nocookie.com`, `https://www.youtube.com` |


1. Salve o arquivo de configuração e implante-o no ambiente do Cloud Service.

Depois de salva, a visualização SCORM começa a aplicar o incluo na lista de permissões de domínio atualizado. Os recursos externos de domínios que não foram adicionados a essa configuração não estarão disponíveis na visualização.

>[!NOTE]
>
> Isso se aplica somente ao ambiente de visualização; o pacote SCORM disponível para download continua a fornecer todo o conteúdo criado conforme esperado.


>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote **Filtro de visualização de SCORM de guias (com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter)**.

   ![](assets/scorm-preview-filters.png){width="600"}


1. Na configuração do pacote, adicione os URLs de domínio permitidos para cada tipo de recurso, conforme necessário:

   | Texto | Descrição |
   |---|---|
   | **Host style-src adicional** | Domínios dos quais as folhas de estilos CSS externas estão autorizadas a carregar (por padrão, `https://fonts.googleapis.com`). |
   | **Host image-src adicional** | Domínios dos quais as imagens externas estão autorizadas a carregar. |
   | **Host font-src adicional** | Domínios dos quais os arquivos de fontes externas (OTF, WOFF, etc.) estão autorizados a carregar (por padrão, `https://fonts.gstatic.com`). |
   | **Host media-src adicional** | Domínios a partir dos quais os arquivos de mídia externos estão autorizados a carregar. |
   | **Host frame-src adicional** | Domínios dos quais o conteúdo de iframe está autorizado a ser inserido (por padrão, `https://www.youtube.com` para permitir inserções de vídeo do YouTube). |

1. Selecione **Salvar**.

Depois de salva, a visualização SCORM começa a aplicar o incluo na lista de permissões de domínio atualizado. Os recursos externos de domínios que não foram adicionados a essa configuração não estarão disponíveis na visualização.

>[!NOTE]
>
> Isso se aplica somente ao ambiente de visualização; o pacote SCORM disponível para download continua a fornecer todo o conteúdo criado conforme esperado.

>[!ENDTABS]