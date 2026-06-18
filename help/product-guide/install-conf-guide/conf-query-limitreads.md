---
title: Configurar o número de LimitReads para uma consulta
description: Saiba como Configurar o número de LimitReads para uma consulta
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 53748636-f3d1-4b3b-a772-2730b78741cb
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 2%

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

**Tópico pai:**[ Personalizar editor](customize-overview.md)
