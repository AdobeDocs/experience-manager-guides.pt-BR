---
title: Adicionar novo botão acionável personalizado na barra de ferramentas do editor da Web
description: Saiba como adicionar um novo botão personalizado na barra de ferramentas do editor da Web e chamar javascript para personalizá-lo.
exl-id: 34999db6-027a-4d93-944f-b285b4a44288
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/7NqswCerJdfej5j4XqnPhHzvvAkhlThHAUY3iQYL3t0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 553
ht-degree: 0%

---

# Adicionar novo botão acionável personalizado na barra de ferramentas do editor da Web

Neste artigo, aprenderemos como adicionar um novo botão personalizado na barra de ferramentas do editor da Web e chamar javascript para executar a operação personalizada desejada.

A adição de um botão acionável ao editor da Web envolve as seguintes etapas:
- Adicionar o botão no *ui_config.json* na posição em que é necessário
- Registrar o evento de clique no botão no editor da Web para que o usuário execute uma ação ao clicar nele


## Implementar utilizando um exemplo

Vamos entender isso com um exemplo em que um autor deseja adicionar uma referência de jira a uma seção de prólogo de tópico. A seção de prólogo com id de referência jira incorporada pode ser semelhante a:

![Seção do prólogo com referência à ID JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)

O elemento &quot;change-request-id&quot; que contém a ID de JIRA deve ser recuperado da API (digamos, com base em uma consulta de JIRA específica descrita pelo aplicativo). Quando o usuário está criando a seção de prólogo, o usuário deve ser capaz de clicar em um botão e inserir uma ID de referência jira na barra de ferramentas do editor da Web, semelhante a:

![Seção do prólogo - adicionar referência JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference.png)

E quando o usuário clica no botão, ele deve mostrar uma caixa de diálogo que deve puxar as opções possíveis e permitir que o usuário selecione a ID JIRA desejada, algo como:

![Caixa de diálogo Adicionar ID do Prolog](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference-dialog.png)

que deve então adicionar o &quot;change-request-id&quot; ao prólogo:

![Seção do prólogo com referência à ID JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)



## A implementação desta


### Adicione o botão no webeditor, configurando-o em *ui_config.json*

Use os perfis de pasta para verificar o *ui_config.json* na guia &quot;Configuração do editor XML&quot; e adicionar a configuração de botão JSON na seção desejada do grupo &quot;barra de ferramentas&quot;

```
{
    "on-click":"insertJIRARef",
    "icon":"linkCheck",
    "variant":"quiet",
    "type":"button",
    "title":"Insert JIRA Reference"
}
```

[use este link para saber mais sobre Perfil de pasta e configuração ui_config.json](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en)


### Manipular o evento ao clicar para o novo botão

OBSERVAÇÃO: as etapas mencionadas abaixo estão disponíveis como pacote anexado a esta publicação


- Depois de salvar o perfil de pasta, crie um &quot;cq:ClientLibraryFolder&quot; em um diretório de projeto (pode estar em */apps*) e adicione propriedades conforme mostrado na captura de tela abaixo:
  ![Configurações da biblioteca do cliente para webeditor](../../../assets/authoring/webeditor-add-customtoolbarbutton-clientlibrarysettings.png)

```
This example uses "coralui3" library to show a dialog as it is used in the Javascript sample we presented.
You may use different library of your choice.
```

- Nessa pasta da biblioteca do cliente, crie dois arquivos, conforme mencionado abaixo:
   - *overrides.js*: que terá o código javascript para lidar com o evento de clique para &quot;insertJIRARef&quot; (use o pacote anexado para obter o conteúdo deste javascript)
   - *js.txt*: que incluirá o &quot;overrides.js&quot; para habilitar esse javascript

- Salve as alterações e você estará pronto para testar.


### Testes

- Abrir editor da Web
- Nas preferências do usuário, escolha o perfil de pasta no qual você adicionou o *ui_config.json* personalizado. Se você o adicionou ao Perfil global, provavelmente já está usando isso.
- Abra um tópico, você notará a barra de ferramentas com um novo botão &quot;Inserir referência Jira&quot;
- Você pode então adicionar a seção do prólogo conforme fornecido abaixo ao tópico e tentar clicar no botão &quot;Inserir referência do Jira&quot; dentro do elemento do prólogo &quot;change-request-reference&quot;

```
<prolog>
    <change-historylist>
        <change-item>
            <change-request-reference>
            </change-request-reference>
            <change-completed></change-completed>
            <change-summary></change-summary>
        </change-item>
    </change-historylist>
</prolog>
```

Consulte a captura de tela abaixo para saber como ela será:

![Testar novo botão](../../../assets/authoring/webeditor-add-customtoolbarbutton-testing.png)


### Anexos

- Exemplo de pacote clientlibs que instalará a biblioteca do cliente webeditor com código javascript para a ação de botão da barra de ferramentas: [baixar usando este link](../../../assets/authoring/webeditor-addbuttonontoolbar-insertjira-clientlib.zip)
- Exemplo *ui_config.json* que você pode carregar para um perfil de pasta: [baixar exemplo ui_config.json](../../../assets/authoring/sample_ui_config_Guides4.2-InsertJiraReference.json)

```
Please note this is compatible to AEM 6.5 and AEM Guides version 4.2.
If you are using a different version please add the toolbar button to the ui_config.json manually.
```
