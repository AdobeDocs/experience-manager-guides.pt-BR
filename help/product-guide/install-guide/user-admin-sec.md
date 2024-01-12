---
title: Administração e segurança do usuário
description: Saiba como a administração de usuários e a segurança funcionam
exl-id: 1269a652-5261-413d-9ea0-b4f75003e9d8
feature: User Management
role: Admin
level: Experienced
source-git-commit: 462647f953895f1976af5383124129c3ee869fe9
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 10%

---

# Administração e segurança do usuário {#id181AED00G5Z}

Para acessar e configurar recursos nos Guias do AEM, é necessário criar usuários. Esses usuários podem receber permissões para acessar todos os recursos ou recursos específicos nos Guias AEM. Saiba como configurar e manter a autorização do usuário e também entenda a teoria por trás de como a autenticação e a autorização funcionam no AEM.

Os seguintes tópicos na documentação do AEM ajudarão você a entender a administração do usuário e os conceitos e recursos relacionados à segurança:

- [Usuários e grupos no AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#UsersandGroupsinAEM)

- [Permissões no AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#PermissionsinAEM)

- [Gerenciar usuários e grupos](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingUsersandGroups)

- [Gerenciamento de permissões](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingPermissions)


## Grupos de usuários criados pelos Guias do AEM {#id181TF0K0MHT}

O Guias do AEM fornece três grupos prontos para uso para gerenciar tarefas diferentes em um projeto DITA. Esses grupos são: *Autores*, *Revisores*, e *Editores*. Dependendo do grupo ao qual um usuário está associado, ele pode executar tarefas específicas. Por exemplo, a tarefa de publicação pode ser executada somente por um editor, mas não por um autor ou um revisor. Da mesma forma, um autor pode criar um novo tópico e um revisor só pode revisar um tópico.

>[!TIP]
>
> Consulte a *Permissões* no guia de Práticas recomendadas para obter as práticas recomendadas sobre a definição de permissões do usuário.

A tabela a seguir lista várias tarefas e os grupos que podem executá-las:

| Tarefa | Autores | Revisores | Editores |
|----|-------|---------|----------|
| Criar tópico DITA | Sim |   | Sim |
| Criar mapa DITA | Sim |   | Sim |
| Mapear coleções | Sim |   | Sim |
| Criar tarefa de análise | Sim |   | Sim |
| Revisar tópico[1](#fntarg_1) | Sim | Sim | Sim |
| Resolução de chave | Sim |   | Sim |
| Abrir no FrameMaker | Sim |   | Sim |
| Check-out/Check-in | Sim |   | Sim |
| Editar tópico | Sim |   | Sim |
| Mover tópico | Sim |   | Sim |
| Editar Propriedades do Tópico | Sim |   | Sim |
| Copiar | Sim |   | Sim |
| Excluir | Sim |   | Sim |
| Compartilhar | Sim |   | Sim |
| **Estado do documento** |
| Criar/editar perfil de estado do documento |   |   | Sim |
| Alterar estado do documento[2](#fntarg_2) | Sim | Sim | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Predefinições de saída\)** |
| Gerar |   |   | Sim |
| Editar |   |   | Sim |
| Duplicar |   |   | Sim |
| Criar |   |   | Sim |
| Excluir predefinição |   |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Saídas\)** |
| Exibir saída gerada | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Tópicos\)** |
| Criar tarefa de análise | Sim |   | Sim |
| Editar | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(guia Linhas de Base\)** |
| Criar |   |   | Sim |
| Editar |   |   | Sim |
| Duplicar |   |   | Sim |
| Remover |   |   | Sim |
| Console do mapa DITA \(guia Relatórios\) | Sim |   | Sim |
| **Recursos disponíveis no console de mapa DITA \(Predefinições de condição\)** |
| Criar/editar predefinição de condição |   |   | Sim |

## Observações adicionais sobre os grupos de usuários

A lista a seguir contém algumas recomendações e pontos relacionados a grupos de usuários e permissões correspondentes:

- Se quiser que um usuário inicie o fluxo de trabalho de tradução ou revisão, verifique se ele é membro da *Editores* e *grupo projetos-administradores*.

- Os usuários devem ter as permissões de leitura, criação, exclusão e modificação disponíveis nas pastas de idioma de origem e destino nas quais precisam trabalhar.

- Se criar um projeto, você será o proprietário do projeto com *Editores* permissões. Para que outros usuários em um projeto possam ver os membros da equipe, criar tarefas ou criar workflows, eles devem ter acesso de leitura em `/home/users` e `/home/groups` nós. Uma maneira de conceder acesso de leitura em `/home/users` e `/home/groups` nós é fornecendo acesso de leitura à variável `projects-users` grupo.

- *Revisores* O pode acessar e adicionar comentários de revisão em um tópico sob revisão no console Projeto ou no link de notificação da caixa de entrada. Além disso, esse acesso só estará disponível até que a tarefa de revisão esteja aberta.

- Por padrão, *Editores* recebem acesso e permissões nas seguintes pastas no DAM:

   - ``/var/dxml``-\> Leitura e gravação

   - `/content/dam/fmdita-outputs` -\> Leitura e gravação

   - `/content/output/sites` -\> Leitura e gravação

  Você deve conceder permissões explícitas de leitura e gravação ao editor se estiver usando qualquer outro local, exceto os locais de publicação padrão mencionados acima.

- Todos os usuários em *Autores*, *Revisores*, e *Editores* Os grupos têm acesso de leitura a todo o conteúdo no DAM.

- As permissões no nível da pasta devem ser atribuídas aos usuários por meio da página de administração do usuário.

- Se quiser que os usuários possam executar operações de pesquisa no DAM, torne-os membros da *dam-users* grupo.

- Se você quiser conceder direitos de administrador a qualquer usuário, é possível fazê-lo fornecendo acesso a ele por meio de grupos padrão AEM, como *administradores*, *projetos-administradores*, ou configuração OSGI \(Felix console\).

- Para conceder ao usuário direitos para alterar um estado de documento, adicione o usuário na seção transição de estado do perfil de estado do documento.

[1](#fnsrc_1) Se *Autores* e *Editores* são convidados para uma revisão.[2](#fnsrc_2) Dependendo dos direitos concedidos ao usuário no perfil de estado do documento.
