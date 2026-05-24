# Prompts testados

Registro dos prompts utilizados no chat do NotebookLM sobre as fontes adicionadas, com objetivo, texto da solicitação, resultado observado na síntese do caderno e aprendizado.

---

## Prompt 1 — Mapear conceitos por fonte

**Objetivo**

Listar os principais conceitos sobre engenharia de prompts, design de prompts, uso de fontes no NotebookLM e boas práticas de revisão de PRs, indicando a fonte de cada conceito.

**Prompt utilizado**

```
Com base apenas nas fontes adicionadas, liste quais são os principais conceitos encontrados sobre Engenharia de Prompts, design de prompts, uso de fontes no NotebookLM e boas práticas para revisão de Pull Requests.

Para cada conceito, indique de qual fonte ele veio.
```

**Resultado observado**

O NotebookLM retornou quatro blocos temáticos com conceitos mapeados às cinco fontes do caderno: definição iterativa e papéis de mensagem (OpenAI), few-shot e técnicas estruturais (Microsoft), limites e sumarização no NotebookLM (Google), PRs pequenos e self-review (GitHub), entre outros.

**Aprendizado obtido**

Restringir a pergunta às “fontes adicionadas” mantém o embasamento no caderno. Pedir a origem por conceito facilita a documentação do portfólio e evita misturar conceitos sem rastreio.

---

## Prompt 2 — Resumo inicial

**Objetivo**

Gerar um resumo sobre engenharia de prompts aplicada ao desenvolvimento de software, cobrindo definição, diferença design vs. engenharia, importância para desenvolvedoras(es), contribuição das fontes e conceitos úteis por cenário.

**Prompt utilizado**

```
Com base apenas nas fontes adicionadas agora, gere um resumo inicial sobre Engenharia de Prompts aplicada ao desenvolvimento de software.

A resposta deve explicar:
- O que é Engenharia de Prompts;
- Qual a diferença entre design de prompts e engenharia de prompts;
- Por que essa habilidade é importante para pessoas desenvolvedoras;
- Como as fontes da OpenAI, Microsoft, Google NotebookLM e GitHub contribuem para este estudo;
- Quais conceitos serão mais úteis para criar prompts de debugging, documentação, revisão de Pull Request e aprendizado técnico.

Organize em Markdown e indique de qual fonte vieram os principais conceitos.
```

**Resultado observado**

Resumo estruturado em cinco seções: definição (processo iterativo, saída não determinística), distinção design (tarefas simples) vs. engenharia (iteração e avaliação), benefícios (precisão, grounding, formatos estruturados, tokens), papel de cada plataforma e conceitos por cenário (grounding e análise em etapas para debugging; formato de saída para documentação; break down e PRs pequenos para revisão; few-shot e instruções de sistema para aprendizado).

**Aprendizado obtido**

Especificar seções obrigatórias na pergunta produz material quase pronto para README e miniguia, sem precisar reformatar manualmente depois.

---

## Prompt 3 — Seis aplicações práticas

**Objetivo**

Documentar seis formas práticas de usar engenharia de prompts, cada uma com objetivo, situação, prompt ruim, prompt melhorado, por que o melhorado funciona e cuidados.

**Prompt utilizado**

```
Com base nas fontes adicionadas, liste formas práticas de usar Engenharia de Prompts no desenvolvimento de software.

A resposta deve trazer exatamente 6 aplicações:
1. Aprender uma nova tecnologia;
2. Entender e corrigir erros de programação;
3. Revisar Pull Requests;
4. Criar documentação técnica;
5. Planejar arquitetura de software;
6. Criar testes.

Para cada aplicação, use obrigatoriamente esta estrutura:
- Objetivo da aplicação;
- Situação prática no dia a dia de uma pessoa desenvolvedora;
- Exemplo de prompt ruim;
- Exemplo de prompt melhorado;
- Por que o prompt melhorado é mais eficiente;
- Cuidados ou limitações ao usar IA nessa situação.

Use as fontes adicionadas para embasar as boas práticas. Não deixe nenhum campo em branco.
Quando necessário, use a expressão "análise estruturada em etapas claras e verificáveis".
```

**Resultado observado**

Seis blocos completos, com exemplos comparativos (React, TS2532, PR com diff, API REST, estoque em microsserviços, pytest). Cada “melhorado” cita práticas das fontes: persona, delimitadores, grounding, break down, few-shot e restrições.

**Aprendizado obtido**

Exigir estrutura fixa e número exato de aplicações evita respostas incompletas. Incluir na solicitação a formulação alternativa a “Chain of Thought” alinha o tom do repositório desde a geração.

---

## Prompt 4 — Modelo de prompt para debugging

**Objetivo**

Criar modelo completo para análise de erro, com dez campos, explicação de cada um e template reutilizável.

**Prompt utilizado**

```
Com base nas fontes adicionadas, crie um modelo completo de prompt para pedir ajuda a uma IA na análise de um erro de programação.

O modelo deve conter:
- Contexto do projeto;
- Linguagem, framework e stack utilizada;
- Objetivo da funcionalidade;
- Código ou trecho relevante;
- Mensagem de erro completa;
- Comportamento esperado;
- Comportamento atual;
- Tentativas já realizadas;
- Restrições importantes;
- Formato esperado da resposta.

Depois, explique por que cada campo ajuda a IA a produzir uma resposta melhor.
Ao final, gere um template reutilizável em Markdown.
Evite recomendar "Chain of Thought". Prefira análise estruturada em etapas claras, objetivas e verificáveis.
```

**Resultado observado**

Explicação campo a campo (supporting content, primary content, grounding, restrições, output structure) e template com seções numeradas, delimitadores em maiúsculas e blocos de código para código e erro.

**Aprendizado obtido**

Pedir template + justificativa gera documentação didática e ferramenta prática no mesmo passo. Campos de comportamento esperado/atual e tentativas já realizadas reduzem sugestões genéricas repetidas.

---

## Prompt 5 — Modelo de prompt para revisão de PR

**Objetivo**

Definir uso de IA como apoio preliminar em PRs: informações necessárias, sete critérios, exemplos ruim/melhorado, template e limitações.

**Prompt utilizado**

```
Com base nas fontes adicionadas, crie um modelo completo de prompt para usar IA na revisão de Pull Requests.

A resposta deve conter:
- Objetivo do uso de IA na revisão de Pull Requests;
- Quais informações devem ser fornecidas para a IA antes da revisão;
- Critérios que a IA deve avaliar (bugs, legibilidade, segurança, performance, testes ausentes, regressão, documentação);
- Um exemplo de prompt ruim;
- Um exemplo de prompt melhorado;
- Um template reutilizável em Markdown;
- Cuidados e limitações.

Considere boas práticas do GitHub sobre PRs pequenos, contexto claro e revisão própria.
A IA deve ser apresentada como apoio preliminar, não substituta da revisão humana.
```

**Resultado observado**

Texto alinhado ao GitHub (PR pequeno, self-review, security) e à Microsoft (break down, critérios explícitos). Template com contexto, ordem de leitura, sete critérios obrigatórios e seção DIFF. Ênfase em não substituir revisão humana nem ferramentas oficiais de segurança.

**Aprendizado obtido**

Declarar na solicitação o papel “apoio preliminar” evita tom de automação total na resposta. Combinar critérios técnicos com práticas de fluxo GitHub produz checklist útil para revisores humanos.

---

## Prompt 6 — Erros comuns ao escrever prompts

**Objetivo**

Listar nove erros com estrutura completa (erro, fraco, por que falha, melhorado, boa prática, uso no dia a dia).

**Prompt utilizado**

```
Com base nas fontes adicionadas e nos testes de prompts realizados, explique quais são os principais erros cometidos ao escrever prompts para desenvolvimento de software.

Inclua erros como:
- pedir respostas genéricas demais;
- não fornecer contexto do projeto;
- não informar código ou erro completo;
- não definir formato esperado;
- não informar restrições;
- não validar a resposta da IA;
- usar PRs ou trechos grandes demais sem dividir a análise;
- não diferenciar instruções de sistema, entrada do usuário e contexto;
- não dar uma saída segura para a IA quando ela não souber responder.

Organize em Markdown e cite as fontes utilizadas quando possível.
```

**Resultado observado**

Nove entradas estruturadas, cada uma com exemplo fraco/melhorado e boa prática nomeada (Be specific, grounding, output structure, break down, message roles, model “out”, self-review).

**Aprendizado obtido**

Referenciar “testes realizados” na pergunta conecta teoria (fontes) com prática (comparativos dos prompts 3–5). Este prompt alimenta diretamente `cicatrizes.md`.

---

## Prompt 7 — Miniguia de estudo

**Objetivo**

Consolidar miniguia com introdução, aplicações, erros, boas práticas, glossário, templates e conclusão crítica.

**Prompt utilizado**

```
Com base nas fontes adicionadas e nos testes de prompts realizados, crie um miniguia de estudo sobre Engenharia de Prompts para Desenvolvimento de Software com IA.

O miniguia deve conter:
- Introdução curta;
- Diferença entre design e engenharia de prompts;
- Por que é importante para pessoas desenvolvedoras;
- Elementos de um bom prompt técnico;
- Principais aplicações;
- Erros comuns;
- Boas práticas;
- Glossário;
- Lista de prompts reutilizáveis (estudar tecnologia, erro, PR, documentação, arquitetura, testes);
- Conclusão crítica sobre os limites da IA.

Evite a expressão "a IA pensa". Prefira "a IA organiza", "o modelo gera", "a resposta é estruturada".
```

**Resultado observado**

Miniguia em dez seções, glossário (zero-shot, few-shot, tokens, recency bias, context window, alucinação) e templates resumidos. Conclusão reforça validação humana e limites estatísticos do modelo.

**Aprendizado obtido**

Um último prompt de consolidação, com índice explícito, funciona como “compilação” do caderno para exportar ao repositório. Restrições de linguagem na solicitação mantêm consistência ética e técnica do material.
