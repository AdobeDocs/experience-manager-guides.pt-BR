---
title: Adicionar fontes personalizadas ao seu PDF DITA
description: Obtenha integração de fontes personalizada para reforçar a identidade da marca e a consistência visual em todo o seu conteúdo em PDFs DITA nativos.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: 151e3b1c-6340-4ff2-84d4-246bc4b68065
source-git-commit: 9c53ac725618db1164b0ed310a47b258a7224778
workflow-type: tm+mt
source-wordcount: '222'
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
