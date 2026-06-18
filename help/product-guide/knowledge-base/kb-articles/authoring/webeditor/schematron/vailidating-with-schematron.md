---
title: Suporte a schematron no webeditor
description: Trabalhar com o Schematron no webeditor
exl-id: 3e61432f-d81e-446e-b0ad-560f5b9fa91a
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/gF-ylj-r-PDXduhUU-60-hiJ4UaYEdsCYTaCIyUiT0s
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 399
ht-degree: 0%

---

# Controle da qualidade do conteúdo no editor da Web

Este artigo fornece uma visão geral das possibilidades de validação no editor da Web do AEM Guides.
Por design, o editor da Web aproveita a configuração do esquema DITA no sistema para forçar os usuários a criar conteúdo compatível com DITA. Com isso, todo o conteúdo armazenado no sistema é estruturado, reutilizável e válido conteúdo DITA.

Além do suporte para regras DITA, o editor da Web também oferece suporte à validação de conteúdo com base nas regras &quot;*Schematron*&quot;.

&quot;*Schematron*&quot; refere-se a uma linguagem de validação baseada em regras usada para definir testes para um arquivo XML. É possível importar os arquivos do Schematron e editá-los no Editor. Usando um arquivo de &quot;Esquematron&quot;, você pode definir determinadas regras e validá-las para um tópico DITA ou um mapa. As regras de esquema podem garantir a consistência da estrutura XML, impondo restrições definidas como regras. Estas restrições são impostas por PME que detêm a qualidade e a coerência do conteúdo.

OBSERVAÇÃO: o editor é compatível com o esquema ISO.


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
