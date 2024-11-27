---
title: Use variáveis para definir as opções Caminho de destino, Nome do site ou Nome do arquivo
description: Saiba como usar variáveis para definir as opções Caminho de destino, Nome do site ou Nome do arquivo. Conhecer variáveis prontas para uso compatíveis com o AEM Guides.
exl-id: 3396c971-6332-45b5-b2ef-b07f0abf97f7
feature: Publishing
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Use variáveis para definir as opções Caminho de destino, Nome do site ou Nome do arquivo


Ao gerar saídas no site ou PDF AEM, você pode usar variáveis para definir as opções Caminho de destino, Nome do site AEM ou Nome do arquivo PDF. É possível usar uma única variável ou uma combinação de variáveis para definir essas opções.

A tabela a seguir lista as variáveis compatíveis prontas para uso:

| Variável | Caminho de destino final | Exemplo |
| --- | --- | --- |
| `${map_filename}` | Usa o nome dos arquivos de mapa DITA para criar o caminho de destino. | **Nome do arquivo de mapa DITA**:<br>`AEMGuides.ditamap`<br><br>**Caminho de Destino** configurado como:<br>`/content/output/sites/${map_filename}`<br><br>**Local de saída final**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Usa o título do mapa DITA para criar o caminho de destino. | **Nome do arquivo de mapa DITA**:<br>`AEMGuides.ditamap`<br><br>**Título do mapa DITA**:<br>`AEMGuides`<br><br>**Caminho de Destino** configurado como:<br>`/content/output/sites/${map_title}`<br><br>**Local de saída final**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Usa o nome da predefinição de saída para criar o caminho de destino. | **Nome da Predefinição de Saída**:<br>`AEM Guides PDF Output`<br><br>**Nome do arquivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Caminho de Destino** configurado como:<br>`/content/output/sites/${preset_name}`<br><br>**Local de saída final**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Usa o código do idioma em que o arquivo de mapa está localizado para criar o caminho de destino. | **Nome do arquivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Caminho do arquivo de mapa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Caminho de Destino** configurado como:<br>`/content/output/sites/${language_code}`<br><br>**Local de saída final**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Usa o caminho completo do arquivo de mapa para criar o caminho de destino.<br><br>**Nota**:Esta variável não pode ser usada para especificar o Nome do Site AEM ou o Nome do Arquivo PDF. | **Nome do arquivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Caminho do arquivo de mapa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Caminho de Destino** configurado como:<br>`/content/output/sites/${map_parentpath}`<br><br>**Local de saída final**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Usa o caminho do arquivo de mapa após a pasta de idioma para criar o caminho de destino.<br><br>**Observação**: esta variável não pode ser usada para especificar o Nome do Site AEM ou o Nome do Arquivo PDF. | **Nome do arquivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Caminho do arquivo de mapa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Caminho de Destino** configurado como:<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Local de saída final**:<br>`/content/output/sites/user-guide/SampleDita.html` |
| `${system_date}` | Usa a data atual do servidor para criar o caminho de destino. | **Nome do arquivo de mapa DITA**: <br> `SampleDita.ditamap` <br><br> **Caminho do arquivo de mapa DITA:** <br> `/content/dam/projects/AEM-Guides/en/user-guide/` <br><br> **Caminho de Destino** configurado como: <br> `/content/output/sites/${system_date}` <br> <br> **Local de saída final:** <br> /`content/output/sites/08252023/SampleDita.html` |
| `${system_time}` | Usa a hora atual do servidor para criar o caminho de destino. | **Nome do arquivo de mapa DITA:** <br>`SampleDita.ditamap` <br> <br> **Caminho do arquivo de mapa DITA:** <br>`/content/dam/projects/AEM-Guides/en/user-guide/` <br><Br>**Caminho de Destino** configurado como: <br> `/content/output/sites/${system_time}`<br><br>**Local de saída final:**<br>`/content/output/sites/055612/SampleDita.html` |

Além disso, também é possível usar os metadados definidos para o mapa DITA ou arquivo de mapa como variáveis. Os metadados podem ser encontrados no nó `/jcr:content/metadata` do mapa DITA ou do arquivo de mapa. Por exemplo, uma das propriedades de metadados definidas no nó `/jcr:content/metadata` é `dc:title`. Você pode especificar `${dc:title}` e o valor do título é usado na saída final.
**Tópico pai:**[ Geração de saída](generate-output.md)
