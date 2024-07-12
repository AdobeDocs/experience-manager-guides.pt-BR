---
title: Excluir parágrafos dentro de um tópico da tradução
description: Como excluir da tradução parágrafos dentro de um tópico
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '148'
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
