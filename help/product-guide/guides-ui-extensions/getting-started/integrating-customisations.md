---
title: Instalação e configuração
description: Instalação e uso do pacote de extensão Guias do AEM
source-git-commit: 2a17d387c59d5e7b58c90edea75f34ad43539b1a
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---


# Instalação e uso do pacote de extensão Guias do AEM

As extensões oferecem a oportunidade de personalizar seu aplicativo Guias do AEM para melhor atender às suas necessidades. Essa estrutura de extensão é compatível com o AEM Guides v4.3 em diante (no local) e 2310 (nuvem).

## Requisitos

Este pacote requer [git bash](https://github.com/git-guides/install-git) e npm

## Instalação

A maneira mais fácil de inicializar a instalação da estrutura de guias AEM é por meio da cli

```bash
npx @adobe/create-guides-extension
```

## Adição de código de personalização

1. Adicione arquivos de código para cada componente que você deseja estender na `src/` diretório. Alguns arquivos de exemplo já foram adicionados para você.
2. Agora no `index.ts` arquivo localizado na `src/` diretório:
   - Importe o `.ts` arquivos com as personalizações que deseja adicionar à build.
   - Adicionar as importações ao `window.extension`
   - Registre os componentes personalizados `id` e a importação correspondente para `tcx extensions`
   - Consulte a amostra `/src/index.ts`

## Criação do código personalizado

- Executar `npm run build` no diretório raiz. Você obterá 3 arquivos no diretório, `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Saída da build](./../imgs/build_output.png)

## Adicionar a personalização ao AEM

- Ir para `CRXDE` `crx/de/index.jsp#/`
- No `apps` , crie um novo nó do tipo `cq:ClientLibraryFolder`

![Estrutura de pastas](./../imgs/crxde_folder_structure.png)

- No `properties` do nó, selecione `Multi` adicione o seguinte Nome da propriedade: `categories`
Tipo: `String []`
Valor: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

![Propriedades da pasta](./../imgs/crxde_folder_properties.png)

- Para adicionar o js construído, crie um novo arquivo, digamos, `tcx1.js` no nó criado acima. Aqui, adicione o código de `dist/guides-extension.umd.cjs` ou `dist/guides-extension.js`. Agora crie um novo arquivo `js.txt`, aqui adicionamos o nome do arquivo js, que nesse caso seria:

```t
#base=.
tcx1.js
```

- Para adicionar o css criado, crie um novo arquivo, digamos, `tcx1.css` no nó criado acima. Aqui, adicione o código de `dist/build.css`. Agora crie um novo arquivo `css.txt`, aqui adicionamos o nome do arquivo css, que nesse caso seria:

```t
#base=.
tcx1.css
```

- Fazer um `shift + refresh` para carregar o aplicativo com as personalizações!

## Resolução de problemas

Verifique se todas as etapas acima foram executadas corretamente.
Depois de adicionar seu código ao tcx.js, certifique-se de fazer uma atualização rígida (shift+refresh).
Agora abra AEM, clique com o botão direito do mouse e clique em `Inspect`
Vá para Origens e pesquise por seus `[node_name].js` (por exemplo: extensions.js) arquivo. Faça um Control / Cmd + D para procurar o arquivo. Se a variável `.js` arquivo existe com o código JS que você colou `dist/guides-extension.umd.cjs` ou `dist/guides-extension.js`, sua configuração foi concluída
