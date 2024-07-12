---
title: Notas de versão | Instruções de atualização e problemas corrigidos na versão Adobe Experience Manager Guides 4.3.0
description: Saiba mais sobre as correções de erros e como atualizar para as versões 4.3.0 do Adobe Experience Manager Guides
exl-id: 7fb568a0-0b88-4ea0-9b79-2625336348ff
feature: Release Notes
role: Leader
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 1%

---

# Versão 4.3.0 do Adobe Experience Manager Guides (julho de 2023)

Esta nota de versão aborda as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos na versão 4.3.0 do Adobe Experience Manager Guides (mais tarde conhecido como *AEM Guides*).

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 4.3.0 do Adobe Experience Manager Guides](./whats-new-4-3-release.md).

## Atualização para a versão 4.3.0 do AEM Guides


Você pode atualizar facilmente sua versão atual do AEM Guides para a versão 4.3.0. Antes de continuar com a atualização para a versão 4.3.0 do AEM Guides, considere os seguintes pontos:
Você pode atualizar sua versão atual do AEM Guides para a versão 4.3.0

- Se você estiver usando a versão 4.2 ou 4.2.x, é possível atualizar diretamente para a versão 4.3.0.
- Se você estiver usando a versão 4.1 ou 4.1.x, será necessário atualizar para a versão 4.2 ou 4.2.x antes de atualizar para a versão 4.3.0.
- Se você estiver usando a versão 4.0, será necessário atualizar para a versão 4.2 antes de atualizar para a versão 4.3.0.
- Se você estiver usando a versão 3.8.5, será necessário atualizar para a versão 4.0 antes de atualizar para a versão 4.2.
- Se você estiver em uma versão anterior à 3.8.5, consulte a seção Atualizar o AEM Guides no guia de instalação específico do produto.



>[!NOTE]
>
>Você deve instalar o service pack AEM antes de atualizar a versão do AEM Guides.

Para obter detalhes, consulte [Instruções de atualização](../install-guide/upgrade-xml-documentation.md).

## Matriz de compatibilidade

Esta seção lista a matriz de compatibilidade para os aplicativos de software compatíveis com a versão AEM Guides 4.3.0.

### Adobe Experience Manager

**4.3.0 Não UUID**
Versão 6.5 Service Pack 18, 17, 16, 15 ou 14

**4.3.0 UUID**
Versão 6.5 Service Pack 18, 17, 16, 15 ou 14

Para obter mais detalhes, consulte a seção *Requisitos técnicos* no guia Instalar e configurar o Adobe Experience Manager Guides.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versão | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.0 (Não UUID) | 2022 ou superior | 2020.2 ou superior* | 2022 ou superior | 2020.3 ou superior |
| 4.3.0 (UUID) | 2022 ou superior | 2020.2 ou superior* | 2022 ou superior | 2020.4 ou superior |
| | | | |

*A linha de base e as condições criadas no AEM são compatíveis com as versões do FMPS a partir de 2020.2.

### Conector de oxigênio

| Versão | Janelas do conector Oxygen | Conector Oxygen Mac | Editar no Oxygen Windows | Editar no Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.0 (Não UUID) | 2.3-regular-5 | 2.3-regular-5 | 1,6 | 1,6 |
| 4.3.0 (UUID) | 3.0-uuid-4 | 3.0-uuid-3 | 2,3 | 2,3 |
|  |  |   |

## Problemas corrigidos

Os bugs corrigidos em várias áreas estão listados abaixo:

### Criação  

- O arquivo de tópico não está desbloqueado no Editor da Web, embora as opções Desbloquear o arquivo e Não salvar estejam selecionadas. (12558)
- Não é possível fazer check-out de um arquivo no Editor da Web, apesar de escolher a opção NÃO para descartar as alterações antes do check-in. (12557)
- As dicas de ferramentas para os ícones Bloquear e Desbloquear arquivo na barra de ferramentas principal no Editor da Web não são consistentes com os ícones exibidos na Exibição do repositório.(12555)
- A opção Cancelar check-out e Desbloquear é exibida para um arquivo no Editor da Web que ainda não foi submetido a check-out na Exibição de mapa. (12556)
- Não é possível selecionar os ativos de PDF nos links &quot;topicref&quot; existentes. (12477).
- Ao fazer uma mesclagem e divisão nas tabelas, o AEM Guides 4.2 gera células de tabela adicionais. (11793)
- Na Exibição de repositório, os tópicos ou imagens não podem ser arrastados após o uso da funcionalidade Pesquisar/Filtrar. (12396)
- Os resultados da pesquisa são desativados no painel Localizar e substituir após abrir um arquivo pesquisado. (12142)
- A tecla numérica &quot;8&quot; no teclado lateral não está funcionando no editor do AEM Guides. (12106)
- Os atributos em linha/Exibição não aparecem na exibição de layout do Editor da Web. (12498)
- A configuração da interface do usuário do perfil global não corresponde ao Perfil da pasta. (1970)
- As referências de conteúdo são quebradas quando os arquivos DITA são copiados e colados. (1959)
- Não é possível editar o fragmento de conteúdo na exibição de coluna com o AEM Guides instalado. (7342)
- O conteúdo é perdido quando uma refex não encapsulada está sob tags de um subelemento. (12532)
- O fluxo de trabalho de aprovação não funciona quando o docstate é alterado para &quot;estado final&quot; nas propriedades File do painel direito. (11026)
- Interface do usuário do ativo | Na exibição em Lista, as colunas disponíveis sobrepostas não são mescláveis. (11528)
- Keyref não foi resolvido na exibição de mapa. (11490)
- O menu superior não é exibido ao navegar pelo editor XML. (10868)
- `conref` na marca ph | A caixa de diálogo de navegação exibida está incorreta. (9481)
- Links locais para outros elementos não são resolvidos no Editor da Web. (8790)
- A função Matches() não funciona no recurso schematron. (11224)



### Gerenciamento

- O campo &quot;title&quot; nas propriedades de metadados do mapa DITA é substituído pelo elemento `<title>` para o mapa. (10702)
- Ao tentar abrir ou atualizar a versão dos tópicos na linha de base, o carregador &quot;Buscando informações do servidor&quot; é executado indefinidamente.(12478)


### Revisar

- Nova interface de revisão | As condições destacadas e mostrar ocultar funcionam de forma diferente em relação ao Editor da Web. (11628)

### Publicação

- Falha na publicação ao renomear uma predefinição de PDF nativa. (12564)
- A duplicação de um modelo de PDF nativo duplica para o local do modelo padrão em vez do local do modelo personalizado fornecido. (12563)
- PDF nativo | Os metadados de idioma não podem ser definidos no PDF gerado para estar em conformidade com a WCAG 2.0. (12407)
- A publicação no site AEM falha ao ler arquivos temporários do pod que podem ter sido atualizados ou reiniciados. (12113)
- PDF nativo | Os atributos personalizados não são propagados para o mecanismo de HTML ou PDF temporário. (DXML-12005)
- PDF nativo |  Java OutOfMemoryError ocorre ao publicar conteúdo grande. (11789)
- PDF nativo | Xref está imprimindo o conteúdo do título do tópico href em vez do rótulo Xref. (11322)
- PDF nativo | Não é possível salvar as configurações do modelo de PDF. (10751)
- PDF nativo | O texto se estende além da largura da coluna ao incluir várias xrefs. (10876)
- PDF nativo | O elemento `<note>``</note>` não gera um título de extensão extra de seu tipo. (10549)
- Saída JSON | A propriedade `fmUuid` no nó jcr:content do JSON é diferente da &quot;id&quot; dentro do JSON. (11564)
- Saída JSON | Se o mapa e o tópico com o mesmo nome de arquivo estiverem presentes, o JSON do mapa será removido. (11524)

## Problema conhecido

A Adobe identificou o seguinte problema conhecido para a versão 4.3.0 do AEM Guides:

- O layout de página comum definido no modelo Básico não é aplicado como modelo padrão.

  Solução alternativa:
Adicione o layout de página comum como capa frontal e traseira e, em seguida, ele começa a vir para cada página.
- Problema ocorre na Pesquisa do site ao pesquisar na página de saída do site AEM no AEM Service Pack 16 ou 17.

  Solução alternativa:

   1. Abrir arquivo com o caminho: `/libs/foundation/components/search/search.jsp` em `crx/de`
   1. Substituir o número de linha 234 pelo seguinte código:

      ```
      <a href="<c:url value="${hit.URL}" context="/"/>" onclick="trackSelectedResult(this, ${status.index + 1})"><%= xssAPI.filterHTML(((Search.Hit) pageContext.getAttribute("hit")).getTitle()) %></a>
      
      *(Add the missing closing anchor tag at the end).
      ```

   1. Salve o arquivo.
