---
title: Atualizações de API em versões do Experience Manager Guides
description: Saiba mais sobre as várias atualizações de APIs em versões do Experience Manager Guides
source-git-commit: 24637376024107ae575620e5491c0150da6cc956
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 2%

---


# Atualizações de API em versões do Experience Manager Guides

Este artigo fornece detalhes sobre as APIs recém-adicionadas na documentação do Swagger para versões do Adobe Experience Manager Guides. Você pode acessar a documentação do Swagger por meio da interface do AEM navegando até **Ferramentas** > **Guias** > **API Swagger**.

<table style="border: 1; border-collapse: collapse; table-layout:fixed">
    <tr>
        <td colspan="5"><strong>Versão 2026.08.0</strong></td>
    </tr>
    <tr>
        <td>Destaque</td>
        <td>Sub-recurso</td>
        <td>Método</td>
        <td>API</td>
        <td>Descrição</td>
    </tr>
    <tr>
        <td rowspan="7"><b>Ativos</b></td>
        <td rowspan="7"></td>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/import`</td>
        <td>Importa um ou mais ativos para uma pasta de destino; oferece suporte para upload e resolução de conflitos em várias partes</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/list`</td>
        <td>Retorna a lista paginada de ativos em um caminho de pasta</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/validatexml`</td>
        <td>Valida o XML DITA quanto à qualidade, validade do esquema e integridade do conref</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/version/revert`</td>
        <td>Reverte um ativo para uma versão especificada</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/asset/currentversion/detail`</td>
        <td>Retorna os detalhes da versão atual (nome da versão, status sujo, rótulos etc.)</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/assets/status`</td>
        <td>Inicia um trabalho assíncrono para verificar o status dos Guias em determinados caminhos</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/assets/status`</td>
        <td>Recupera o status/resultados de um trabalho de status do ativo por ID do trabalho</td>
    </tr>
    <tr>
        <td rowspan="3"><b>Publicação</b></td>
        <td rowspan="3"></td>
        <td>POST</td>
        <td>`/bin/guides/v1/output/generate`</td>
        <td>Inicia a execução da predefinição para gerar a saída de um mapa</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/output/status`</td>
        <td>Retorna o status de uma única geração de saída por caminho do mapa e ID de geração</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/output/status/list`</td>
        <td>Retorna o status de todas as predefinições geradas para um caminho de mapa</td>
    </tr>
    <tr>
        <td rowspan="18"><b>Tradução</b></td>
        <td rowspan="6">Idioma</td>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/copies`</td>
        <td>Cópias de idioma de um ativo por caminho ou UUID</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/groups`</td>
        <td>Grupos de idiomas para um perfil de pasta</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/list`</td>
        <td>Oferece suporte a idiomas de tradução (filtrado)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/root`</td>
        <td>Idiomas raiz disponíveis para um caminho de ativo</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/variable`</td>
        <td>Variáveis de idioma por tipo e códigos de idioma</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/language/variable`</td>
        <td>Cria, atualiza ou exclui variáveis de idioma</td>
    </tr>
    <tr>
        <td rowspan="7">Projeto</td>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/project/create`</td>
        <td>Criar/atualizar projeto de tradução para um mapa DITA</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/project/sync`</td>
        <td>Cria/atualiza o projeto de tradução (fluxo de sincronização)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/project/creationstatus`</td>
        <td>Status de sincronização de tradução de um projeto por caminho</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/project/existing`</td>
        <td>Projetos de tradução existentes para o usuário atual</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/project/inprogress`</td>
        <td>Projetos em andamento para um determinado ativo</td>
    </tr>
    <tr>
        <td>EXCLUIR</td>
        <td>`/bin/guides/v1/translation/project/delete`</td>
        <td>Pré-excluir atualização de status/propriedades de tradução de ativos</td>
    </tr>
    <tr>
        <td>EXCLUIR</td>
        <td>`/bin/guides/v1/translation/project/job/delete`</td>
        <td>Pré-excluir atualização de status de ativos antes de remover o trabalho</td>
    </tr>
    <tr>
        <td rowspan="5">Referência</td>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/accept`</td>
        <td>Aceitar conteúdo traduzido de páginas filho do trabalho</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/reject`</td>
        <td>Rejeitar conteúdo traduzido das páginas filho do trabalho</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/sync`</td>
        <td>Criar cópias de idioma nas pastas de destino</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/baseline/export`</td>
        <td>Exportar linha de base de tradução para idiomas de destino</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/status/forcesync`</td>
        <td>Forçar atualização de ativos fora de sincronia para em sincronia</td>
    </tr>
</table>
