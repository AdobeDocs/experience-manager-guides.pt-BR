---
title: Personalizar editor da Web
description: Saiba como personalizar a exibição de tabelas coladas no Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 839128b4-4889-4c61-b1c0-214ba1d3165e
TQID: https://experienceleague.adobe.com/0g3LyLfKxZEbtl968wJK6r1xPHRjagayeBF4xSvJF6c
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 223
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
