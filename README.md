# Engenharia de Prompts para Desenvolvimento de Software com IA

## Sobre o desafio

Este projeto foi desenvolvido como parte de um desafio da DIO, com o objetivo de usar IA como ferramenta de aprendizagem ativa por meio da criação de um caderno temático no **Google NotebookLM**.

A proposta foi combinar curadoria de fontes abertas, pensamento crítico, testes de prompts e organização do conhecimento em um material de portfólio. O NotebookLM foi usado como ambiente de estudo para reunir fontes, gerar sínteses, fazer perguntas estratégicas e consolidar aprendizados sobre Engenharia de Prompts aplicada ao desenvolvimento de software.

O resultado principal está neste README: ele documenta o tema escolhido, as fontes usadas, o processo de curadoria, os prompts testados, as dificuldades encontradas, os aprendizados e um miniguia final reutilizável. A pasta [`docs`](docs) permanece como material complementar.

## Tema escolhido

O tema escolhido foi **Engenharia de Prompts para Desenvolvimento de Software com IA**.

Escolhi esse tema porque ele é atual, útil para pessoas desenvolvedoras e diretamente relacionado ao uso mais crítico de ferramentas de IA no dia a dia técnico. Em vez de tratar prompts como simples perguntas, o estudo investiga como instruções bem estruturadas podem apoiar tarefas reais como aprendizado técnico, debugging, documentação, revisão de Pull Requests, planejamento de arquitetura e criação de testes.

A ideia central do caderno foi entender como melhorar a qualidade das respostas geradas por IA sem perder de vista um ponto essencial: a IA é apoio, não substituição da pessoa desenvolvedora.

## Objetivos do estudo

- Compreender o que é Engenharia de Prompts.
- Entender a diferença entre design de prompts e engenharia de prompts.
- Estudar boas práticas para criar prompts técnicos.
- Aplicar prompts em cenários reais de desenvolvimento de software.
- Registrar testes, dificuldades e melhorias ao longo do processo.
- Criar um miniguia reutilizável para futuras revisões e estudos.

## Ferramenta utilizada: NotebookLM

O **Google NotebookLM** foi usado como ferramenta central do caderno temático. Nele, foram adicionadas fontes abertas e técnicas para organizar o estudo, gerar resumos, fazer perguntas estratégicas, comparar respostas e consolidar o aprendizado.

No contexto deste projeto, o NotebookLM ajudou a:

- reunir fontes sobre prompts, IA e revisão de código;
- organizar materiais em um único caderno;
- gerar resumos embasados nas fontes adicionadas;
- testar perguntas com diferentes níveis de especificidade;
- comparar prompts genéricos com prompts estruturados;
- transformar o estudo em um material final de portfólio.

## Fontes selecionadas

### 1. Google NotebookLM — Add or discover new sources for your notebook

https://support.google.com/notebooklm/answer/16215270?co=GENIE.Platform%3DDesktop&hl=pt-BR

Essa fonte foi escolhida por ser a documentação da ferramenta central do desafio. Ela ajudou a entender como adicionar fontes ao caderno, quais tipos de arquivo e URL podem ser usados e quais limites precisam ser considerados durante a curadoria.

Também contribuiu para compreender o papel do NotebookLM como ambiente de organização e sumarização de conteúdo, com respostas apoiadas nos materiais adicionados ao caderno.

### 2. OpenAI — Prompt engineering | OpenAI API

https://developers.openai.com/api/docs/guides/prompt-engineering

Essa fonte foi escolhida por apresentar práticas fundamentais para escrever instruções mais eficazes para modelos de linguagem. Ela contribuiu com conceitos como contexto relevante, exemplos, papéis de mensagem, formatação e refinamento iterativo de prompts.

No caderno, foi especialmente útil para relacionar Engenharia de Prompts com tarefas de desenvolvimento, como debugging, documentação técnica e estruturação de respostas.

### 3. OpenAI — Prompt guidance | OpenAI API

https://developers.openai.com/api/docs/guides/prompt-guidance

Essa fonte complementou o estudo com orientações sobre como melhorar prompts a partir do resultado desejado. Ela ajudou a reforçar a importância de escrever comandos orientados a objetivo, com restrições claras e expectativa explícita de saída.

Também contribuiu para o cuidado de linguagem adotado neste projeto: em vez de atribuir processos internos à IA, o material descreve que o modelo gera, organiza ou estrutura respostas com base no contexto fornecido.

### 4. Microsoft Learn — Prompt engineering techniques

https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/prompt-engineering

Essa fonte foi escolhida por apresentar uma visão prática e estruturada sobre técnicas de Engenharia de Prompts. Ela contribuiu com elementos como instruções, conteúdo primário, conteúdo de suporte, exemplos few-shot, delimitadores, divisão de tarefas complexas, grounding e formato esperado de saída.

Foi uma das bases mais importantes para transformar perguntas genéricas em prompts técnicos mais completos e verificáveis.

### 5. GitHub Docs — Helping others review your changes

https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/helping-others-review-your-changes

Essa fonte foi escolhida para conectar Engenharia de Prompts com uma prática real do desenvolvimento de software: revisão de Pull Requests. Ela contribuiu com boas práticas como PRs pequenos, contexto claro, ordem de leitura, self-review e atenção à segurança.

No caderno, essa fonte ajudou a definir que a IA pode apoiar revisões, mas não deve substituir revisão humana, testes automatizados e validação de segurança.

## Processo de curadoria

As fontes foram selecionadas por serem abertas, oficiais ou técnicas, e por contribuírem com perspectivas diferentes sobre o tema:

- **NotebookLM:** ferramenta usada para organizar o estudo e trabalhar com fontes.
- **OpenAI:** boas práticas de engenharia, orientação e refinamento de prompts.
- **Microsoft:** técnicas de estruturação de prompts, grounding, few-shot e formato de saída.
- **GitHub:** aplicação prática em revisão de Pull Requests e colaboração técnica.

O processo começou com a seleção das cinco fontes principais, seguido pela adição delas ao NotebookLM. Depois, foram feitas perguntas estratégicas para extrair conceitos, comparar respostas, gerar exemplos e consolidar o conteúdo em um miniguia.

Durante o processo, algumas fontes e abordagens foram ajustadas para manter a curadoria focada no tema central. O objetivo não foi acumular links, mas construir um caderno coerente, útil e aplicável ao desenvolvimento de software.

## Prompts testados no NotebookLM

Esta seção apresenta uma síntese dos principais prompts testados no NotebookLM. O registro completo, com os prompts integrais, resultados observados e aprendizados, está disponível em [`docs/prompts-testados.md`](docs/prompts-testados.md).

### Prompt 1 — Resumo inicial do tema

**Objetivo:**
Explicar o que é Engenharia de Prompts aplicada ao desenvolvimento de software, incluindo definição, diferença entre design e engenharia de prompts, importância para pessoas desenvolvedoras e contribuição das fontes.

**Prompt utilizado:**

```text
Com base apenas nas fontes adicionadas agora, gere um resumo inicial sobre Engenharia de Prompts aplicada ao desenvolvimento de software.

A resposta deve explicar:
- O que é Engenharia de Prompts;
- Qual a diferença entre design de prompts e engenharia de prompts;
- Por que essa habilidade é importante para pessoas desenvolvedoras;
- Como as fontes da OpenAI, Microsoft, Google NotebookLM e GitHub contribuem para este estudo;
- Quais conceitos serão mais úteis para criar prompts de debugging, documentação, revisão de Pull Request e aprendizado técnico.

Organize em Markdown e indique de qual fonte vieram os principais conceitos.
```

**Resultado obtido:**
O NotebookLM gerou um resumo estruturado sobre o tema, destacando Engenharia de Prompts como um processo iterativo de escrita, teste e refinamento de instruções. A resposta também diferenciou design de prompts, mais ligado à criação inicial do comando, de engenharia de prompts, mais ligada à avaliação e melhoria contínua.

**Aprendizado:**
Especificar seções obrigatórias na pergunta gerou uma resposta mais organizada e pronta para ser reaproveitada no README e no miniguia.

---

### Prompt 2 — Aplicações práticas no desenvolvimento de software

**Objetivo:**
Mapear formas práticas de usar Engenharia de Prompts em tarefas reais de desenvolvimento.

**Prompt utilizado:**
Foi solicitado ao NotebookLM que listasse exatamente seis aplicações, cada uma com objetivo, situação prática, prompt ruim, prompt melhorado, motivo da melhoria e cuidados.

**Resultado obtido:**
As seis aplicações identificadas foram:

- aprender uma nova tecnologia;
- entender e corrigir erros;
- revisar Pull Requests;
- criar documentação técnica;
- planejar arquitetura;
- criar testes.

**Aprendizado:**
Pedir uma estrutura obrigatória melhorou a qualidade da resposta. A saída ficou mais completa, comparável e útil para transformar o estudo em material de portfólio.

---

### Prompt 3 — Prompt ruim vs. prompt melhorado

**Objetivo:**
Comparar prompts genéricos com prompts bem estruturados.

**Prompt utilizado ou resumo fiel do prompt:**
Foi usado um comparativo entre um prompt fraco, sem contexto suficiente, e um prompt melhorado com erro, código, objetivo e pedido de análise estruturada em etapas claras, objetivas e verificáveis.

**Resultado obtido:**
O caderno mostrou que prompts fracos tendem a gerar respostas vagas, amplas ou pouco conectadas ao problema real. Já prompts com contexto, código, erro completo, objetivo, restrições e formato esperado geram respostas mais úteis.

**Exemplo de diferença observada:**

```text
Prompt fraco:
Meu código está dando erro. Como arrumar?

Prompt melhorado:
Analise o erro abaixo e sugira correção para a função fornecida.
Apresente análise estruturada em etapas claras, objetivas e verificáveis.

ERRO:
[cole stack trace]

CÓDIGO:
[cole função exata]
```

**Aprendizado:**
A qualidade da resposta depende muito da qualidade do contexto fornecido. Para desenvolvimento de software, o modelo precisa receber dados concretos, como stack, código, log, comportamento esperado e comportamento atual.

---

### Prompt 4 — Modelo para debugging

**Objetivo:**
Criar um template para pedir ajuda na análise de erros de programação.

**Prompt utilizado ou resumo fiel do prompt:**
Foi solicitado um modelo completo de prompt para análise de erro, incluindo contexto do projeto, stack, objetivo, código, mensagem de erro, comportamento esperado, comportamento atual, tentativas já feitas, restrições e formato esperado.

**Resultado obtido:**
O NotebookLM identificou dez campos importantes para um bom prompt de debugging:

- contexto do projeto;
- stack;
- objetivo da funcionalidade;
- código relevante;
- mensagem de erro;
- comportamento esperado;
- comportamento atual;
- tentativas já feitas;
- restrições;
- formato esperado.

**Aprendizado:**
Pedir template e justificativa no mesmo prompt produziu um material didático e prático. Os campos de comportamento esperado, comportamento atual e tentativas já feitas ajudam a reduzir respostas repetitivas ou genéricas.

---

### Prompt 5 — Revisão de Pull Request

**Objetivo:**
Criar um template para usar IA como apoio preliminar na revisão de Pull Requests.

**Prompt utilizado ou resumo fiel do prompt:**
Foi solicitado um modelo de prompt para revisão de Pull Requests com objetivo, informações necessárias antes da análise, critérios obrigatórios, exemplo ruim, exemplo melhorado, template reutilizável e cuidados de uso.

**Resultado obtido:**
O caderno consolidou um modelo de revisão com critérios explícitos:

- bugs;
- legibilidade;
- segurança;
- performance;
- testes ausentes;
- riscos de regressão;
- documentação.

**Aprendizado:**
Definir a IA como apoio preliminar evita a ideia de automação total da revisão. O uso mais adequado é como checklist, resumo e apoio para levantar hipóteses, mantendo a aprovação final com pessoas desenvolvedoras.

---

### Prompt 6 — Cicatrizes do processo

**Objetivo:**
Identificar erros comuns ao escrever prompts para desenvolvimento de software.

**Prompt utilizado ou resumo fiel do prompt:**
Foi solicitado ao NotebookLM que explicasse os principais erros cometidos ao escrever prompts técnicos, considerando as fontes adicionadas e os testes realizados no caderno.

**Resultado obtido:**
Foram registrados erros como pedidos genéricos demais, falta de contexto, ausência de código ou erro completo, falta de formato esperado, ausência de restrições, confiança excessiva na resposta da IA, PRs grandes demais, mistura entre instruções e dados, e falta de uma saída segura quando a informação não existe.

**Aprendizado:**
As falhas nos prompts serviram como parte essencial do estudo. Elas mostraram que bons prompts surgem de iteração, comparação e validação crítica.

---

### Prompt 7 — Miniguia final

**Objetivo:**
Consolidar o estudo em um material reutilizável.

**Prompt utilizado ou resumo fiel do prompt:**
Foi solicitado um miniguia de estudo com introdução, diferença entre design e engenharia de prompts, importância para pessoas desenvolvedoras, elementos de um bom prompt técnico, aplicações, erros comuns, boas práticas, glossário, prompts reutilizáveis e conclusão crítica.

**Resultado obtido:**
O miniguia final reuniu resumo, diferença entre design e engenharia de prompts, elementos de um bom prompt técnico, aplicações práticas, erros comuns, boas práticas, glossário, prompts reutilizáveis e conclusão crítica sobre limites da IA.

**Aprendizado:**
Um prompt final de consolidação, com índice explícito, funcionou bem para transformar o caderno em uma entrega organizada e útil para consultas futuras.

## Engenharia de Prompts e Cicatrizes

As cicatrizes foram uma das partes mais importantes do projeto. Elas registram dificuldades reais encontradas durante a criação do caderno e mostram como o estudo evoluiu a partir de testes, erros e refinamentos.

As três cicatrizes principais abaixo sintetizam dificuldades reais do processo: prompt genérico demais, falta de formato esperado e uso da IA como apoio, não como substituta.

Durante o processo, ficaram evidentes alguns pontos:

- fontes precisam ser escolhidas com critério para manter o caderno focado;
- quando uma fonte não carrega corretamente no NotebookLM, é necessário revisar a URL, substituir o material ou retirar a fonte da curadoria;
- prompts genéricos geram respostas corretas, mas pouco aplicáveis;
- pedir exemplos práticos sem estrutura obrigatória pode gerar respostas incompletas;
- definir formato de saída melhora muito a utilidade do resultado;
- fontes que não fazem parte da curadoria principal devem ser removidas ou deixadas fora da entrega;
- respostas da IA não devem ser aceitas sem validação crítica.

### Cicatriz 1 — Prompt genérico demais

**Prompt inicial:**

```text
Explique Engenharia de Prompts.
```

**Problema:**
A resposta ficou correta, mas genérica e pouco conectada ao desenvolvimento de software.

**Prompt refinado:**

```text
Explique Engenharia de Prompts no contexto do desenvolvimento de software, incluindo exemplos de uso em debugging, revisão de Pull Requests, documentação técnica, arquitetura e testes.
```

**Aprendizado:**
Um bom prompt precisa de contexto, objetivo e escopo claro.

### Cicatriz 2 — Falta de formato esperado

**Problema:**
Pedir apenas "exemplos práticos" não foi suficiente. A resposta podia trazer exemplos úteis, mas sem padrão, profundidade ou comparação entre abordagens.

**Refinamento aplicado:**
Depois, o prompt passou a exigir uma estrutura fixa com objetivo, situação prática, prompt ruim, prompt melhorado, motivo da melhoria e limitações.

**Aprendizado:**
Definir o formato esperado transforma uma resposta solta em material organizado, comparável e reutilizável.

### Cicatriz 3 — IA como apoio, não substituta

**Problema:**
Em tarefas como revisão de Pull Requests, documentação e debugging, existe risco de aceitar a resposta da IA como se fosse validação final.

**Refinamento aplicado:**
Os prompts passaram a reforçar que a IA deve atuar como apoio preliminar, com análise estruturada em etapas claras, objetivas e verificáveis.

**Aprendizado:**
A IA pode ajudar a revisar código, organizar hipóteses e criar checklists, mas não substitui testes, revisão humana, validação de segurança e análise de regra de negócio.

## Miniguia de estudo

### Resumo estruturado

**O que é Engenharia de Prompts:**
É o processo de escrever, estruturar, testar e otimizar instruções para que o modelo gere respostas mais alinhadas a um objetivo técnico. No desenvolvimento de software, isso significa fornecer contexto suficiente, delimitar dados, definir restrições e especificar o formato esperado.

**Por que é importante para devs:**
Porque pessoas desenvolvedoras usam IA em tarefas que exigem precisão: entender erros, revisar código, documentar APIs, aprender tecnologias, criar testes e avaliar alternativas de arquitetura. Prompts melhores reduzem respostas vagas e aumentam a chance de obter uma saída útil.

**Elementos de um bom prompt técnico:**
Um bom prompt técnico combina instrução clara, contexto, conteúdo primário, conteúdo de suporte, exemplos, restrições, formato de saída e uma saída segura quando a informação não estiver disponível.

**Principais aplicações:**
As aplicações estudadas foram aprendizado técnico, debugging, revisão de Pull Requests, documentação técnica, arquitetura e testes.

### Elementos de um bom prompt técnico

- **Instrução clara:** define o que a IA deve fazer.
- **Contexto:** explica o cenário, o projeto ou o problema.
- **Conteúdo primário:** inclui o material principal a ser analisado, como código, diff ou stack trace.
- **Conteúdo de suporte:** adiciona stack, versões, regras de negócio ou restrições do projeto.
- **Exemplos few-shot:** mostram o padrão esperado de entrada e saída.
- **Restrições:** indicam o que deve ou não ser feito.
- **Formato esperado:** define se a resposta deve vir em Markdown, tabela, JSON, XML ou outro formato.
- **Saída segura:** orienta o modelo a dizer que não encontrou a informação quando não houver evidência suficiente.

### Glossário

| Termo | Definição curta |
|------|------------------|
| **Prompt** | Instrução ou entrada enviada a um modelo de IA para gerar uma resposta. |
| **Engenharia de Prompts** | Processo de estruturar, testar e refinar prompts para obter respostas mais úteis e consistentes. |
| **Design de Prompts** | Criação inicial de uma instrução em linguagem natural para orientar uma tarefa. |
| **Few-shot** | Uso de exemplos no prompt para mostrar o formato ou comportamento esperado. |
| **Zero-shot** | Pedido feito sem exemplos prévios no prompt. |
| **Grounding** | Uso de dados concretos, como código, logs ou fontes, para ancorar a resposta. |
| **Tokens** | Unidades de texto processadas pelo modelo. |
| **Janela de contexto** | Limite de informações que o modelo consegue considerar em uma requisição. |
| **Alucinação** | Resposta plausível, mas incorreta ou inventada por falta de embasamento. |
| **Metaprompting** | Uso da IA para avaliar ou melhorar o próprio prompt. |
| **Pull Request** | Solicitação de integração de mudanças em um repositório, geralmente revisada antes do merge. |

### Prompts reutilizáveis

#### 1. Estudar uma tecnologia

```text
Atue como um Engenheiro de Software Sênior. Explique o conceito de [TECNOLOGIA] para um desenvolvedor júnior.
Apresente uma análise estruturada em etapas claras, objetivas e verificáveis.
Limite a resposta a 3 parágrafos e use lista de marcadores para os principais benefícios.
```

#### 2. Analisar um erro

```text
Atue como Engenheiro de Software Sênior especialista em resolução de problemas.
Analise as informações abaixo, identifique a causa provável e proponha uma correção.
Apresente uma análise estruturada em etapas claras, objetivas e verificáveis.

CONTEXTO DO PROJETO:
[descrição do módulo ou produto]

STACK:
[linguagem, framework, versões]

OBJETIVO DA FUNCIONALIDADE:
[o que o código deveria fazer]

COMPORTAMENTO ESPERADO:
[resultado desejado]

COMPORTAMENTO ATUAL:
[o que ocorre de errado]

TENTATIVAS JÁ REALIZADAS:
[o que já foi testado]

RESTRIÇÕES:
[o que não deve ser sugerido]

CÓDIGO:
[cole o trecho relevante]

ERRO:
[cole o log completo]
```

#### 3. Revisar um Pull Request

```text
Você é Engenheiro de Software Sênior. Atue como apoio preliminar na revisão deste Pull Request.
A análise é para revisores humanos e não substitui aprovação final.

CONTEXTO DO PR:
- Propósito: [descrição]
- Ordem de leitura: [arquivos]
- Issue relacionada: [opcional]

CRITÉRIOS:
1. Possíveis bugs
2. Legibilidade
3. Segurança
4. Performance
5. Testes ausentes
6. Riscos de regressão
7. Documentação

DIFF:
[cole o diff]

Apresente análise estruturada em etapas claras, objetivas e verificáveis.
Para cada critério, aponte problemas ou declare: Nenhum problema encontrado nesta categoria.
```

#### 4. Criar documentação técnica

```text
Atue como Tech Lead. Crie documentação técnica para o endpoint fornecido.
Use tags XML: <endpoint>, <parametros>, <retorno>.
Apresente análise estruturada em etapas claras, objetivas e verificáveis para validar tipagens.

CÓDIGO:
[cole o código]
```

#### 5. Planejar arquitetura

```text
Você é Arquiteto de Software. Planeje [OBJETIVO DO SISTEMA].

Etapa 1: entidades de banco.
Etapa 2: endpoints da API REST.
Etapa 3: principais riscos e trade-offs.

Restrições:
[ex.: não usar NoSQL, manter compatibilidade com sistema legado]
```

#### 6. Criar testes

```text
Siga este padrão:

Função:
[exemplo de função]

Teste:
[exemplo de teste]

Com base no padrão, analise casos de sucesso e falha em etapas verificáveis e escreva os testes.

CÓDIGO:
[cole o código]
```

## Materiais complementares

A pasta [`docs`](docs) contém os registros completos e materiais de apoio, mas o README foi estruturado para funcionar como a entrega principal do desafio. Ela não substitui o README; apenas aprofunda o que já foi consolidado aqui:

- [`docs/fontes.md`](docs/fontes.md): detalhamento das fontes usadas no caderno.
- [`docs/prompts-testados.md`](docs/prompts-testados.md): registro completo dos prompts testados.
- [`docs/cicatrizes.md`](docs/cicatrizes.md): erros, ajustes e aprendizados do processo.
- [`docs/miniguia.md`](docs/miniguia.md): versão complementar do miniguia de estudo.

## Conclusão

A Engenharia de Prompts não é apenas "fazer perguntas para a IA". Ela envolve clareza, contexto, restrições, formato esperado e validação crítica.

No desenvolvimento de software, bons prompts podem acelerar o aprendizado, apoiar debugging, organizar documentação, orientar revisões de código e ajudar na criação de testes. Porém, a IA não substitui a pessoa desenvolvedora. O modelo gera respostas com base no contexto recebido, mas não compila o projeto, não garante segurança e não valida regras de negócio.

Todo código gerado precisa ser testado. Decisões de arquitetura, segurança, qualidade e regra de negócio continuam sob responsabilidade humana. A melhor forma de usar IA no desenvolvimento é tratá-la como apoio técnico: útil para organizar ideias, levantar hipóteses e estruturar análises, mas sempre com revisão, testes e senso crítico.

## Referências

1. Google. **NotebookLM — Add or discover new sources for your notebook**
   https://support.google.com/notebooklm/answer/16215270?co=GENIE.Platform%3DDesktop&hl=pt-BR

2. OpenAI. **Prompt engineering | OpenAI API**
   https://developers.openai.com/api/docs/guides/prompt-engineering

3. OpenAI. **Prompt guidance | OpenAI API**
   https://developers.openai.com/api/docs/guides/prompt-guidance

4. Microsoft Learn. **Prompt engineering techniques**
   https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/prompt-engineering

5. GitHub Docs. **Helping others review your changes**
   https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/helping-others-review-your-changes
