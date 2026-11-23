---
title: Notas de versão | Notas de versão do Adobe Experience Manager Guides 5.2.0 Service Pack 4
description: Saiba mais sobre o processo de atualização e as correções de erros na versão 5.2.0 Service Pack 4 do Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: ad78587f55ec7190443dbbce80f596821ec41f9f
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 1%
---
# Notas de versão do 5.2.0 Service Pack 4 (novembro de 2026)

Este artigo fornece informações sobre as instruções de atualização, compatibilidade do Java SDK, problemas corrigidos e problemas conhecidos na versão 5.2.0 Service Pack 4 do Adobe Experience Manager Guides.

## Recursos do Java SDK

Use os recursos a seguir ao desenvolver plug-ins Java personalizados ou integrações com o Experience Manager Guides. Verifique se a versão do SDK corresponde à versão instalada do Experience Manager Guides.

| Versão | Versão do Java SDK | Maven Central | Referência da API Java |
|---|---|---|----|
| 5.2.0 Service Pack 4 (UUID) | 5.2.2 | [API do AEM Guides SDK 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/) | [Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) |

Para obter mais detalhes, consulte [Configurar e usar o JAR da API do repositório central Maven](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).

## Atualização para a versão 5.2.0 Service Pack 4 do Experience Manager Guides

Saiba como instalar a versão Experience Manager Guides 5.2.0 Service Pack 4.

>[!NOTE]
>
>Esta versão está disponível somente para o AEM 6.5 LTS. O service pack compatível é o AEM 6.5 LTS Service Pack 2.

### Pré-requisitos

Antes de iniciar o processo de atualização do Experience Manager Guides 5.2.0 Service Pack 4, verifique se você está usando a versão 5.2.0 Service Pack 1.

### Processo de atualização versão 5.2.0 do Service Pack 4

1. Baixe o pacote do Experience Manager Guides versão 5.2.0 Service Pack 4.
1. Carregue o pacote na sua instância usando o Gerenciador de Pacotes (`/crx/packmgr`).
1. Instale o pacote. Em seguida, verifique se os conjuntos `fmdita` retornaram ao estado **Ativo**. Você pode verificar o estado do pacote em `/system/console/bundles`.
1. Limpe o cache do navegador.

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Criação

- Ao arrastar e soltar um ativo em um mapa do painel Explorador que não foi atualizado depois que outro autor moveu esse ativo, uma referência corrompida é adicionada ao mapa. (GUIDES-57869)

### Gerenciamento de ativos

- Ao substituir um ativo não DITA existente, como uma imagem, usando a opção **Substituir arquivos existentes**, a nova versão da imagem carregada não é criada. Como resultado, a saída gerada usando a linha de base contém o ativo mais antigo. (GUIDES-59287)

- Quando um ativo não DITA, como uma imagem, que foi migrado de uma configuração não UUID para uma configuração UUID é revertido ou ramificado para outra versão, sua UUID é alterada. As referências existentes ao ativo não são mais resolvidas e a imagem aparece quebrada nos tópicos que fazem referência a ele. (GUIDES-58414)

### Publicação

- Ao publicar um mapa enquanto outros mapas estão sendo exportados, a saída usa intermitentemente um formato de imagem de qualidade inferior em vez da imagem vetorial original. (GUIDES-55221)

## Problemas conhecidos

A Adobe identificou o seguinte problema conhecido na versão 5.2.0 Service Pack 4:

- Quando você arrasta e solta um elemento em um local inválido, o Editor o move para a posição válida mais próxima, durante a qual a referência pode manter o caminho do repositório. Da mesma forma, ao substituir uma referência existente em um mapa DITA usando a função arrastar e soltar, a nova referência pode manter o caminho do repositório. (GUIDES-60688)