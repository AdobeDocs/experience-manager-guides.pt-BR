---
title: Adicionar estilos personalizados ao editor da Web de Guias
description: Saiba como adicionar estilos personalizados para alterar a aparência do editor da Web de Guias.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
feature: Web Editor
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Adicionar estilos personalizados ao editor da Web de Guias

Neste artigo, aprenderemos como adicionar estilos personalizados para alterar a aparência padrão do editor da Web.

Isso envolverá as seguintes etapas:
- Adicionando os estilos personalizados por meio da Configuração do editor XML do perfil de pasta
- Escolher o respectivo perfil de pasta no editor da Web e testar as alterações


## Implementar utilizando um exemplo

Vamos entender isso com um exemplo em que queremos mostrar a descrição curta e o título como blocos separados com alguns aspectos de estilo no editor.

![Visualização do editor da Web com estilos personalizados](../../../assets/authoring/webeditor-customstyles-preview.png)


## A implementação desta


### Adicionar o CSS personalizado ao perfil de pasta

Use os perfis de pasta para verificar a *css_layout.css* na guia &quot;Configuração do editor XML&quot; e adicione o CSS com estilos personalizados

[use este link para saber mais sobre Perfil de pasta e configuração do layout de modelo CSS](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en#customize-the-css-template-layout)

Use o seguinte para configurar o estilo acima no editor da Web:
- Uso [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) e carregue-o no perfil de pasta de sua escolha
- Instalar o pacote anexado [webeditor-estilos-recursos.zip](../../../assets/authoring/webeditor-styles-resources.zip) utilização do gerenciador de pacotes AEM para instalar os recursos usados no arquivo CSS acima

```
This will install the resources at path "/content/dam/resources" which will include sub-folders "fonts" and "images"
```


### Testes

- Abrir editor da Web
- Em preferências do usuário, escolha o perfil de pasta no qual você adicionou os estilos personalizados. Se você o adicionou ao Perfil global, provavelmente já está usando isso.
- Abra um tópico e observe que a área de edição deve ter uma interface personalizada

```
Please note this is compatible to AEM Guides version 4.2 and AEM Guides cloud version 2303 (March)
```


## Referências

Você também pode estar interessado na sessão especializada sobre configurações do editor da Web e personalização abordada em [Sessão de especialistas sobre o editor da Web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=en)
