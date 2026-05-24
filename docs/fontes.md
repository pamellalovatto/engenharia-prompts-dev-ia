# Fontes do projeto

Documentação das cinco fontes oficiais do caderno temático e de como cada uma contribuiu para o estudo.

## Lista de fontes

| Fonte | URL |
|--------|-----|
| Google NotebookLM — Add or discover new sources | https://support.google.com/notebooklm/answer/16215270?co=GENIE.Platform%3DDesktop&hl=pt-BR |
| OpenAI — Prompt engineering | https://developers.openai.com/api/docs/guides/prompt-engineering |
| OpenAI — Prompt guidance | https://developers.openai.com/api/docs/guides/prompt-guidance |
| Microsoft Learn — Prompt engineering techniques | https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/prompt-engineering |
| GitHub Docs — Helping others review your changes | https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/helping-others-review-your-changes |

---

## Por fonte

### 1. Google NotebookLM — Add or discover new sources

**Por que foi escolhida**

É a documentação da ferramenta central do projeto: define como adicionar fontes, limites do caderno e recursos de sumarização que sustentam a curadoria.

**Como contribuiu para o projeto**

- Tipos suportados: áudio, texto, Google Docs/Slides/Sheets, imagens, PDF, URLs e YouTube público.
- Limites: até **50 fontes** por caderno, **500.000 palavras** por fonte.
- **Source Guide** e chat para resumos por tópico ou do documento inteiro.
- Sincronização com **Google Drive** (botão “Click to sync with Google Drive”) para fontes atualizadas sem reenvio manual.
- Base prática para **grounding**: respostas do chat ancoradas no material ingerido, alinhado ao uso de contexto em prompts técnicos.

**Conceitos extraídos (origem)**

| Conceito | Contribuição |
|----------|----------------|
| Tipos e limites de fontes | Estrutura do caderno e planejamento da curadoria |
| Sumarização / Source Guide | Processo de estudo e extração de conceitos |
| Sincronização Drive | Manutenção de fontes vivas no caderno |

---

### 2. OpenAI — Prompt engineering

**Por que foi escolhida**

Referência direta para APIs e práticas de escrita de instruções: papéis de mensagem, few-shot, formatação e integração com desenvolvimento de software.

**Como contribuiu para o projeto**

- **Definição e processo iterativo** — engenharia de prompts como escrita de instruções efetivas, com testes contínuos (arte + ciência).
- **Papéis de mensagem** — `developer`/`system`, `user`, `assistant` para separar regras, entrada e resposta.
- **Few-shot learning** — exemplos entrada/saída para condicionar comportamento.
- **Formatação** — Markdown, tags XML e estrutura de mensagens para delimitar instruções e dados.
- **Contexto para debugging e documentação** — incluir código e logs relevantes; definir formato de saída.

**Conceitos extraídos (origem)**

| Conceito | Fonte |
|----------|--------|
| Definição e iteração | OpenAI — Prompt engineering |
| Message roles | OpenAI — Prompt engineering |
| Few-shot | OpenAI — Prompt engineering (+ Microsoft) |
| Include relevant context / output structure | OpenAI — Prompt engineering |

---

### 3. OpenAI — Prompt guidance

**Por que foi escolhida**

Complementa a engenharia com orientações sobre refinamento de prompts, resultados esperados e uso da própria IA para melhorar instruções.

**Como contribuiu para o projeto**

- **Metaprompting** — usar a IA para inspecionar falhas e sugerir melhorias no prompt original.
- **Outcome-first** — comandos orientados ao resultado desejado (comportamento esperado vs. atual).
- Preferir **análise estruturada em etapas claras, objetivas e verificáveis** e descrição do resultado esperado, em vez de pedir que o modelo exponha processos internos.

**Conceitos extraídos (origem)**

| Conceito | Fonte |
|----------|--------|
| Metaprompting | OpenAI — Prompt guidance |
| Foco em resultado, não em passos internos da IA | OpenAI — Prompt guidance |

---

### 4. Microsoft Learn — Prompt engineering techniques

**Por que foi escolhida**

Oferece taxonomia estrutural do prompt e técnicas universais aplicáveis a debugging, documentação, PRs e testes.

**Como contribuiu para o projeto**

- **Componentes do prompt** — instruções, conteúdo primário, exemplos, gatilhos, contexto de suporte.
- **Few-shot** e comparação com zero-shot.
- **Sintaxe clara e delimitadores** — Markdown, cabeçalhos, tags.
- **Break the task down** — etapas menores (extrair fatos, depois responder).
- **Grounding** — dados exatos no prompt para reduzir alucinações.
- **Análise em etapas** — para tarefas complexas, com **análise estruturada em etapas claras, objetivas e verificáveis**.
- **Specifying output structure** — JSON, Markdown, tabelas.
- **Space efficiency** — uso consciente de tokens e janela de contexto.
- **Give the model an “out”** — resposta segura quando a informação não existir no material.

**Conceitos extraídos (origem)**

| Conceito | Fonte |
|----------|--------|
| Few-shot, grounding, break task down | Microsoft — Prompt engineering techniques |
| Output structure, clear syntax | Microsoft — Prompt engineering techniques |
| Primary / supporting content | Microsoft — Prompt engineering techniques |
| Model “out” / missing evidence | Microsoft — Prompt engineering techniques |

---

### 5. GitHub Docs — Helping others review your changes

**Por que foi escolhida**

Conecta engenharia de prompts ao fluxo real de colaboração: PRs pequenos, contexto para revisores e revisão própria antes de pedir feedback.

**Como contribuiu para o projeto**

- **PRs pequenos e focados** — revisão mais rápida, menos bugs, histórico claro; alinhado ao limite de contexto da IA.
- **Contexto e ordem de leitura** — propósito, visão geral e por onde começar no diff.
- **Self-review** — build, testes e revisão da autoria antes da equipe (e antes de usar IA como apoio).
- **Security review** — dependency diff, Code Scanning.
- **IA como apoio** — Copilot para descrições/resumos de PR (apoio, não substituição).
- **Labels e issues** — clareza de status e vínculo com issues.

**Conceitos extraídos (origem)**

| Conceito | Fonte |
|----------|--------|
| Write small PRs | GitHub Docs |
| Context + reading order | GitHub Docs |
| Self-review | GitHub Docs |
| Security / dependency review | GitHub Docs |
| AI summaries (Copilot) | GitHub Docs |

---

## Mapa rápido: tópico → fontes

| Tópico | Fontes principais |
|--------|-------------------|
| Engenharia de prompts | OpenAI (engineering, guidance), Microsoft |
| Design de prompts | Uso no projeto (instrução inicial); técnicas estruturais em Microsoft e OpenAI |
| Uso de fontes no NotebookLM | Google NotebookLM |
| Revisão de Pull Requests | GitHub Docs; técnicas Microsoft (break down, formato); OpenAI (contexto, diff) |
