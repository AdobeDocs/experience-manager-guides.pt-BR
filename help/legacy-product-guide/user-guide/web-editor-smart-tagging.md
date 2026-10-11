---
title: Marcação inteligente
description: Saiba como adicionar tags inteligentes no AEM Guides. Use a ferramenta XML Keyword Extract para extrair palavras-chave relevantes.
feature: Metadata Management
role: User
hide: true
exl-id: dd5b2648-37e1-4737-bd9d-8618f735d11f
TQID: 'https://experienceleague.adobe.com/eP6k8NDSN2OAjO9JIa8qcNDDAqg2B1lpFjPzacLsG5c'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: da9cce28-0561-45e7-851e-4500741b9744
    internal-label: Metadata management
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%
---
# Marcação inteligente {#id216KH0ID0Y8}

>[!IMPORTANT]
>
> O recurso de marcação inteligente não está disponível imediatamente e requer uma implementação personalizada para a qual você precisa consultar o administrador do sistema.

O AEM Guides vem com o recurso para adicionar tags inteligentes. Você pode usar a ferramenta Extração de palavra-chave XML para extrair tags inteligentes. Essa ferramenta usa inteligência artificial para entender o conteúdo e fornecer palavras-chave relevantes. Você pode usar tags inteligentes para melhorar a otimização do mecanismo de pesquisa (SEO\) e ajudar os usuários a encontrar o conteúdo relacionado.

Execute as seguintes etapas para criar tags inteligentes:

1. Na interface do usuário do Assets, navegue até o tópico para o qual deseja criar as tags inteligentes.
1. Abra o tópico no modo de Visualização e selecione o ícone **Reprocessar Assets** na barra de ferramentas principal.
1. Selecione Extração de palavra-chave XML para extrair palavras-chave relevantes.

   ![](images/smart-tag-reprocess-asset.png){width="300"}

1. Selecione a opção Executar Pós-Processamento. Uma mensagem é exibida no início bem-sucedido da ferramenta.
1. As tags são extraídas automaticamente e podem ser vistas na página Propriedades do tópico selecionado.

   ![](images/properties-smart-tags.png){width="800"}

   >[!NOTE]
   >
   > Além de extrair as palavras-chave por meio da ferramenta XML Keyword Extract, também é possível adicionar, excluir ou personalizar as tags inteligentes na página de propriedades.


*Contate a equipe de êxito do cliente para habilitar este recurso no ambiente. Isso não é habilitado como parte do suporte pronto para uso.*

**Tópico pai:**&#x200B;[&#x200B; Gerenciar metadados](manage-metadata.md)
