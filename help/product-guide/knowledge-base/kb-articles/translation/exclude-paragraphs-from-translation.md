---
title: Excluir parágrafos dentro de um tópico da tradução
description: Como excluir da tradução parágrafos dentro de um tópico
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
TQID: https://experienceleague.adobe.com/IAY5PLpWlHEpMygjmHI-BqS75-VqAU5x1o9mdiu4Aac
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 0%

---

# Como excluir da tradução parágrafos dentro de um tópico

A maneira mais fácil é usar a tradução=sem atributo.

+ Os autores podem inserir o atributo adicional como **translation=no** nos parágrafos que não desejam traduzir. O fornecedor de tradução precisa ser informado e pode fazer a configuração ao final para ignorar o texto com esse atributo.
+ A tradução automática OOTB (com o conector de avaliação do Microsoft Translation) exibe o mesmo comportamento.
+ Teste com a Tradução do Microsoft : se você definir o atributo **translate=no** no nível de parágrafo, ele não traduzirá o parágrafo completo. Esse atributo pode ser definido em qualquer elemento e o conteúdo dentro desse elemento não será traduzido.


Veja a seguir algumas capturas de tela para explicar isso mais detalhadamente:

**Conteúdo do Source**

![Conteúdo do Source](assets/source-content.jpg)

**Conteúdo traduzido em espanhol**

![Conteúdo traduzido em espanhol](assets/trans-content.jpg)
