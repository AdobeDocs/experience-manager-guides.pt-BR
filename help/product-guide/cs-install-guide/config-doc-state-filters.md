---
title: Configurar filtros de estado do documento
description: Saiba como configurar filtros de estado do documento
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 4942b914ff278ebcf09d00da32d6f9c7cc4d7ff9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# Configurar filtros de estado do documento

O Adobe Experience Manager Guides fornece o recurso para pesquisar um arquivo com base em seu estado de documento atual. Você pode usar a pesquisa de filtro para pesquisar arquivos na interface do repositório para procurar arquivos.

Execute as seguintes etapas para configurar os filtros de estado do documento:

1. Faça logon no Adobe Experience Manager como Administrador.
1. Selecione o link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e selecione **Perfis de Pasta**.
1. Abra o bloco **Perfil Global**. Você também pode selecionar um bloco de perfil de pasta específico se quiser que essas alterações sejam aplicadas somente a essa pasta, em vez de globalmente.
1. Navegue até **Configuração do Editor de XML**.
1. Selecione o ícone **Editar** na parte superior.
1. Selecione o ícone **Baixar** para baixar o arquivo `ui\_config.json` no sistema local.
No arquivo `ui\_config.json` baixado, consulte a seguinte seção:

       &quot;
       &quot;repositoryFilters&quot;: [
       {
       &quot;título&quot;: &quot;Estado do documento&quot;,
       &quot;propriedade&quot;: &quot;jcr:content/metadata/docstate&quot;,
       &quot;filhos&quot;: [
       {
       &quot;título&quot;: &quot;Rascunho&quot;,
       &quot;valor&quot;: &quot;Rascunho&quot;
       ,
       {
       &quot;título&quot;: &quot;Editar&quot;,
       &quot;valor&quot;: &quot;Editar&quot;
       ,
       {
       &quot;title&quot;: &quot;Em revisão&quot;,
       &quot;valor&quot;: &quot;Em revisão&quot;
       ,
       {
}       &quot;título&quot;: &quot;Aprovado&quot;,
       &quot;valor&quot;: &quot;Aprovado&quot;
       ,
       {
       &quot;título&quot;: &quot;Revisado&quot;,
       &quot;valor&quot;: &quot;Revisado&quot;
       ,
       {
       &quot;título&quot;: &quot;Concluído&quot;,
       &quot;valor&quot;: &quot;Concluído&quot;
       
       ]
       
       ]
       &quot;
   Este trecho representa os filtros de estado de documento padrão disponíveis no Experience Manager Guides.

1. Você pode personalizar os valores de filtro com base no fluxo de trabalho da sua organização. Por exemplo, para adicionar um estado de documento personalizado **Pendente**, insira a seguinte entrada em `children`:

   ```
   {
       "title": "Pending",
       "value": "Pending"
   }
   ```

1. Depois de atualizado, salve o arquivo e faça upload dele.

Os filtros configurados são exibidos no painel **Filtros** em Repositório, na Home page.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
