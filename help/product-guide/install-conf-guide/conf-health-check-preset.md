---
title: Configurar predefinições de verificação de integridade
description: Saiba como configurar predefinições de verificação de integridade no perfil global ou de nível de pasta para que os autores e editores possam executar verificações de integridade em um mapa DITA.
feature: Web Editor Configuration
role: Admin
level: Experienced
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
source-wordcount: '431'
ht-degree: 0%
---
# Criar e gerenciar predefinições de verificação de integridade

>[!NOTE]
>
> Esse recurso é ativado por padrão. Se preferir não usar esse recurso em seu ambiente, entre em contato com a equipe de Sucesso do cliente.

Como administrador, você pode configurar o recurso de verificação de integridade em um nível de perfil de pasta no Experience Manager, permitindo que Autores e Editores executem verificações de integridade em um mapa DITA. Isso inclui a detecção antecipada de problemas como links com falha, IDs duplicadas e falhas de validação de Schematron em um mapa antes da publicação, em vez de verificar cada arquivo individualmente. As verificações executadas são definidas por uma predefinição de verificação de integridade, um conjunto de regras que os autores e editores podem selecionar e executar.

Este artigo fornece informações sobre como criar e gerenciar predefinições de verificação de integridade.

## Criar uma predefinição de verificação de integridade

Execute as seguintes etapas para criar uma predefinição de verificação de integridade em nível de perfil de pasta:

1. Vá para [configurações do Workspace](./workspace-settings.md) e selecione **Verificação de integridade** na lista.
1. No painel **Predefinições de verificação de integridade**, selecione **Novo**.

   ![](./assets/health-check-preset-create.png)
1. A caixa de diálogo **Nova predefinição de verificação de integridade** é exibida. Adicione um nome predefinido e selecione as regras ou verificações que deseja incluir - as opções disponíveis são Links desfeitos, IDs duplicadas e Validações de esquema.

   ![](./assets/health-check-preset-dialog.png)
1. Selecione **Criar**.
1. Selecione **Salvar** para salvar a configuração.

Essa predefinição agora está disponível para Autores e Editores. Para Autores, o recurso está disponível no menu Opções de um mapa na exibição Mapa e no painel Relatório de verificação de integridade ao lado do painel Pesquisar, permitindo que eles executem uma verificação de integridade no mapa selecionado usando uma das predefinições de verificação de integridade configuradas para seus perfis. Para obter detalhes, exiba [recursos adicionais no Editor de mapa](../user-guide/map-editor-other-features.md#run-health-check-on-a-map).

Para Editores, a opção **Executar verificação de integridade antes da geração de saída** é exibida no painel predefinido, que eles podem habilitar ou desabilitar de acordo com o requisito. Quando ativado, o relatório de verificação de integridade é anexado aos logs no início do processo de publicação, mas não bloqueia a geração de saída.

## Gerenciar predefinições de verificação de integridade

Depois de criada, a predefinição é adicionada ao painel Predefinições de verificação de integridade, onde é possível executar as operações de edição, duplicação ou remoção na predefinição.

![](./assets/health-check-preset-manage.png)

- **Editar**: permite editar campos predefinidos, como o nome da predefinição, as verificações (selecionar ou desmarcar verificações) e adicionar ou remover arquivos de Esquematron anexados à predefinição.
- **Duplicar**: cria uma duplicata da predefinição na mesma lista.
- **Remover**: remove a predefinição do painel.

Selecione **Salvar** para salvar suas alterações.
