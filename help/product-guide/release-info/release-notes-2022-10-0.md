---
title: Notas de versão | Guias do Adobe Experience Manager as a Cloud Service, versão de outubro de 2022
description: Versão de outubro do Adobe Experience Manager Guides as a Cloud Service
exl-id: 38638080-625c-49c3-9e54-56cc23831546
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 1%

---

# Versão de outubro do Adobe Experience Manager Guides as a Cloud Service

## Atualize para a versão de outubro

Atualize seus Guias do Adobe Experience Manager atuais as a Cloud Service (mais tarde chamados de *Guias de AEM as a Cloud Service*), executando as seguintes etapas:
1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
1. Atualizar `<dox.version>` propriedade no `/dox/dox.installer/pom.xml` arquivo do seu código Git Cloud Service para 2022.10.183.
1. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de outubro do AEM Guides as a Cloud Service.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software compatíveis com os Guias do AEM as a Cloud Service na versão de outubro de 2022.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Não compatível | Atualização 4 e superior para 2020 |
| | |

*A linha de base e as condições criadas no AEM são compatíveis com as versões do FMPS a partir de 2020.2.

### Conector de oxigênio

| Versão do AEM Guides as a Cloud | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |


## Novos recursos e melhorias

O AEM Guides as a Cloud Service oferece aprimoramentos e novos recursos na versão de outubro:


### Painel Geração rápida

Agora, o AEM Guides fornece a **Geração rápida** painel que ajuda a gerar e visualizar rapidamente a saída das predefinições criadas para o mapa DITA.

![Ícone Geração rápida](assets/quick-generate-icon.png)

No **Geração rápida** é possível ver a lista de todas as predefinições de saída criadas para o mapa DITA.

![Painel Geração rápida](assets/quick-generate-panel.png)

Selecione uma ou mais predefinições e gere rapidamente a saída. Também é possível visualizar rapidamente a saída gerada para as predefinições. Uma mensagem de sucesso é exibida na geração da saída. Uma mensagem de erro será exibida se a geração de saída falhar. Você também pode exibir o log de erros para ver os detalhes do erro que ocorreu no processo de geração.


## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

* PDF nativo | Ocorre um erro ao remover tópicos somente de recursos da saída do PDF. (10554)
* PDF nativo | Keyrefs vazios são exibidos na saída do PDF. (10553)
* PDF nativo | `navtitle` para `topichead` não é respeitado. (10509)
* PDF nativo | Suporte necessário para tipos de JDK amd64. (10465)
* PDF nativo | Não é possível ocultar tópicos de destaque do índice. (10355)
* PDF nativo | Reiniciar o número da página no layout do capítulo inicia aleatoriamente a numeração a partir do final do capítulo anterior. (10154)
* Navegador Chrome | A tela está ficando em branco ao arrastar e soltar qualquer elemento da interface do usuário. Por exemplo, ao arrastar uma condição do painel Condições. (10524)
* As propriedades do nó estão sendo removidas após a operação de copiar e colar de um ativo. (10053)
* Ao clicar em  **Fechar** os usuários estavam sendo redirecionados para ativos - a experiência foi corrigida para levar os usuários à página inicial do AEM. (9654)
