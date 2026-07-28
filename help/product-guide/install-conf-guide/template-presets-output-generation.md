---
title: Predefinições de modelo para geração de saída
description: Saiba mais sobre como criar e usar predefinições de modelo para geração de saída no Adobe Experience Manager Guides.
source-git-commit: 0107a693c6d07c84f20dad7a9ffb53e8cb888d08
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 1%

---


# Configurar predefinições do modelo para geração de saída

>[!NOTE]
>
> A predefinição de modelo está disponível no Experience Manager Guides as a Cloud Service a partir da versão 2026.08.0. Entre em contato com a equipe de Sucesso do cliente para habilitar esse recurso.

As predefinições de modelo permitem que os administradores padronizem configurações de predefinição de saída em vários mapas DITA. Em vez de configurar a mesma predefinição de saída individualmente para cada mapa, você pode definir uma predefinição como modelo e aplicá-la a todos os mapas associados a um perfil de pasta.

Esse recurso ajuda a manter configurações de publicação consistentes em todos os projetos e reduz o esforço manual de configuração.

## Benefícios

O uso de predefinições de modelo oferece as seguintes vantagens:

- Garante configurações de publicação consistentes em vários mapas.
- Reduz o esforço manual, eliminando configurações predefinidas repetitivas.
- Permite o gerenciamento centralizado das configurações de predefinição de saída.

## Tipos de saída compatíveis

As predefinições de modelo são compatíveis com todos os tipos de predefinição de saída, exceto os seguintes:

- Edge Delivery Services
- Knowledge Base
- SCORM

## Criar e gerenciar predefinição de modelo

>[!NOTE]
>
> - As predefinições de modelo só podem ser criadas e gerenciadas por **Administradores** e **Administradores de Perfil de Pasta**.
> - As predefinições de modelo são destinadas ao gerenciamento de configuração e não são usadas diretamente para a geração de saída.

1. Configure o Perfil de pasta que deseja usar para as pastas.
2. Abra **Predefinições de saída** no console Mapa para a pasta associada.
3. Crie ou selecione a predefinição de saída que deseja usar como modelo.

   >[!NOTE]
   >
   > Ao criar ou selecionar a predefinição de saída que deseja usar como modelo, verifique se ela foi adicionada ao perfil da pasta atual.

4. Selecione o **Definir como modelo** no menu **Opções** para a predefinição.

   ![](assets/template-preset.png){width="650"}

   A predefinição de saída selecionada é convertida em uma predefinição de modelo. As predefinições de modelo são identificadas por um ícone de modelo, que as distingue das predefinições comuns. Para remover o status do modelo, selecione **Cancelar Definição como Modelo** no menu **Opções** da predefinição de modelo a qualquer momento.

   ![](assets/unset-as-template.png){width="650"}

5. Selecione **Aplicar Alterações de Predefinição** no menu **Opções** da predefinição de modelo para aplicar as configurações de predefinição atualizadas a todos os mapas existentes no perfil de pasta selecionado.

   A caixa de diálogo **Aplicar alterações predefinidas** é aberta.

   ![](assets/apply-preset-change.png){width="350"}

6. Para substituir a predefinição existente, marque a caixa de seleção **Substituir predefinição existente** e selecione **OK**. A substituição atualiza a predefinição, mas não modifica as configurações de Linha de base, Predefinição de condição, DITAVAL, Lista de tópicos ou Contexto de publicação na predefinição de destino. Essas configurações permanecem inalteradas.

   Uma caixa de diálogo **Confirmar Ação** é aberta, indicando a quantos mapas as alterações predefinidas se aplicam.

   ![](assets/confirm-preset-change.png){width="350"}

7. Selecione **OK**.

As alterações são aplicadas a todas as predefinições em todos os mapas nas pastas associadas.

>[!NOTE]
>
> Ao criar um novo mapa na pasta associada, a cópia local da predefinição de modelo também estaria disponível para esse mapa recém-criado.


## Comportamento de geração de saída

As predefinições de modelo são modelos de configuração e não se destinam à publicação direta. Quando uma predefinição é marcada como modelo:

- Gerar saída não está disponível.
- A predefinição de modelo não pode ser usada para publicação.
- As saídas geradas existentes para a predefinição do modelo permanecerão acessíveis se tiverem sido criadas antes de a predefinição ser convertida em um modelo.



