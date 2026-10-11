---
title: Personalizar editor
description: Saiba como personalizar a exibição de tabelas coladas no Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: e66c13e4-6dc0-41a0-8582-32bacec9ae6c
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%
---
# Configurar exibição de tabelas coladas para o Cloud Service

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
