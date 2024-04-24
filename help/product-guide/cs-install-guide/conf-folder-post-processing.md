---
title: Configurar nomes de arquivo
description: Saiba como desativar o pós-processamento para uma pasta carregada no Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: fedd04f4a261ec199f86cb38ecd57e76b9393ae5
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---


# Desativar pós-processamento para uma pasta

Por padrão, todos os ativos carregados são processados usando o fluxo de trabalho Atualizar ativo do DAM. Os Guias do Experience Manager executam um processamento adicional, chamado pós-processamento, como parte desse fluxo de trabalho. Isso também ajuda a gerar as UUIDs

Ao fazer upload de arquivos e pastas para o *Adobe Experience Manager Assets* também é possível desativar o pós-processamento e a geração de UUIDs.


Use as instruções em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para desativar o pós-processamento em um determinado caminho ou ignorar o pós-processamento de uma pasta:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valor da string para definir qualquer NODE_OPTIONS padrão (propriedade de vários valores, strings com caminho que omite `/` no final) <br> **Valor padrão**: `/content/dam/projects/translation_output` |


| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valor da string para definir qualquer NODE_OPTIONS padrão (propriedade de vários valores, strings com caminho que omite `/` no final) <br> **Valor padrão**: `/content/dam` |


## Regras para ativar ou desativar o pós-processamento

Por padrão, o pós-processamento é feito para cada caminho de pasta na pasta Experience Manager DAM. As configurações são aplicadas a qualquer pasta de acordo com as seguintes regras:

* Se o pai for ignorado para pós-processamento, mas a pasta filho estiver habilitada, o filho e todos os seus sucessores serão considerados habilitados.
* Se o pai estiver ativado para pós-processamento, mas o filho for ignorado, o filho e todos os seus sucessores serão considerados ignorados.
* Se o mesmo caminho de pasta existir nas configurações ignore.post.processing.paths e enabled.post.processing.paths, então ele será considerado ignorado para pós-processamento.
