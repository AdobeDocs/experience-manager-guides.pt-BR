---
title: Versões dos Guias AEM
description: Versões mais recentes do AEM Guides e versões pré-requisitos do AEM
exl-id: 780697a9-bdc6-40c2-b258-64639fe30f88
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---

# [!DNL AEM Guides] Versões

[!DNL Adobe Experience Manager Guides] O é um aplicativo implantado no AEM. É uma poderosa solução de gerenciamento de conteúdo de componentes (CCMS) de nível empresarial que permite o suporte ao DITA nativo no Adobe Experience Manager, permitindo que o AEM lide forma a lidar com a criação e a entrega de conteúdo baseado em DITA.

Os pacotes de Guias do AEM estão disponíveis em duas variantes: build UUID e builds não UUID.

## Builds UUID e não UUID

As principais diferenças entre as builds UUID e Não UUID são as seguintes:

|  | Compilação não UUID | Compilação UUID |
|---|---|---|
| **Identificação do ativo** | Todos os ativos são identificados usando o caminho do ativo no repositório. | Todos os ativos são identificados usando a UUID (ID exclusiva gerada pelo sistema quando o ativo foi carregado pela primeira vez). |
| **Criação de referência** | Todas as referências de conteúdo são criadas com base em seus caminhos. | Todas as referências de conteúdo são criadas com base em sua UUID. |

### Benefícios do build de UUID

* A instalação da UUID tem mais desempenho:
   * As referências são independentes de caminho: o sistema de gerenciamento de referências reconhece os vínculos, pois as referências são criadas com base em UUIDs e não nos caminhos.
   * As operações de movimentação/atualização são eficientes: os UUIDs permanecem os mesmos mesmo se os ativos forem movidos para outro caminho no repositório. Portanto, nenhum processamento é necessário para corrigir as referências entre os ativos nas operações de movimentação/atualização.
* A build UUID é prospetiva, pois usamos essa estrutura para a configuração da nuvem dos Guias AEM também.


### Escolha entre as duas builds

* Se você for um novo cliente, recomendamos usar a build de UUID.
* Se você for um cliente do, poderá optar por migrar para a build UUID, pois a migração de build Não UUID para UUID agora é possível. Para obter mais detalhes, consulte *Migração de conteúdo não UUID para UUID* na seção **Instale e configure o Adobe Experience Manager Guides.**

>[!NOTE]
>
>* Os clientes precisarão decidir entre o modo UUID e Não UUID no momento da primeira configuração (caso precise de ajuda, conecte-se ao Customer Success Manager para ajudá-lo a tomar a decisão com base no seu caso de uso).
>* Ao atualizar de uma versão dos Guias do AEM para uma versão mais recente, os clientes precisarão garantir que escolham o mesmo modo (UUID/não UUID) para corresponder ao modo existente. Uma build não UUID não deve ser atualizada diretamente para uma build UUID. A migração da build não UUID para a build UUID exigiria migração de conteúdo.

**Atualização de builds**

Ao atualizar de uma versão mais antiga para uma versão mais recente do [!DNL AEM Guides], talvez seja necessário executar scripts de migração. Consulte as Notas de versão e a documentação específica da versão para obter instruções de atualização.

Nem todos os caminhos de atualização são diretamente compatíveis. Por exemplo, a atualização direta para a versão 4.0 é possível somente na versão 3.8. Se você estiver em uma versão anterior à 3.8, consulte a documentação específica da versão para obter instruções de atualização [Arquivo de Ajuda](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).
Entre em contato com o gerente de sucesso do cliente para validar o caminho de atualização.

**[!DNL AEM Guides]Builds**

A lista a seguir contém os mais recentes [!DNL AEM Guides] pacotes disponíveis para instalação no AMS ou no local, versões correspondentes do AEM (pré-requisitos), links de download de pacotes e outras informações úteis. É recomendável usar somente a build mais recente do [!DNL AEM Guides]. Se, por algum motivo, você precisar acessar builds mais antigos, conecte-se com o Gerente de sucesso do cliente da sua conta.

>[!NOTE]
>
>Entre em contato com o Gerente de sucesso do cliente para obter acesso a [!DNL AEM Guides] builds para o AEM as a Cloud Service.

| [!DNL AEM Guides] Versão | Notas de versão | Pré-requisito do AEM | Criar links de download |
|---|---|---|---|
| **Guias do AEM 4.3.0** | [Notas de versão do 4.3.1](./release-notes-4.3.1.md)<br><br>[Notas de versão 4.3.0](./release-notes-4.3.md) | **Não UUID e UUID 4.3.1** <br>AEM 6.5 SP18, SP17, SP16, SP15 ou SP14 <br><br>   Java: 11 ou 8 <br><br> **Não UUID e UUID 4.3.0** <br>AEM 6.5 SP18, SP17, SP16, SP15 ou SP14 <br><br>   Java: 11 ou 8 | **AEM 6.5 não UUID** <br> [4.3.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-3-1%2Fcom.adobe.fmdita-6.5-4.3.1.390.zip) <br> [4.3.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-3%2Fcom.adobe.fmdita-6.5-4.3.0.347.zip)<br> **UUID AEM 6.5** <br> [4.3.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-3-1%2Fcom.adobe.fmdita-6.5-uuid-4.3.1.390.zip)<br>[4.3.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-3%2Fcom.adobe.fmdita-6.5-uuid-4.3.0.347.zip) |
| **Guias do AEM 4.2** | [Notas de versão 4.2.1](/help/product-guide/release-info/release-notes-4.2.1.md)<br> <br> [Notas de versão 4.2](/help/product-guide/release-info/release-notes-4.2.md) | **Não UUID e UUID 4.2.1**<br><br> AEM 6.5 SP15, SP14, SP13 ou SP12 <br><br>Java: 11 ou 8 <br><br>**Não UUID e UUID 4.2**<br><br> AEM 6.5 SP15, SP14, SP13 ou SP12 <br><br>Java: 11 ou 8<br><br> | **Não UUID**: <br> **AEM 6.5** <br>[4.2.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-2-1%2F4-2-1-non-uuid%2Fcom.adobe.fmdita-6.5-4.2.1.270.zip)<br>[4.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-2%2F4-2-non-uuid%2Fcom.adobe.fmdita-6.5-4.2.229.zip)<br><br> **UUID** <br>**AEM 6.5** <br>[4.2.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-2-1%2F4-2-1-uuid%2Fcom.adobe.fmdita-6.5-uuid-4.2.1.270.zip)<br>[4.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-2%2F4-2-uuid%2Fcom.adobe.fmdita-6.5-uuid-4.2.229.zip)<br> |
| **Guias do AEM 4.1** | [Notas de versão 4.1.x](/help/product-guide/release-info/release-notes-4.1.md) | **Não UUID e UUID 4.1.2**<br><br> AEM 6.5 SP13, SP12, SP11 ou SP10 <br>Java: 11 ou 8 <br><br>**Não UUID e UUID 4.1**<br><br> AEM 6.5 SP13, SP12, SP11 ou SP10 | **Não UUID**: <br> **AEM 6.5** <br>[4.1.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-3%2F4-1-3-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.1.3.2.zip)<br>[4.1.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-2%2F4-1-2-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.1.2.11.zip)<br>[4.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1%2F4-1-non-uuid%2Fcom.adobe.fmdita-6.5-4.1.159.zip)<br><br> **UUID** <br>**AEM 6.5** <br>[4.1.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-3%2F4-1-3-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.1.3.2.zip)<br>[4.1.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-2%2F4-1-2-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.1.2.11.zip)<br>[4.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1%2F4-1-uuid%2Fcom.adobe.fmdita-6.5-uuid-4.1.159.zip) |
| **Guias do AEM 4.0** | [Notas de versão 4.0.x](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html) | **Não UUID e UUID 4.0.3**<br> AEM 6.5 SP12, SP11, SP10 ou SP9 <br>Java: 11 ou 8 <br><br> <br>**Não UUID e UUID 4.0.2** <br> AEM 6.5 SP12, SP11, SP10 ou SP9 <br>Java: 11 ou 8 <br><br> **Não UUID e UUID 4.0** <br> AEM 6.5 SP11, SP10 ou SP9 | **Não UUID**: <br> **AEM 6.5** <br>[4.0.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-3%2F4-0-2-non-uuid%2Fcom.adobe.fmdita-6.5-hotfix-4.0.3.1.zip)<br>[4.0.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-2%2F4-0-2-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.0.2.10.zip)  <br> [4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/4-0/4-0-non-uuid/com.adobe.fmdita-6.5-4.0.70.zip)  <br><br> **UUID** <br>**AEM 6.5**  <br>[4.0.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-3%2F4-0-3-uuid%2Fcom.adobe.fmdita.uuid-6.5-hotfix-4.0.3.1.zip) <br>[4.0.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-2%2F4-0-2-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.0.2.10.zip)<br> [4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/4-0/4-0-uuid/com.adobe.fmdita-6.5-uuid-4.0.70.zip) |
| **Guias do AEM 3.8.5** <br> O 3.8.5 é uma versão SP acima do 3.8. <br>A versão 3.8 não deve ser instalada de modo independente, pois a versão 3.8.5 do SP contém uma correção crítica. <br>Os clientes devem instalar primeiro o 3.8 e depois o SP 3.8.5. | [Notas de versão do 3.8.x](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-3-8.html) | **Não UUID** <br> AEM 6.5 SP9 ou SP8 <br> AEM 6.4 SP8 <br> AEM 6.3 SP3 <br><br> **UUID** <br> AEM 6.5 SP9 ou SP8 | **Não UUID**: <br> **AEM 6.5** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.5-hotfix-3.8.5.2.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.5-3.8.166.zip)<br> **AEM 6.4** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.4-hotfix-3.8.5.1.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.4-3.8.166.zip) <br> **AEM 6.3** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.3-hotfix-3.8.5.1.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.3-3.8.166.zip) <br><br> **UUID** <br>**AEM 6.5** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5uuid/com.adobe.fmdita.uuid-6.5-hotfix-3.8.5.2.zip) <br> [3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8uuid/com.adobe.fmdita.uuid-6.5-3.8.168.zip) |