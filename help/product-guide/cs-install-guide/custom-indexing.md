---
title: Implantação de indexação personalizada
description: Saiba como personalizar o conteúdo de índice
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 7d2d0c21001cd53244588f6b700db184a73ffa77
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 3%

---

# Implantação de índice personalizado para o recurso Localizar e substituir (exibição do Source)

## Visão geral

Este guia fornece instruções passo a passo para implantar o índice personalizado `guidesAssetLucene‑1‑custom‑1` no Adobe Experience Manager (AEM) as a Cloud Service. Embora o recurso padrão de Localizar e substituir na exibição Autor funcione sem esse índice, o índice personalizado é especificamente necessário para habilitar Localizar e substituir na exibição do Source. A opção Localizar e substituir (visualização Source) permite pesquisar não apenas o conteúdo criado visível, mas também a estrutura XML subjacente; incluindo elementos, tags e valores de atributo.

## Pré-requisitos

Antes de continuar com a implantação do índice, verifique se você tem:

- **Ambiente AEM as a Cloud Service** com AEM Guides instalado
- **Acesso à base de código do seu projeto** (repositório Git)
- **Acesso ao Cloud Manager** com permissões de implantação

## Definição de índice

Para habilitar o recurso Localizar e substituir (exibição do Source), você precisa implantar um índice personalizado chamado **`guidesAssetLucene-1-custom-1`** no seu ambiente do AEM Cloud Service.

### Nome do índice

```
guidesAssetLucene-1-custom-1
```

### Definição de índice (.content.xml)

Crie a seguinte definição de índice no seu projeto em:

`ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:dam="http://www.day.com/dam/1.0"
          xmlns:nt="http://www.jcp.org/jcr/nt/1.0" xmlns:oak="http://jackrabbit.apache.org/oak/ns/1.0"
          xmlns:rep="internal"
          jcr:mixinTypes="[rep:AccessControllable]"
          jcr:primaryType="oak:QueryIndexDefinition"
          async="[async,nrt]"
          compatVersion="{Long}2"
          evaluatePathRestrictions="{Boolean}true"
          includedPaths="[/content/dam]"
          reindex="{Boolean}false"
          reindexCount="{Long}1"
          seed="{Long}958982603885135223"
          selectionPolicy="tag"
          tags="[ditaSearch]"
          type="lucene">

    <aggregates jcr:primaryType="nt:unstructured">
        <dam:Asset jcr:primaryType="nt:unstructured">
            <include0
                    jcr:primaryType="nt:unstructured"
                    path="jcr:content/renditions/original/jcr:content"
                    relativeNode="{Boolean}true"/>
        </dam:Asset>
    </aggregates>

    <analyzers jcr:primaryType="nt:unstructured">
        <default jcr:primaryType="nt:unstructured">
            <tokenizer
                    jcr:primaryType="nt:unstructured"
                    name="Whitespace"/>
        </default>
    </analyzers>

    <indexRules jcr:primaryType="nt:unstructured">
        <dam:Asset
                jcr:primaryType="nt:unstructured"
                indexNodeName="{Boolean}true">
            <properties jcr:primaryType="nt:unstructured">
                <cqTags
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/cq:tags"
                        nodeScopeIndex="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        useInSpellcheck="{Boolean}true"
                        useInSuggest="{Boolean}true"/>
                <jcrLastModified
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/jcr:lastModified"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <jcrCreated
                        jcr:primaryType="nt:unstructured"
                        name="jcr:created"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <guidesParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesParentMaps"
                        propertyIndex="{Boolean}true"/>
                <guidesDirectParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesDirectParentMaps"
                        propertyIndex="{Boolean}true"/>
                <ditaClass
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dita_class"
                        propertyIndex="{Boolean}true"/>
                <nodeNameLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(fn:name())"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"/>
                <cqDriveLock
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/cq:driveLock"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <docState
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/docstate"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <jcrPath
                        jcr:primaryType="nt:unstructured"
                        function="fn:path()"
                        ordered="{Boolean}true"/>
                <dcTitleLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(jcr:first(jcr:content/metadata/@dc:title))"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <dcTitle
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dc:title"
                        propertyIndex="{Boolean}true"/>
            </properties>
        </dam:Asset>
    </indexRules>

    <tika jcr:primaryType="nt:unstructured">
        <mimeTypes jcr:primaryType="nt:unstructured">
            <application jcr:primaryType="nt:unstructured">
                <xml
                        jcr:primaryType="nt:unstructured"
                        mappedType="application/dita+xml"/>
            </application>
            <text jcr:primaryType="nt:unstructured">
                <markdown
                        jcr:primaryType="nt:unstructured"
                        mappedType="text/markdown+source"/>
            </text>
        </mimeTypes>
    </tika>
</jcr:root>
```

## Etapas de implantação

Para obter instruções detalhadas sobre como implantar índices personalizados no AEM as a Cloud Service, consulte [Pesquisa e indexação de conteúdo - AEM as a Cloud Service](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-service/content/operations/indexing).

### Pontos importantes para este índice

Ao seguir o guia de implantação, use as seguintes especificações para o índice Localizar e substituir:

- **Nome do índice**: `guidesAssetLucene-1-custom-1`
- **Tipo de índice**: índice totalmente personalizado (não é uma personalização do índice OOTB)
- **Local**: `ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`
- **Propriedades do Pacote Necessárias**:
   - `noIntermediateSaves=true`
   - `allowIndexDefinitions=true`

## Reindexação

A reindexação é tratada **automaticamente** pela AEM as a Cloud Service quando você implanta o índice pelo pipeline de CI/CD do Cloud Manager.

Normalmente, a indexação é feita automaticamente. No entanto, se os dados antigos não puderem ser pesquisados mesmo após a implantação correta e a conclusão do processo de indexação, uma reindexação manual do índice deverá ser executada uma vez.

### O que esperar

- O trabalho de indexação será iniciado automaticamente após a implantação.
- Você pode monitorar o progresso na página de build do Cloud Manager.
- O ambiente permanece totalmente operacional durante a indexação.

## Verificação

Após a conclusão da implantação e da indexação, verifique se o índice está funcionando corretamente.

### Verificar Implantação de Índice

Em seu ambiente de desenvolvimento (se o CRXDE Lite estiver disponível):

1. Vá até `/oak:index/guidesAssetLucene-1-custom-1`.
2. Verifique se o nó existe com a configuração esperada.

### Testar o recurso Localizar e substituir

A verificação primária está testando o recurso:

1. Abra o AEM Guides.
2. Navegue até **Ferramentas** > **Guias** > **Localizar e Substituir no Repositório**.
3. Configure uma pesquisa de texto nos arquivos DITA ou Markdown.
4. Verifique se os resultados da pesquisa foram retornados corretamente.
5. Testar a funcionalidade de substituição em um arquivo de teste.

## Recursos adicionais

- [Documentação de indexação do AEM as a Cloud Service](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-service/content/operations/indexing)
- [Guia de indexação do Apache Jackrabbit Oak](https://jackrabbit.apache.org/oak/docs/query/indexing.html)
- [Documentação do AEM Guides](https://experienceleague.adobe.com/pt-br/docs/experience-manager-guides)
- [Documentação do Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager)
