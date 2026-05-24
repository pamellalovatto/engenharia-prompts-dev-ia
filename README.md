# Engenharia de Prompts para Desenvolvimento de Software com IA

Repositório de portfólio — entrega DIO. Documentação derivada de um caderno temático no **Google NotebookLM**, com curadoria de fontes oficiais sobre engenharia de prompts, uso de fontes no NotebookLM e boas práticas de revisão de Pull Requests.

## Contexto do projeto

Este projeto consolida o estudo de **Engenharia de Prompts** aplicada ao desenvolvimento de software com IA. O trabalho partiu da adição de cinco fontes oficiais ao NotebookLM, da síntese dos conceitos no chat do caderno e da experimentação de prompts orientados a cenários reais (debugging, documentação, revisão de PR, aprendizado técnico, arquitetura e testes).

A IA é tratada como **ferramenta de apoio**: o modelo gera texto de forma probabilística; a validação, os testes e as decisões de merge permanecem com a pessoa desenvolvedora.

## Objetivos

- Montar um repositório de portfólio com base no caderno temático do NotebookLM.
- Documentar fontes selecionadas, processo de curadoria e contribuição de cada fonte.
- Registrar prompts testados, resultados observados e aprendizados.
- Registrar erros e ajustes do processo (cicatrizes).
- Entregar um miniguia reutilizável para estudo e uso no dia a dia.

## Ferramenta utilizada

**Google NotebookLM** — ingestão de fontes (URLs, PDFs, Drive, YouTube), sumarização via Source Guide e chat com respostas embasadas no material adicionado ao caderno.

## Fontes selecionadas

| # | Fonte |
|---|--------|
| 1 | [Google NotebookLM — Add or discover new sources for your notebook](https://support.google.com/notebooklm/answer/16215270?co=GENIE.Platform%3DDesktop&hl=pt-BR) |
| 2 | [OpenAI — Prompt engineering \| OpenAI API](https://developers.openai.com/api/docs/guides/prompt-engineering) |
| 3 | [OpenAI — Prompt guidance \| OpenAI API](https://developers.openai.com/api/docs/guides/prompt-guidance) |
| 4 | [Microsoft Learn — Prompt engineering techniques](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/prompt-engineering) |
| 5 | [GitHub Docs — Helping others review your changes](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/helping-others-review-your-changes) |

Detalhamento em [docs/fontes.md](docs/fontes.md).

## Processo de curadoria

1. **Seleção** — Cinco fontes complementares: gestão de fontes no NotebookLM, diretrizes OpenAI (engenharia e orientação), técnicas Microsoft e colaboração em PRs no GitHub.
2. **Ingestão** — Fontes adicionadas ao caderno do NotebookLM (limite de 50 fontes, até 500.000 palavras por fonte).
3. **Síntese** — Perguntas estruturadas no chat para extrair conceitos, resumo inicial, seis aplicações práticas, modelos de prompt, erros comuns e miniguia final.
4. **Testes** — Comparação de prompts fracos e melhorados nos cenários documentados; templates reutilizáveis para debugging e revisão de PR.
5. **Consolidação** — Material organizado neste repositório, com substituição de “Chain of Thought” por **análise estruturada em etapas claras, objetivas e verificáveis** nas orientações aos modelos.

## Prompts testados no NotebookLM

| Tema | Objetivo resumido |
|------|-------------------|
| Conceitos por fonte | Mapear conceitos de engenharia de prompts, design, NotebookLM e PRs |
| Resumo inicial | Explicar o que é engenharia de prompts e contribuição das fontes |
| Seis aplicações | Documentar uso prático com prompt ruim vs. melhorado |
| Modelo de debugging | Template com 10 campos para análise de erros |
| Modelo de revisão de PR | Critérios, exemplos e template com apoio preliminar |
| Erros comuns | Nove erros com fraco/melhorado e boas práticas |
| Miniguia | Consolidação final para estudo |

Registro completo em [docs/prompts-testados.md](docs/prompts-testados.md).

## Principais aprendizados

- **Engenharia vs. design** — Design de prompts: criação inicial da instrução; engenharia de prompts: processo de testar, avaliar e refinar para resultados mais consistentes (OpenAI, Microsoft).
- **Estrutura do prompt** — Instruções, conteúdo primário, contexto de suporte, exemplos (few-shot) e delimitadores (Markdown, XML, cabeçalhos) melhoram a assertividade.
- **Embasamento (grounding)** — Código, logs e diff completos reduzem alucinações; omitir contexto força o modelo a adivinhar.
- **Tarefas complexas** — Dividir a análise em etapas e critérios explícitos (segurança, legibilidade, testes) produz respostas mais úteis que pedidos genéricos.
- **PRs e contexto** — PRs pequenos, descrição clara, ordem de leitura e self-review alinham boas práticas humanas com limites de janela de contexto da IA.
- **Validação humana** — Respostas da IA são rascunho; compilar, testar, revisar dependências e usar ferramentas oficiais de segurança continuam obrigatórios.

## Cicatrizes do processo

Durante os testes, ficou evidente que prompts vagos, contexto omitido, PRs grandes e ausência de formato de saída geram respostas genéricas ou incompletas. O registro detalhado (fraco → melhorado) está em [docs/cicatrizes.md](docs/cicatrizes.md).

## Miniguia de estudo

Guia consolidado com introdução, elementos de um bom prompt, aplicações, erros, boas práticas, glossário e templates: [docs/miniguia.md](docs/miniguia.md).

## Glossário

| Termo | Definição breve |
|--------|------------------|
| **Engenharia de prompts** | Processo de escrever e otimizar instruções para o modelo gerar saídas consistentes com os requisitos. |
| **Design de prompts** | Construção direta do comando em linguagem natural, em geral para tarefas mais simples. |
| **Few-shot** | Inclusão de exemplos entrada/saída no prompt para condicionar formato e estilo. |
| **Grounding** | Fornecer dados ou textos exatos nos quais a resposta deve se basear. |
| **Tokens / janela de contexto** | Unidades de processamento e limite de memória por requisição. |
| **Alucinação** | Saída plausível porém incorreta ou inventada por falta de embasamento. |
| **Metaprompting** | Usar a IA para inspecionar erros e sugerir melhorias no prompt original. |
| **Saída segura (“out”)** | Instruir o modelo a declarar ausência de informação em vez de inventar. |

## Prompts reutilizáveis

### Estudar uma tecnologia

```
Atue como um Engenheiro de Software Sênior. Explique o conceito de [TECNOLOGIA] para um desenvolvedor júnior.
Apresente uma análise estruturada em etapas claras, objetivas e verificáveis.
Limite a resposta a 3 parágrafos e use lista de marcadores para os principais benefícios.
```

### Analisar um erro (debugging)

Ver template completo em [docs/miniguia.md](docs/miniguia.md#template--análise-de-erro-de-programação).

### Revisar um Pull Request (apoio preliminar)

Ver template completo em [docs/miniguia.md](docs/miniguia.md#template--revisão-de-pull-request).

### Criar documentação técnica

```
Atue como Tech Lead. Crie documentação técnica para o endpoint fornecido.
Use tags XML: <endpoint>, <parametros>, <retorno>.
Apresente análise estruturada em etapas claras, objetivas e verificáveis para validar tipagens.

CÓDIGO:
[cole o código]
```

### Planejar arquitetura

```
Você é Arquiteto de Software. Planeje microsserviços para [OBJETIVO].
Análise em etapas: (1) entidades de banco; (2) rotas da API.
Restrição: [ex.: não usar NoSQL]
```

### Criar testes (few-shot)

```
Siga este padrão:
Função: [exemplo]
Teste: [exemplo]

Com base no padrão, analise casos de sucesso e falha em etapas verificáveis e escreva os testes.

CÓDIGO:
[cole o código]
```

## Conclusão crítica

A engenharia de prompts aumenta a qualidade e a previsibilidade das respostas, mas a IA permanece **ferramenta de apoio** e **não substitui** a pessoa desenvolvedora. O modelo organiza e gera texto a partir de padrões estatísticos; não compila nem garante correção semântica do sistema real. **Todo código gerado precisa ser testado** antes de ir para produção. Revisão humana, segurança, regras de negócio e decisões de arquitetura continuam sob responsabilidade da equipe, com testes automatizados e ferramentas oficiais do repositório. Em revisão de PR, a IA oferece apoio preliminar — não auditoria final.

## Referências

1. Google. *NotebookLM — Add or discover new sources for your notebook*. https://support.google.com/notebooklm/answer/16215270?co=GENIE.Platform%3DDesktop&hl=pt-BR
2. OpenAI. *Prompt engineering*. OpenAI API documentation. https://developers.openai.com/api/docs/guides/prompt-engineering
3. OpenAI. *Prompt guidance*. OpenAI API documentation. https://developers.openai.com/api/docs/guides/prompt-guidance
4. Microsoft. *Prompt engineering techniques*. Microsoft Learn. https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/prompt-engineering
5. GitHub. *Helping others review your changes*. GitHub Docs. https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/helping-others-review-your-changes
