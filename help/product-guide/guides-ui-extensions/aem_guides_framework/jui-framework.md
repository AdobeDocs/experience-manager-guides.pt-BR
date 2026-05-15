---
title: Estrutura Jui
description: Noções Básicas Sobre A Estrutura Jui
role: User, Admin
exl-id: c193cf90-5916-4d8c-88f1-be5014beca1c
TQID: https://experienceleague.adobe.com/AQFEy2bHTDHXq6QH8KTBOEzUvtA3Hf2ojhxvD0dsI7o
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 1%

---

# Estrutura Jui

Antes de entrar em como escrever extensões, entenderemos a arquitetura da estrutura.
Para que possamos estendê-la efetivamente.

## Introdução

A JUI é uma estrutura MVC sobre componentes do React e do Adobe React Spectrum. A JUI é a interface do usuário JSON. Ele consiste em vários repositórios Git.

JUI-Core é a biblioteca principal com toda a lógica para converter a configuração JSON em componentes de reação em funcionamento e vinculá-la a uma instância de classe de controlador relevante.
A biblioteca JUI-React-Spectrum tem widgets de wrapper dos componentes do Adobe React Spectrum

## Design de núcleo JUI

### Design da interface do MVC

![Fluxo MVC da interface do usuário](./imgs/jui-mvc-flow.png)

### Widget

- Tem um identificador exclusivo.
- Tem um arquivo JSON individual para exibição.
- Pode ter um Controlador próprio ou compartilhado.
- Pode usar modelo principal ou novo modelo.
- Pode ter elementos de interface do usuário (Componentes do React)
- Pode ter outros widgets
- O aplicativo é um widget

![Widget de JUI](./imgs/jui-widget.png)

### Elemento

- É um componente do HTML/React.
- Não tem nenhum modelo, o usa um modelo de widget principal.

### Manipulador de eventos

- Next(eventOpts)
   - Para acionar um evento com algumas opções
- Assinar (retorno de chamada)
   - Obter notificação de que o evento é acionado com configuração

### Modelo global/aplicativo

- Next(novo valor)
   - Para publicar o novo valor
- Assinar (retorno de chamada)
   - Para obter notificação sobre a alteração de valor
   - Primeira vez que obter valor antigo
- GetValue()
   - Para obter o valor atual

### Controlador

- Ele deve ser estendido da classe Controller
- APIs
- CriarModelo
   - Para criar um modelo separado do widget filho
- InitEventHandler
   - Para criar um manipulador de eventos separado por widget filho
- RegisterCommands
   - Para registrar eventos locais, principais ou de aplicativos
- Next(eventName, eventHandler)
   - Para acionar um evento do manipulador de eventos do widget filho, do manipulador de eventos do widget pai ou do manipulador de eventos do aplicativo
- Subscribe(retorno de chamada, eventHandler)
- SubscribeAppModel(callback)

### Exemplo de design do aplicativo

![Aplicativo de Exemplo](./imgs/jui-sample-app.png)
