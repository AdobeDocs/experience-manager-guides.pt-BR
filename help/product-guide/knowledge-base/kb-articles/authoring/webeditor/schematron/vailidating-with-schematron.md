---
title: Suporte a schematron no webeditor
description: Trabalhar com o Schematron no webeditor
exl-id: 3e61432f-d81e-446e-b0ad-560f5b9fa91a
feature: Web Editor
role: User, Admin
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Controle da qualidade do conteúdo no editor da Web

Este artigo fornece uma visão geral das possibilidades de validação no editor da Web do AEM Guides.
Por design, o editor da Web aproveita a configuração do esquema DITA no sistema para forçar os usuários a criar conteúdo compatível com DITA. Com isso, todo o conteúdo armazenado no sistema é estruturado, reutilizável e válido conteúdo DITA.

Além do suporte para regras DITA, o editor da Web também oferece suporte à validação de conteúdo com base nas regras &quot;*Schematron*&quot;.

&quot;*Schematron*&quot; refere-se a uma linguagem de validação baseada em regras usada para definir testes para um arquivo XML. É possível importar os arquivos do Schematron e editá-los no Editor da Web. Usando um arquivo de &quot;Esquematron&quot;, você pode definir determinadas regras e validá-las para um tópico DITA ou um mapa. As regras de esquema podem garantir a consistência da estrutura XML, impondo restrições definidas como regras. Estas restrições são impostas por PME que detêm a qualidade e a coerência do conteúdo.

OBSERVAÇÃO: o editor da Web é compatível com o Schematron ISO.


## Saber como o &quot;Schematron&quot; funciona no editor da Web

### Configuração de regras do Schematron

Consulte a seção &quot;Suporte para arquivos do Schematron&quot; no [Guia do Usuário](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=148)


### Aplicar regras de validação ao salvar arquivo

As configurações do Editor da Web permitem que os usuários avançados configurem regras/arquivos de esquema que serão executados sempre que um usuário atualizar o conteúdo. Para obter mais detalhes, consulte a seção &quot;Validação&quot; no [Guia do Usuário](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=58)

![Definir regras nas configurações do editor da Web](../../../assets/authoring/schematron-editorsettings-validation-tab.png)


### Você pode executar a validação manualmente?

Sim, como autor/usuário ao criar conteúdo, você pode usar o painel Esquematron no editor da Web para fazer upload de um arquivo de esquematron e executar validações no arquivo aberto no editor.

Para que isso funcione, o administrador de perfil da pasta deve permitir que todos os usuários adicionem arquivos Schemtron no painel Validação. Ver configurações do editor (captura de tela acima)

![Escolher arquivo do Schematron](../../../assets/authoring/schematron-rightpanel-validation-addsch.png)
![Executar validação](../../../assets/authoring/schematron-rightpanel-validation-runsch.png)


### Regras compatíveis

A versão atual da validação de suporte do AEM Guides usa somente regras baseadas em &quot;Asserção&quot;. (consulte [ativo vs. relatório](https://schematron.com/document/205.html))
Quaisquer regras baseadas em &quot;Relatórios&quot; ainda não são compatíveis.


### Exemplos e mais ajuda sobre as regras do Schematron

#### Casos de uso de exemplo

- Verifique se um link é externo e se tem escopo &quot;externo&quot;

  ```
  <sch:pattern>
      <sch:rule context="xref[contains(@href, 'http') or contains(@href, 'https')]">
          <sch:assert test="@scope = 'external' and @format = 'html'">
              All external xref links must be with scope='external' and format='html'
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- Verifique se há pelo menos um &quot;topicref&quot; em um mapa ou pelo menos um &quot;li&quot; em um &quot;ul&quot;

  ```
  <sch:pattern>
      <sch:rule context="map">
          <sch:assert test="count(topicref) > 0">
              There should be atleast one topicref in map
          </sch:assert>
      </sch:rule>
  
      <sch:rule context="ul">
          <sch:assert test="count(li) > 1" >
              A list must have more than one item.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- O elemento &quot;indexterm&quot; deve estar sempre presente em um &quot;prólogo&quot;

  ```
  <sch:pattern>
      <sch:rule context="*[contains(@class, ' topic/indexterm ')]">
          <sch:assert test="ancestor::node()/local-name() = 'prolog'">
              The indexterm element should be in a prolog.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

#### Recursos

- Noções básicas sobre o [Schematron](https://da2022.xatapult.com/#what-is-schematron)
- Mais sobre [Regras de asserção no Esquematron](https://www.xml.com/pub/a/2003/11/12/schematron.html#Assertions)
- [Arquivo de exemplo do Schematron](../../../assets/authoring/sample_schematron.sch)
