---
title: Notas de versão | Novidades da versão de fevereiro de 2026 do conteúdo de treinamento e aprendizado do produto
description: Saiba mais sobre os recursos novos e aprimorados da versão de fevereiro de 2026 do conteúdo de treinamento e aprendizado do produto
role: Leader
hidefromtoc: true
source-git-commit: 5ba7ba00cbc9209aad9f17f0793d621f1f1838e2
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---

# Versão de fevereiro de 2026 do conteúdo de treinamento e aprendizado do produto

Esta nota de versão aborda os novos aprimoramentos de recursos e problemas corrigidos na versão de fevereiro de 2026 do conteúdo de treinamento e aprendizado do produto.

## Novas melhorias de recursos

Os seguintes recursos foram introduzidos na versão de fevereiro de 2026 do conteúdo de treinamento e aprendizado do produto:

- **Suporte para legendas**: agora você pode adicionar legendas ao seu conteúdo de aprendizado usando a nova opção **Adicionar legenda** em **Propriedades do arquivo**. Isso aumenta a clareza e a capacidade de pesquisa em todo o conteúdo do curso.

  Para obter mais detalhes, consulte [Adicionar título e subtítulo ao conteúdo didático](../learning-content/lc-basic-blocks.md#add-title-and-subtitle-to-learning-content).

  ![](assets/add-subtitles.png)

- **Habilitar ou desabilitar a pontuação final negativa**: ao configurar as propriedades do questionário, você pode controlar a pontuação negativa usando a opção **Permitir pontuação final negativa**. Quando ativado, os alunos recebem uma pontuação final mínima de zero, mesmo que uma marcação negativa seja aplicada. Isso mantém os alunos motivados, garantindo que as pontuações nunca caem abaixo de zero.

  Saiba mais sobre [Propriedades do questionário](../learning-content/quiz-properties.md).

  ![](assets/negative-scores-lc.png)

- **Excluir widgets com um clique no botão direito do mouse**: além de excluir perguntas do questionário, agora é possível excluir widgets como Acordeões, Cartões invertidos e Guias com **Clique com o botão direito do mouse > Excluir item**. Este aprimoramento estende a funcionalidade existente de *Excluir pergunta* para widgets, permitindo removê-los com menos cliques e navegação mínima.

  Saiba mais sobre [Usar widgets interativos](../learning-content/lc-widgets.md).

  ![](assets/delete-widget-items.png)
- **Opções de resposta de PIN**: agora é possível fixar opções de resposta específicas para que suas posições permaneçam inalteradas, mesmo quando as respostas forem aleatórias durante a geração da saída SCORM. Isso é especialmente útil para opções como *Todas as opções acima* ou *Nenhuma das opções acima*.

  ![](assets/pin-question.png)
- **Tipo de resposta curta**: o tipo de pergunta de resposta curta permite que os alunos respondam usando respostas alfanuméricas breves e descritivas em vez de selecionar opções predefinidas. Esse tipo de pergunta incentiva os alunos a recordar e articular ativamente sua compreensão em suas próprias palavras, tornando as avaliações mais envolventes para os alunos.

  Saiba mais sobre [Tipos de pergunta](../learning-content/quiz-insert-questions.md#question-types).


  ![](assets/short-answer.png)
- **Tentativa sequencial para perguntas do questionário**: agora é possível impor tentativas sequenciais de teste para saída SCORM usando a opção **Os alunos devem tentar cada pergunta para continuar** na predefinição de saída SCORM. Quando ativado, os alunos devem responder a cada pergunta antes de passar para a seguinte, com navegação restrita até que a pergunta atual seja concluída. Isso garante um fluxo de avaliação passo a passo guiado e uma experiência de aprendizado consistente.

  Para obter mais detalhes, consulte [Configurar predefinição de saída SCORM](../learning-content/config-scorm-preset.md).

  ![](assets/scorm-general-tab-v3.png)

## Problemas corrigidos

Os seguintes problemas foram corrigidos na versão de fevereiro de 2026 do conteúdo de treinamento e aprendizado do produto:

- Ao publicar a saída do SCORM e implantá-la no ALM, o relatório do L2 Quiz mostra pontuações totais e máximas incorretas para o questionário que usa várias tentativas e seleção aleatória do banco de perguntas. (GUIDES-38855)
- Quando qualquer curso é gerado no servidor na nuvem, um espaço em branco não intencional é exibido abaixo do rodapé de direitos autorais devido à folha de estilos `coralui3.css`, causando inconsistência de layout. (GUIDES-38853)
- Quando o curso de aprendizado com um acordeão é navegado usando o teclado, o sinal + ou o título da guia não é realçado, impedindo a identificação visual do elemento ativo. (GUIDES-38852)
- Para cursos gerados usando o modelo de carbono SCORM ou o modelo padrão, quando acessado em um dispositivo móvel no modo paisagem, o Sumário (Menu Curso) não exibe os links do módulo que impedem a navegação. (GUIDES-38851)
- Ao replicar a hierarquia de um curso no Experience Manager Guides, a criação de um objeto de aprendizado exige primeiro a criação de um grupo de aprendizado, pois não há suporte para adições no nível do objeto. (GUIDES-38849)
- Tentativas de acessar as opções suspensas em Corresponder ao seguinte tipo de pergunta usando o teclado falham, pois as opções não respondem à tecla de tabulação ou seta que impede a navegação. (GUIDES-38985)
- Aplicar uma predefinição de estilo de cabeçalho faz com que o texto selecionado desapareça, provavelmente devido à mudança de cor da fonte para branco, tornando o texto não selecionável e não visível. (GUIDES-39981)
- Ao usar o Experience Manager Guides no Mozilla Firefox, o cartão Inverter exibe o texto da frente no verso no verso depois de virar. (GUIDES-39983)
- Quando você clica no índice no painel esquerdo do curso, o curso continua a mostrar o status de conclusão mesmo que o questionário tenha falhado. (GUIDES-40398)
- Tentar Corresponder ao seguinte tipo de pergunta em um questionário incorretamente no ALM faz com que as opções selecionadas não apareçam no relatório. (GUIDES-38640)
- Ao gerar a saída do PDF, os estilos de criação aplicados não são preservados, resultando em inconsistências no design.(GUIDES-38642)

