---
title: Adicionar fontes personalizadas ao seu PDF DITA
description: Obtenha integração de fontes personalizada para reforçar a identidade da marca e a consistência visual em todo o seu conteúdo em PDFs DITA nativos.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: 151e3b1c-6340-4ff2-84d4-246bc4b68065
TQID: https://experienceleague.adobe.com/xqr9eYA2XTcyXL8X4aS-Wu2-FmU8-aCWDpb-L2BBFqI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 223
ht-degree: 0%

---

# Adicionar fontes personalizadas à sua PDF nativa DITA

## Este artigo abrange:

Adicionar a fonte personalizada para reforçar a identidade da marca e a consistência visual em todo o conteúdo.

Esse processo envolve 3 etapas:

- [Fazer upload da fonte personalizada](#step-1--upload-the-custom-font-to-the-resource-folder-of-your-template)
- [Faça as alterações necessárias na folha de estilos dos modelos do PDF](#step-2--make-necessary-changes-in-pdf-templatess-stylesheet)

- [Incorporar fontes usadas (Opcional)](#step-3-optional--embed-used-font-in-pdf)

## Etapa 1: Fazer upload da fonte personalizada para a pasta de recursos do seu modelo

![Importar e carregar fontes personalizadas ](../assets/publishing/custom-font1.png)

## Etapa 2: fazer as alterações necessárias na folha de estilos dos modelos do PDF

![Face de fonte na folha de estilos do modelo do PDF ](../assets/publishing/custom-font2.png)

## Etapa 3 (opcional): incorporar fonte usada no PDF

![Incorporação de fonte personalizada no DITA PDF ](../assets/publishing/custom-font3.png)

## Perguntas frequentes

### Posso usar o Adobe Fonts?

> Sim, vá para fonts.adobe.com e clique em &quot;Adicionar ao projeto da Web&quot;.
> 
> Copiar código de importação como `" @import url("https://use.typekit.net/xxxx.css")`;
>
> Cole no CSS de conteúdo e faça as alterações desejadas no arquivo CSS.

![Usar fonte da adobe no DITA PDF](../assets/publishing/custom-font4.png)


### Minha fonte não é exibida no PDF

> Verificar ortografia do nome da fonte novamente (erro mais comum)
>
> Verifique se a fonte está incorporada se as fontes não estão disponíveis no sistema em que o PDF está aberto

## Para outras dúvidas, entre em contato com seus respectivos CSMs


## Outros recursos:

- [Como incluir o índice do DITA Bookmap no PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Como incluir o índice na publicação do PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Vídeo de sessão com especialistas sobre o PDF nativo](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
