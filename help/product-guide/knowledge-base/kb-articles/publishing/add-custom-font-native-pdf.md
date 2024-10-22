---
title: Adicionar fontes personalizadas ao PDF DITA
description: Obtenha integração de fontes personalizada para reforçar a identidade da marca e a consistência visual em todo o seu conteúdo em PDF de DITA nativo.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: 518bec870dc07e88a422d889a1c54be26c248799
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Adicionar fontes personalizadas ao seu PDF nativo DITA

## Este artigo abrange:

Adicionar a fonte personalizada para reforçar a identidade da marca e a consistência visual em todo o conteúdo.

Esse processo envolve 3 etapas:

- [Fazer upload da fonte personalizada](#step-1--upload-the-custom-font-to-the-resource-folder-of-your-template)
- [Faça as alterações necessárias na folha de estilos dos modelos PDF](#step-2--make-necessary-changes-in-pdf-templatess-stylesheet)

- [Incorporar fontes usadas (Opcional)](#step-3-optional--embed-used-font-in-pdf)

## Etapa 1: Fazer upload da fonte personalizada para a pasta de recursos do seu modelo

![Importar e carregar fontes personalizadas ](../assets/publishing/custom-font1.png)

## Etapa 2: Fazer as alterações necessárias na folha de estilos dos modelos PDF

![Face de fonte na folha de estilos do modelo PDF ](../assets/publishing/custom-font2.png)

## Etapa 3 (opcional): incorporar fonte usada no PDF

![Incorporação de fonte personalizada no PDF ](../assets/publishing/custom-font3.png) do DITA

## Perguntas frequentes

- ### Posso usar o Adobe Fonts?

> Sim, vá para fonts.adobe.com e clique em &quot;Adicionar ao projeto da Web&quot;.
> 
> Copiar código de importação como `" @import url("https://use.typekit.net/xxxx.css")`;
>
> Cole no CSS de conteúdo e faça as alterações desejadas no arquivo CSS.

![Usar fonte da adobe no PDF DITA](../assets/publishing/custom-font4.png)


- ### Minha fonte não é exibida no PDF

> Verificar ortografia do nome da fonte novamente (erro mais comum)
>
> Verifique se a fonte está incorporada se as fontes não estão disponíveis no sistema onde o PDF está aberto

- ## Para outras dúvidas, entre em contato com seus respectivos CSMs


## Outros recursos:

- [Como incluir o índice do DITA Bookmap no PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Como incluir o índice na publicação do PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Vídeo de sessão especializada sobre o PDF nativo](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)