---
title: Configurar o número de LimitReads para uma consulta
description: Saiba como Configurar o número de LimitReads para uma consulta
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 2%

---

# Configurar o número de LimitReads para uma consulta {#id231RC0HL0ID}

Para aumentar o número de nós que uma consulta pode ler de cada vez, execute as seguintes etapas:

1. Abra a página JMX do console da Web da Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Procure por e clique em **QueryEngineSettings**.

1. Alterar valor de atributo para o **LimitReads** atributo.

1. Clique em **Salvar**.


Quando você aumenta esse valor de atributo, ele ajuda a gerar o relatório para mapas DITA maiores.

**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
