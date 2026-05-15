---
title: Outros recursos nos editores de mapa
description: Descubra alguns recursos comuns nos Editores de mapa básico e avançado. Saiba como resolver referências principais no Editor de mapa.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: d6e00884-e17c-499e-9568-0807a75051ad
TQID: https://experienceleague.adobe.com/tAzYI5Pxc6SkzgksjL3mFAQHY01YtejwTrU6vHW5vMc
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 467
ht-degree: 0%

---

# Outros recursos nos editores de mapa {#id1942D0T0HUI}

Alguns recursos comuns nos Editores de mapa básico e avançado são:

## Resolver referências de chave {#id176GD01H05Z}

Uma referência de chave de conteúdo DITA ou `conkeyref` é um mecanismo para inserir uma parte do conteúdo de um tópico em outro. Esse mecanismo usa a chave para localizar o conteúdo a ser reutilizado, em vez do mecanismo de referência direta de conteúdo. Para obter mais informações sobre referências diretas e indiretas no DITA, consulte *Endereçamento DITA* na Especificação de Linguagem OASIS DITA.

Se o tópico DITA tiver referências-chave associadas, elas precisarão ser resolvidas antes de visualizar, editar ou revisar um tópico.

As referências principais são resolvidas com base no mapa raiz definido na seguinte ordem de prioridade:

1. Preferências de usuário
1. Painel Exibição de mapa
1. Perfil da pasta

O mapa raiz selecionado nas Preferências do usuário tem a precedência mais alta para resolver referências principais seguidas pelo painel Exibição de mapa e pelo mapa raiz do Perfil de pasta. Portanto, se nenhum mapa estiver definido nas Preferências do usuário, o mapa aberto no painel Exibição de mapa será usado. Se nenhum mapa for aberto no painel Exibição de mapa, o conjunto de mapas nos Perfis de pasta será usado para resolver as referências principais.

As referências de chave podem ser armazenadas em um arquivo de mapa DITA ou em um arquivo DITA separado. No AEM Guides, você pode especificar referências principais no nível do projeto ou no nível de uma sessão. Se um mapa raiz já estiver definido para a sessão do usuário, ele será usado para resolver as chaves. Caso contrário, o mapa raiz padrão para essa pasta será usado. Caso um mapa raiz padrão não esteja configurado, as referências de chave ausentes são realçadas para o usuário.

Há várias maneiras de resolver referências principais em um tópico DITA definindo o mapa DITA a ser usado nos seguintes locais:

**Propriedades do projeto** - Você pode definir um mapa raiz para resolver referências principais ao criar um Projeto na seção Propriedades do Projeto.

Esse mapa raiz será aplicável a todos os ativos \(pastas e subpastas\) associados a esse projeto. Para um conteúdo referenciado em vários projetos, uma lista em ordem alfabética de projetos é mantida e o mapa raiz padrão associado ao primeiro projeto é usado. Você também pode escolher o mapa DITA a ser usado na lista para resolver referências principais.

**Visualização do tópico** - No modo de visualização do tópico, clique no ícone Resolução de Chave na barra de ferramentas e selecione o arquivo DITA a ser usado para as referências de chave.

**Modo de exibição de edição de tópico** - Clique no ícone Resolução de Chave ao editar um tópico DITA e selecione o arquivo DITA a ser usado para resolver as referências de chave.

**Tópico pai:**[ Trabalhar com o Editor de Mapa](map-editor.md)
