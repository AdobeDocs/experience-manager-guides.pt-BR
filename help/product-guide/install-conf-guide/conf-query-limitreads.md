---
title: Configurar o número de LimitReads para uma consulta
description: Saiba como Configurar o número de LimitReads para uma consulta
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%

---

# Configurar o número de LimitReads para uma consulta no local

Para aumentar o número de nós que uma consulta pode ler de cada vez, execute as seguintes etapas:

1. Abra a página JMX do console da Web da Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Procure por e clique em **QueryEngineSettings**.

1. Altere o valor do atributo para o atributo **LimitReads**.

1. Clique em **Salvar**.


Quando você aumenta esse valor de atributo, ele ajuda a gerar o relatório para mapas DITA maiores.

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](customize-overview.md)
