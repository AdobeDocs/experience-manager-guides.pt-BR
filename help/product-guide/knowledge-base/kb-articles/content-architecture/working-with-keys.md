---
title: Trabalhar com chaves
description: Como criar chaves para serem usadas no conteúdo da organização
role: Admin
exl-id: b8e3a6d2-ea82-4fdb-bd16-3f4b6594af52
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# Criar chaves

As organizações devem usar teclas nos casos em que têm algum texto reutilizável e comum, como nome do produto ou apresentação do produto, que é usado em muitos lugares, mas sujeito a alterações. Usar chaves para esse texto reutilizável permite enviar uma atualização em vários locais fazendo a alteração em um único local, como no valor da chave.

## Etapa 1: criar um mapa global para armazenar suas chaves

Crie um mapa e adicione o [!UICONTROL keyref] elemento a ele.

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_ffbdbf06-8658-4311-ad84-1c631bba904f">
  <title>global-keys-map</title>
  <keydefkeys="adobe">
    <topicmeta>
      <linktext>Adobe Systems</linktext>
    </topicmeta>
  </keydef>
  <keydefkeys="AEM">
    <topicmeta>
      <linktext>Adobe Experience Manager</linktext>
    </topicmeta>
  </keydef>
</map>
```

Aqui você definiu duas definições, conforme mostrado acima, fornecendo uma [!UICONTROL keyref] as _AEM_ para o _Adobe Experience Manager_ texto.

## Etapa 2: adicionar este mapa ao mapa de publicação

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_cbf4a96d-e382-4e8c-8830-bcc093fe6638">
  <title>sample-map</title>
  <topicrefhref="sample-topic-using-the-keys.dita"type="topic">
  </topicref>
  <maprefformat="ditamap"href="global-keys-map.ditamap"type="map">
  </mapref>
</map>
```

## Etapa 3: usar as chaves para se referir às variáveis definidas no mapa de chaves global

+ Edite o tópico e adicione o valor da chave usando o [!UICONTROL keyref].
+ Como mostrado na captura de tela, uma pequena janela aparecerá de onde as palavras-chave podem ser escolhidas. Isso será exibido quando você adicionar o elemento &quot;palavra-chave&quot;.
  ![Inserir elemento](assets/insert_element.png)
  ![Ref Chave](assets/key_ref.png)

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "technicalContent/dtd/topic.dtd">
<topicid="topic.dita_31b00e61-04b5-4193-af7a-68503e88b087">
  <title>sample-topic-using-the-keys</title>
  <shortdesc></shortdesc>
  <body>
    <p>This is a sample topic using the keys defined in the global map</p>
    <p>here i am using the key definition for AEM :<keywordkeyref="AEM"></keyword></p>
  </body>
</topic>
```
