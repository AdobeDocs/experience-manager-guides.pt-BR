---
title: Publicação usando o FrameMaker Publishing Server (FMPS) nos guias do AEM
description: Publicação com o FMPS usando guias do AEM
exl-id: 05d4d876-f83b-473c-bf31-14d6565e80e2
feature: AEM Guides FrameMaker Publishing Server
role: User, Admin
source-git-commit: 462647f953895f1976af5383124129c3ee869fe9
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Publicação usando o FrameMaker Publishing Server (FMPS) nos guias do AEM

A integração do AEM Guides com o FrameMaker Publishing Server pode ser a sua solução se você estiver procurando uma publicação automatizada de alta qualidade.\
O artigo ajuda na configuração e execução do FMPS com Guias AEM.

## Compatibilidade do FMPS com o Guia do AEM

- Compatibilidade com Guias AEM 4.1: [Matriz de compatibilidade 4.1](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)
- Compatibilidade com guias de AEM 4.0: [Matriz de compatibilidade 4.0](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Versão mais recente: [Informações da versão mais recente](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## Instalação

Consulte o seguinte para instalação e configuração de Guias do AEM e FMPS

### Guias do AEM

Instalação e configuração consulte: [Instalação e configurações 4.1](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

Para a instalação do FMPS, você pode consultar [Link para o YouTube](https://www.youtube.com/watch?v=2deelyM5VA8&amp;t) ou [Instalação e configuração do FMPS](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&amp;rhtocid=_2)

## Configurações necessárias

O FrameMaker Publishing Server (FMPS) pode ser usado para gerar o conteúdo DITA. O FMPS suporta uma ampla gama de formatos de saída. Modifique as seguintes propriedades do &quot;pacote com.adobe.fmdita.config.ConfigManager&quot; no Console da Web para configurar os Guias do AEM para usar o FMPS.

Para abrir o Console da Web, acesse o URL Access http://\&lt;server name=&quot;&quot;>:\&lt;port>/system/console/configMgr

**Propriedades de configuração e sua descrição** [4.1 instalação e configuração](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Executando teste:

Usando o FMPS, você pode publicar automaticamente **PDF, HTML responsivo5**, e **Epub** para seus ativos DITA e FM.

No menu &quot;Gerar PDF usando&quot;, escolha FrameMaker Publishing Server.

O usuário pode fornecer &quot;settings File(.sts)&quot; e &quot;ditaval&quot;. A filtragem é feita usando ditaval com base nas condições fornecidas.

- **Arquivo de configuração**: um arquivo de configuração FrameMaker /FMPS Publish que contém todas as configurações que você deseja que o FMPS respeite ao publicar. Por exemplo, criar saída com um modelo personalizado, criar Marcas e sangramentos (PDF) e criar PDF com índice.
- **Predefinição FMPS:** É uma combinação predefinida de arquivo de configurações e de edição. Em vez de fornecer arquivos de configurações e adicionais separados, o usuário pode pré-criar uma predefinição FMPS que pode ser reutilizada para necessidades de publicação.

**Nota:** A configuração padrão do sistema será usada pelo FMPS para publicar se você não escolher nenhuma das configurações ou da predefinição do FMPS.

É um conflito se você escolher a predefinição FMPS e também fornecer configurações personalizadas ou um arquivo diferente do AEM. Nesse caso, a predefinição FMPS tem precedência sobre as configurações personalizadas ou o arquivo condicional.

### Publicação de linha de base usando FMPS:

Você pode publicar suas linhas de base já criadas com o FMPS2020.0.2 ou versão superior.

**Exemplo de arquivo de configurações FMPS (arquivo .sts) para começar:** [Arquivo de configurações FMPS de exemplo](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (descompacte este arquivo)

## Perguntas frequentes e solução de problemas:

- ### Falha na publicação do FMPS com &quot;Exceção de tempo limite&quot;

>Verifique e aumente o valor de &quot;Tempo limite do FMPS&quot; (Segundos) em /system/console/configMgr/com.adobe.fmdita.config.ConfigManager&quot;

- ### Não é possível obter a predefinição FMPS na lista suspensa

>Verifique se você tem uma predefinição de FMPS predefinida criada no Servidor e se as configurações de conexão estão corretas.

- ### Estou recebendo PDF em branco ao publicar

>Se estiver usando UUID, verifique se você marcou a opção &quot;Usar referência baseada em UUID&quot; nas Preferências de edição do FrameMaker e vice-versa para guias AEM não UUID.

- ### Minhas configurações/adições não estão sendo aplicadas na saída final publicada

>Verifique se você não está escolhendo simultaneamente a predefinição FMPS e o arquivo de configuração/discagem. Use o FrameMaker para verificar a saída manualmente.

- ### A linha de base não está sendo publicada do FMPS

>O FMPS2020.0.2 ou versões posteriores são compatíveis com a publicação da linha de base.
>Verifique se a linha de base foi criada corretamente. Para verificar, vá para o Painel do mapa — Tópicos — Baixe o mapa e escolha &quot;Usar linha de base&quot;.
- ### Tarefas de Publicação do FMPS levam mais tempo do que outros Mecanismos

>Ao publicar do FMPS, o tempo do cabeçalho fixo ideal é de aproximadamente 3-4 minutos; se achar que é mais longo, consulte o administrador do FMPS ou entre em contato com o Suporte do Adobe.

## Outros recursos:

[Aprendizagem e suporte do FMPS](https://helpx.adobe.com/support/framemaker-publishing-server.html)

[Aprendizagem e suporte do AEM](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[FrameMaker e comunidade FMPS](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&amp;sort=latest_replies&amp;lang=all&amp;tabid=all)

[Comunidade de guias do AEM](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
