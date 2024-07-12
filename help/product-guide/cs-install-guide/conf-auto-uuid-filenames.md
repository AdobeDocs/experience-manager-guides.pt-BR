---
title: Configurar nomes de arquivo automáticos com base no UUID
description: Saiba como Configurar nomes de arquivo automáticos com base na UUID
exl-id: bdbdf119-b928-4ed2-bab3-d99370da8aa9
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---

# Configurar nomes de arquivo automáticos com base no UUID {#id205QG070D5Z}

Por padrão, quando um tópico ou arquivo de mapa é criado, os autores têm a opção de especificar também o nome do arquivo. Os autores podem atribuir os nomes de arquivo de acordo com seus requisitos. No entanto, isso pode gerar inconsistência e uma grande variedade de nomes de arquivos pode ser vista em um grande sistema de documentação. Como administrador, você pode impedir que seus autores atribuam nomes de arquivos aos arquivos que eles criam em seu sistema. Para cada novo tópico ou arquivo de mapa, você pode optar por atribuir nomes de arquivo baseados em UUID automaticamente.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar nomes de arquivo automáticos com base na UUID:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Booleano \(true/false\).<br> **Valor padrão**: falso |

>[!NOTE]
>
> Quando essa opção estiver ativada, os autores não verão a opção para especificar o nome do arquivo ao criar um novo tópico ou arquivo de mapa. Um novo tópico ou arquivo de mapa pode ser criado na interface do usuário do Assets e no Editor da Web.

**Tópico pai:**[ Configurar nomes de arquivo](conf-file-names.md)
