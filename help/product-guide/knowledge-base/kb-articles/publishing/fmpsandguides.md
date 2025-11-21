---
title: Publicação usando o FrameMaker Publishing Server (FMPS) no AEM Guides
description: Publicação com FMPS usando o AEM Guides
exl-id: 05d4d876-f83b-473c-bf31-14d6565e80e2
feature: AEM Guides FrameMaker Publishing Server
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Publicação usando o FrameMaker Publishing Server (FMPS) no AEM Guides

A integração do AEM Guides com o FrameMaker Publishing Server pode ser a sua solução se você estiver procurando uma publicação automatizada de alta qualidade.\
O artigo ajuda na configuração e execução do FMPS com o AEM Guides.

## Compatibilidade do FMPS com o AEM Guides

- Compatibilidade com o 4.1 AEM Guides: [4.1 matriz de compatibilidade](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=pt-BR/#compatibility-matrix)
- Compatibilidade com o AEM Guides 4.0: [Matriz de compatibilidade 4.0](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Versão mais recente: [Informações da versão mais recente](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=pt-BR)

## Instalação

Consulte o seguinte para a instalação e configuração do AEM Guides e do FMPS

### Guias do AEM

Consulte instalação e configuração: [4.1 instalação e configurações](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

Para instalação FMPS, você pode consultar o [link do YouTube](https://www.youtube.com/watch?v=2deelyM5VA8&t) ou a [instalação e configuração do FMPS](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&rhtocid=_2)

## Configurações necessárias

O FrameMaker Publishing Server (FMPS) pode ser usado para gerar o conteúdo DITA. O FMPS suporta uma ampla gama de formatos de saída. Modifique as seguintes propriedades do &quot;pacote com.adobe.fmdita.config.ConfigManager&quot; no Console da Web para configurar o AEM Guides para usar o FMPS.

Para abrir o Console da Web, acesse o URL Access http://\&lt;server name\>:\&lt;port\>/system/console/configMgr.

**Propriedades de configuração e sua descrição** [4.1 instalação e configuração](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Executando teste:

Usando o FMPS, você pode publicar automaticamente o **PDF, o Responsive HTML5** e o **Epub** na sua Assets DITA e FM.

No menu &quot;Gerar PDF usando&quot;, escolha FrameMaker Publishing Server.

O usuário pode fornecer &quot;settings File(.sts)&quot; e &quot;ditaval&quot;. A filtragem é feita usando ditaval com base nas condições fornecidas.

- **Arquivo de configuração**: um arquivo de configuração FrameMaker /FMPS Publish que contém todas as configurações que você deseja que o FMPS respeite ao publicar. Por exemplo, criar saída com um modelo personalizado, criar Marcas e sangramentos (PDF) e criar PDF com índice.
- **Predefinição de FMPS:** É uma combinação predefinida de arquivo de configurações e adições. Em vez de fornecer arquivos de configurações e adicionais separados, o usuário pode pré-criar uma predefinição FMPS que pode ser reutilizada para necessidades de publicação.

**Observação:** a configuração padrão do sistema será usada pelo FMPS para publicar se você não escolher nenhuma das configurações ou a predefinição do FMPS.

É um conflito se você escolher a predefinição FMPS e também fornecer configurações personalizadas ou um arquivo diferente do AEM. Nesse caso, a predefinição FMPS tem precedência sobre as configurações personalizadas ou o arquivo condicional.

### Publicação de linha de base usando FMPS:

Você pode publicar suas linhas de base já criadas com o FMPS2020.0.2 ou versão superior.

**Arquivo de configurações FMPS de exemplo (arquivo .sts) para começar:** [Arquivo de configurações FMPS de exemplo](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (descompacte este arquivo)

## Perguntas frequentes e solução de problemas:

- ### Falha na publicação do FMPS com &quot;Exceção de tempo limite&quot;

>Verifique e aumente o valor de &quot;Tempo limite do FMPS&quot; (Segundos) em /system/console/configMgr/com.adobe.fmdita.config.ConfigManager&quot;

- ### Não é possível obter a predefinição FMPS na lista suspensa

>Verifique se você tem uma predefinição de FMPS predefinida criada no Servidor e se as configurações de conexão estão corretas.

- ### Estou recebendo PDFs em branco ao publicar

>Se estiver usando UUID, certifique-se de marcar &quot;Usar referência baseada em UUID&quot; nas Preferências de edição do FrameMaker e vice-versa para guias do AEM que não sejam UUID.

- ### Minhas configurações/adições não estão sendo aplicadas na saída final publicada

>Verifique se você não está escolhendo simultaneamente a predefinição FMPS e o arquivo de configuração/discagem. Use o FrameMaker para verificar a saída manualmente.

- ### A linha de base não está sendo publicada do FMPS

>O FMPS2020.0.2 ou versões posteriores são compatíveis com a publicação da linha de base.
>Certifique-se de que sua linha de base foi criada corretamente. Para verificar, vá para o Painel do mapa — Tópicos— Download  Mapeie e escolha &quot;Usar linha de base&quot;.

- ### Tarefas de Publicação do FMPS levam mais tempo do que outros Mecanismos

>Ao publicar do FMPS, o tempo do cabeçalho fixo ideal é de aproximadamente 3 a 4 minutos; se achar que é mais longo, consulte o administrador do FMPS ou entre em contato com o Suporte da Adobe.

## Outros recursos:

[Aprendizagem e Suporte do FMPS](https://helpx.adobe.com/br/support/framemaker-publishing-server.html)

[Aprendizagem e Suporte do AEM Guides](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[Comunidade FrameMaker e FMPS](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&sort=latest_replies&lang=all&tabid=all)

[Comunidade AEM Guides](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation?profile.language=pt)
