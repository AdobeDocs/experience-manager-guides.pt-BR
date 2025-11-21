---
title: Administração e segurança do usuário
description: Saiba como a administração de usuários e a segurança funcionam
exl-id: 1269a652-5261-413d-9ea0-b4f75003e9d8
feature: User Management
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 10%

---

# Administração e segurança do usuário {#id181AED00G5Z}

Para acessar e configurar recursos no AEM Guides, é necessário criar usuários. Esses usuários podem receber permissões para acessar todos os recursos ou recursos específicos no AEM Guides. Saiba como configurar e manter a autorização do usuário e também entenda a teoria por trás de como a autenticação e a autorização funcionam no AEM.

Os seguintes tópicos na documentação do AEM ajudarão você a entender a administração do usuário e os conceitos e recursos relacionados à segurança:

- [Usuários e grupos no AEM](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/security.html#UsersandGroupsinAEM)

- [Permissões no AEM](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/security.html#PermissionsinAEM)

- [Gerenciando Usuários e Grupos](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/security.html#ManagingUsersandGroups)

- [Gerenciando Permissões](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/security.html#ManagingPermissions)


## Grupos de usuários criados pelo AEM Guides {#id181TF0K0MHT}

O AEM Guides fornece três grupos prontos para uso. Estes grupos são: *Autores*, *Revisores* e *Editores*. Dependendo do grupo ao qual um usuário está associado, ele pode executar tarefas específicas. Por exemplo, a tarefa de publicação pode ser executada somente por um editor, mas não por um autor ou um revisor. Da mesma forma, um autor pode criar um novo tópico e um revisor só pode revisar um tópico.

>[!TIP]
>
> Consulte a seção *Permissões* no guia de Práticas recomendadas para obter práticas recomendadas sobre a definição de permissões de usuário.

A tabela a seguir lista várias tarefas e os grupos que podem executá-las:

| Tarefa | Autores | Revisores | Editores |
|----|-------|---------|----------|
| Criar tópico DITA | Sim |   | Sim |
| Criar mapa DITA | Sim |   | Sim |
| Mapear coleções | Sim |   | Sim |
| Criar tarefa de análise | Sim |   | Sim |
| Tópico de Revisão[1](#fntarg_1) | Sim | Sim | Sim |
| Resolução de chave | Sim |   | Sim |
| Abrir no FrameMaker | Sim |   | Sim |
| Check-out/Check-in | Sim |   | Sim |
| Editar tópico | Sim |   | Sim |
| Mover tópico | Sim |   | Sim |
| Editar Propriedades do Tópico | Sim |   | Sim |
| Copiar | Sim |   | Sim |
| Excluir | Sim |   | Sim |
| Compartilhar | Sim |   | Sim |
| **Estado do documento** |  |  |  |
| Criar/editar perfil de estado do documento |   |   | Sim |
| Alterar estado do documento[2](#fntarg_2) | Sim | Sim | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Predefinições de Saída\)** |  |  |  |
| Gerar |   |   | Sim |
| Editar |   |   | Sim |
| Duplicado |   |   | Sim |
| Criar |   |   | Sim |
| Excluir predefinição |   |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Saídas\)** |  |  |  |
| Exibir saída gerada | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Tópicos\)** |  |  |  |
| Criar tarefa de análise | Sim |   | Sim |
| Editar | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Linhas de Base\)** |  |  |  |
| Criar |   |   | Sim |
| Editar |   |   | Sim |
| Duplicado |   |   | Sim |
| Remover |   |   | Sim |
| Console do mapa DITA \(guia Relatórios\) | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(Predefinições de Condição\)** |  |  |  |
| Criar/editar predefinição de condição |   |   | Sim |

## Observações adicionais sobre os grupos de usuários

A lista a seguir contém algumas recomendações e pontos relacionados a grupos de usuários e permissões correspondentes:

- Se quiser que um usuário inicie o fluxo de trabalho de tradução ou revisão, verifique se ele é membro do *grupo de editores* e *grupo de administradores de projetos*.

- Os usuários devem ter as permissões de leitura, criação, exclusão e modificação disponíveis nas pastas de idioma de origem e destino nas quais precisam trabalhar.

- Se você criar um projeto, será o proprietário do projeto com *permissões de Editores*. Para que outros usuários em um projeto possam ver os membros da equipe, criar tarefas ou criar fluxos de trabalho, eles devem ter acesso de leitura nos nós `/home/users` e `/home/groups`. Uma maneira de conceder acesso de leitura nos nós `/home/users` e `/home/groups` é concedendo acesso de leitura ao grupo `projects-users`.

- *Os revisores* podem acessar e adicionar comentários de revisão sobre um tópico sob revisão no console Projeto ou no link de notificação da caixa de entrada. Além disso, esse acesso só estará disponível até que a tarefa de revisão esteja aberta.

- Por padrão, *Editores* recebem acesso e permissões nas seguintes pastas do DAM:

   - ``/var/dxml``-\> Leitura e gravação

   - `/content/dam/fmdita-outputs` -\> Ler e Gravar

   - `/content/output/sites` -\> Ler e Gravar

  Você deve conceder permissões explícitas de leitura e gravação ao editor se estiver usando qualquer outro local, exceto os locais de publicação padrão mencionados acima.

- Todos os usuários nos grupos *Autores*, *Revisores* e *Editores* têm acesso de leitura a todo o conteúdo no DAM.

- As permissões no nível da pasta devem ser atribuídas aos usuários por meio da página de administração do usuário.

- Se você quiser que seus usuários executem operações de pesquisa no DAM, torne-os membros do grupo *dam-users*.

- Se você quiser conceder direitos de administrador a qualquer usuário, conceda a ele acesso por meio dos grupos padrão do AEM, como *administradores*, *administradores-projetos* ou a configuração OSGI \(Felix console\).

- Para conceder ao usuário direitos para alterar um estado de documento, adicione o usuário na seção transição de estado do perfil de estado do documento.

[1](#fnsrc_1) Se *Autores* e *Editores* forem convidados para uma revisão.[2](#fnsrc_2) Dependendo dos direitos concedidos ao usuário no perfil de estado do documento.
