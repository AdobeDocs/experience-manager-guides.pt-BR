---
title: Personalizar editor da Web
description: Saiba como personalizar a exibição de tabelas coladas no Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: d03ac6ba3ec8e5c52c31a3239e2043bbae79622e
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Configurar exibição de tabelas coladas

Usando a barra de ferramentas secundária no Editor, você pode inserir uma tabela simples no local válido atual ou próximo de um tópico. Você também pode copiar uma tabela do Microsoft Word ou Excel e colá-la diretamente em um arquivo de tópico.

Os administradores podem configurar como as tabelas copiadas serão exibidas. Por padrão, essas tabelas copiadas são exibidas como `simpletable` no editor. No entanto, você pode alterar essa configuração para exibir tabelas copiadas como `tgroup` atualizando a configuração Configuração do Editor de XML.

>[!NOTE]
>
> Se você copiar uma tabela com linhas ou colunas mescladas, a tabela será colada como tabela normal `trgoup` e não `simpletable` independentemente da configuração de tabela definida na Configuração do Editor XML.

Para atualizar o formato de tabela padrão, execute as seguintes etapas:

1. Abra a página Navegações do Adobe Experience Manager e selecione **Ferramentas** à esquerda.
2. No painel Ferramentas, selecione **Guias** na lista de ferramentas.
3. Selecione **Perfis de Pasta** e selecione o perfil no qual deseja atualizar a configuração da tabela.
4. Navegue até a guia **Configuração do editor XML**.
5. Selecione o ícone **Editar** na parte superior.
6. Selecione o ícone **Baixar** para baixar o arquivo `ui_config.json` no sistema local.
7. No arquivo `ui_config.json`, atualize a configuração `simpletable` conforme mostrado abaixo:

   ```
   "htmlToDitaMapping":{ "table": {
   "name" : "tgroup",
   "wrapTag" : {
       "dita" : "table",
       "html" : "div"
   }
   } },
   ```


Depois de atualizado, salve o arquivo e faça upload dele.

