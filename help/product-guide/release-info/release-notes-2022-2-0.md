---
title: Notas de versão do [!DNL AEM Guides], versão de fevereiro de 2022
description: Versão de fevereiro do [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: eb7ff475-bb5b-4d32-b291-024147fbfed1
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 0%

---

# Versão de fevereiro do [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Atualização para a versão de fevereiro

Atualize seu atual [!DNL Adobe Experience Manager Guides] as a Cloud Service (mais tarde referido como [!DNL AEM Guides] as a Cloud Service) executando as seguintes etapas:
1. Confira o código Git do Cloud Service e alterne para a ramificação configurada no pipeline Cloud Service correspondente ao ambiente que você deseja atualizar.
1. Atualizar `<dox.version>` propriedade no `/dox/dox.installer/pom.xml` arquivo do seu código Git Cloud Service para 2022.2.114.
1. Confirme as alterações e execute o pipeline do Cloud Service para atualizar para a versão de fevereiro do [!DNL AEM Guides] as a Cloud Service.

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade dos aplicativos de software suportados pela [!DNL AEM Guides] Versão as a Cloud Service de fevereiro de 2022.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Não compatível | Atualização 4 e superior para 2020 |
| | |


### Conector de oxigênio

| [!DNL AEM Guides] Versão na nuvem | Janelas do conector Oxygen | Conector Oxygen Mac |
| --- | --- | --- |
| 2022.2.0 | 2.4.0 | 2.4.0 |
|  |  |  |


## Novos recursos e melhorias

### Publicação de PDF nativo

O suporte para a criação de um PDF nativo também foi adicionado na versão de fevereiro do [!DNL AEM Guides] as a Cloud Service. Um novo mecanismo de publicação foi introduzido com os seguintes recursos:
* Criar um modelo CSS
* Criar modelos de página diferentes
* Criar modelos de PDF compreendendo CSS e modelos de página
* Publicar o mapa e o conteúdo do tópico no formato PDF

### Suporte para caminho do site da base de dados de conhecimento na publicação baseada em artigo

[!DNL AEM Guides] O as a Cloud Service fornece o recurso de publicação baseado em artigos para gerar de forma incremental uma saída de um ou mais tópicos ou publicar seu conteúdo em uma plataforma da base de conhecimento. Com a versão de fevereiro, você terá uma opção adicional para escolher o caminho do site da Base de conhecimento no qual o tópico/mapa precisa ser publicado. Após selecionar o caminho, a saída é gerada no caminho especificado.

### Aprimoramentos no Editor da Web

Muitos aprimoramentos e novos recursos foram adicionados ao Editor da Web:

* **Caixa de diálogo aprimorada no fechamento do arquivo**

[!DNL AEM Guides] O as a Cloud Service solicita que você salve suas alterações e desbloqueie os arquivos bloqueados ao tentar fechar um arquivo aberto no Editor da Web. Os prompts são exibidos com base no **Solicitar check-in ao fechar** e **Solicitar nova versão ao fechar** configurações definidas pelo administrador.

Com base na configuração, você tem a opção de salvar as alterações e criar uma nova versão do documento. Ou você também pode fazer check-in do arquivo e salvar as alterações na versão atual.

![Arquivo fechar](assets/file-close-save-changes-unlock.png)

Para obter mais detalhes, consulte *Cenários de fechamento e salvamento de arquivos* no Guia do usuário.

* Um espaço sem quebra foi adicionado ao palete de caracteres.  A **não-separável** o espaço impede uma quebra de linha automática em um ponto específico de um documento HTML. O Editor da Web suporta um espaço não-separável para saída de AEM Site e HTML 5.

* Ao fazer upload de uma imagem do Editor da Web, uma caixa de diálogo de confirmação será exibida se uma imagem com o mesmo nome já existir. Você pode manter ambos os arquivos, existentes e novos, ou substituir o arquivo existente e salvar apenas o novo arquivo.

* Se qualquer usuário tiver bloqueado qualquer arquivo para edição, um administrador poderá liberar o bloqueio e fazer check-in do arquivo. Este recurso será útil quando alguns arquivos precisarem ser editados, mas tiverem sido bloqueados por usuários que não estão disponíveis para check-in no arquivo

### Mapear painel

Quando você seleciona baixar o mapa DITA, a solicitação é enfileirada e você recebe uma notificação quando o mapa estiver pronto para download. Você pode optar por baixar o arquivo de mapa imediatamente ou baixá-lo posteriormente a partir do link fornecido na Caixa de entrada de notificação do AEM.

![Download de mapa](assets/download-map-prompt.png)

### Revisar

Você pode mencionar os detalhes no campo de descrição da tarefa de revisão e eles serão exibidos no e-mail enviado ao revisor.

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Publicação baseada em artigo

* A publicação baseada em artigos não publica artigos com base na linha de base selecionada. (8771)
* Os arquivos DITAVAL não são honrados na publicação baseada em artigos. (8770)
* Não é possível fazer a publicação baseada em artigo para o perfil do Salesforce quando o tipo de registro é Perguntas frequentes e o conteúdo do campo de artigo é Pergunta. (8448)
* Não é possível fazer a publicação baseada em artigo para o perfil do Salesforce quando o tipo de registro é Manual. (8447)

### Editor da Web

* Arrastar e soltar uma condição não funciona em tópicos DITA. (8761)
* Os atributos estão ausentes ao adicionar um capítulo no bookmap usando a função Arrastar e soltar da exibição Favoritos. (8746)
* A edição das propriedades de uma imagem (altura, largura) resulta em um erro de aplicativo. (8722)
* Os links quebrados não aparecem no painel Estrutura de tópicos na exibição de origem. (8590)
* O Editor XML remove a marca de nova linha no bloco de código. (8522)
* Glossusage é mostrado como uma Nota quando um Glossentry é criado. (8384)
* xref não pode ser inserido mesmo em locais válidos. (8354)
* A lista de elementos (Alt+Enter) aparece esmaecida no tema Escuro/Escuro. (7913)
* A lista de modelos de mapa em **Criar** opção (menu reticências) do painel Repositório não é conforme a **Perfil da pasta** em Preferências do usuário. (5918)
* As IDs de elemento não são geradas automaticamente para elementos adicionados do recurso Reutilizar conteúdo da barra de ferramentas principal. (5826)

### Interface do usuário do Assets

* A edição de imagens não funciona conforme esperado no servidor de nuvem. (8768)
* No painel Histórico de versão, a seção versão atual mostra um carimbo de data e hora incorreto e modificado pelas informações. (8765)
* O upload de arquivo DITAVAL no servidor da nuvem falha quando a ferramenta de desktop AEM é usada. (8707)
* O segundo usuário administrador não pode ser adicionado como o primeiro usuário administrador a uma pasta. (8430)
* As propriedades não exclusivas de um ativo não são copiadas quando o ativo é copiado e colado. (8241)

### Alterações de usabilidade

* No painel Revisão do Editor da Web, se um nome de usuário for longo, os ícones para aceitar/rejeitar não serão exibidos claramente. (8793)
* No **Localizar e substituir** um ícone indesejado é exibido ao passar o mouse na seção de resultados. (8775)
* O ícone personalizado não é separado da propriedade e, em vez disso, o ícone padrão é exibido para os relatórios gerados usando o botão Gerar relatório. (8573)
