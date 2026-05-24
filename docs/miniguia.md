# Miniguia de estudo

Engenharia de Prompts para Desenvolvimento de Software com IA — consolidação do caderno NotebookLM para pessoas em nível iniciante a intermediário.

---

## 1. O que é Engenharia de Prompts?

É o processo de escrever, estruturar e otimizar instruções (prompts) para que o modelo de linguagem gere conteúdo alinhado aos requisitos técnicos. A saída é **não determinística**: o modelo prevê a próxima unidade de texto com base no contexto fornecido. Por isso a formulação do comando e a avaliação iterativa importam tanto quanto a “primeira tentativa”.

*Fontes: OpenAI — Prompt engineering; Microsoft — Prompt engineering techniques.*

---

## 2. Design de prompts vs. Engenharia de prompts

| | Design de prompts | Engenharia de prompts |
|---|-------------------|------------------------|
| **Foco** | Criar o comando inicial em linguagem natural | Refinar, estruturar e avaliar comandos ao longo do tempo |
| **Quando basta** | Tarefas mais simples | Tarefas complexas que exigem precisão e repetibilidade |
| **Práticas** | Tarefa, instruções de sistema, exemplos, contexto | Iteração, few-shot, delimitadores, métricas de qualidade da resposta |

*Neste projeto, o termo **design de prompts** foi usado para representar a criação inicial da instrução, enquanto **engenharia de prompts** foi usado para representar o processo mais amplo de testar, avaliar e refinar prompts para obter resultados mais consistentes. As técnicas estruturais (instruções, conteúdo primário, contexto de suporte, few-shot e formato de saída) estão em Microsoft e OpenAI.*

---

## 3. Por que isso importa para pessoas desenvolvedoras?

- **Precisão** — Grounding com código, logs e regras de negócio reduz respostas genéricas e inventadas.
- **Integração** — Saídas em Markdown, JSON ou XML facilitam uso em pipelines e documentação.
- **Custo e limites** — Prompts enxutos respeitam tokens e a janela de contexto (*space efficiency* — Microsoft).
- **Colaboração** — Prompts alinhados a PRs pequenos e descritivos combinam com fluxo GitHub e apoio da IA sem substituir revisão humana.

O modelo **organiza e gera** texto; não executa nem garante correção do sistema em produção sem validação local.

---

## 4. Elementos de um bom prompt técnico

1. **Instruções** — Papel e tarefa (ex.: “Atue como Engenheira de Software Sênior e documente este endpoint”).
2. **Conteúdo primário** — Código, diff, stack trace.
3. **Contexto de suporte** — Stack, versões, domínio, issue relacionada.
4. **Exemplos (few-shot)** — Pares entrada/saída para testes ou formatação.
5. **Gatilhos / sintaxe** — Delimitadores, tags XML, cabeçalhos Markdown, frase que dispara o formato (“Retorne apenas o JSON abaixo”).

*Fontes: Microsoft — Prompt engineering techniques; OpenAI — Prompt engineering.*

---

## 5. Principais aplicações no desenvolvimento de software

| Aplicação | Ideia central |
|-----------|----------------|
| Aprender nova tecnologia | Persona + limite de tamanho + estrutura da explicação |
| Debugging | Grounding com código + erro + análise em etapas verificáveis |
| Revisão de PR | Critérios explícitos + diff + apoio preliminar (não substituto) |
| Documentação técnica | Formato de saída fixo (Markdown/XML) |
| Arquitetura | Etapas sequenciais + restrições negativas |
| Testes | Few-shot com padrão de teste desejado + edge cases |

Detalhes com exemplos fraco/melhorado: [prompts-testados.md](prompts-testados.md) (Prompt 3).

---

## 6. Erros comuns

1. Respostas genéricas demais  
2. Ausência de contexto do projeto  
3. Código ou erro incompleto  
4. Formato de saída indefinido  
5. Restrições não informadas  
6. Falta de validação humana da resposta  
7. PR ou trecho grande demais num único prompt  
8. Instruções e dados sem delimitação  
9. Ausência de saída segura (“informação não encontrada”)  

Expandido em [cicatrizes.md](cicatrizes.md).

---

## 7. Boas práticas

- **Seja específico** — Defina o que fazer e o que não fazer.  
- **Use sintaxe clara** — `---`, tags `<codigo>`, cabeçalhos `###`.  
- **Divida a tarefa** — Uma etapa ou critério por vez em tarefas complexas.  
- **Exija análise em etapas verificáveis** — A resposta apresenta etapas claras, objetivas e verificáveis, sem pedir processos internos ao modelo.  
- **Dê rota de escape** — “Se não houver evidência no material, diga que não encontrou.”  
- **Valide localmente** — Compile, teste, revise dependências e faça self-review do PR antes da equipe.

*Fontes: Microsoft; OpenAI; GitHub Docs.*

---

## 8. Glossário

| Termo | Definição |
|--------|-----------|
| **Zero-shot** | Pedido sem exemplos no prompt. |
| **Few-shot** | Um ou mais exemplos entrada/saída no prompt para condicionar formato. |
| **Tokens** | Unidades de processamento do modelo; impactam custo e limite. |
| **Janela de contexto** | Máximo de tokens que o modelo retém numa requisição. |
| **Viés de recência** | Tendência de priorizar instruções no final do prompt. |
| **Grounding** | Ancorar a resposta em dados fornecidos (código, logs, fontes do caderno). |
| **Alucinação** | Saída plausível porém falsa por falta de embasamento. |
| **Metaprompting** | Usar a IA para sugerir melhorias no próprio prompt. |
| **Primary / supporting content** | Material principal a analisar vs. contexto auxiliar (stack, negócio). |
| **Message roles** | Papéis system/developer, user e assistant na API. |
| **Saída segura (“out”)** | Comportamento definido quando a informação não existe no input. |

---

## 9. Prompts reutilizáveis

### Estudar uma tecnologia

```
Atue como um Engenheiro de Software Sênior. Explique o conceito de [TECNOLOGIA] para um desenvolvedor júnior.
Apresente uma análise estruturada em etapas claras, objetivas e verificáveis.
Limite a resposta a 3 parágrafos e use lista de marcadores para os principais benefícios.
```

### Analisar um erro (resumido)

```
STACK: [linguagem, framework, versões]
ERRO: [log completo]
CÓDIGO: [trecho relevante]

Apresente análise estruturada em etapas claras, objetivas e verificáveis e proponha correção em Markdown.
```

### Revisar um Pull Request (resumido)

```
OBJETIVO DO PR: [propósito]
ORDEM DE LEITURA: [arquivos]
DIFF: [alterações]

Apoio preliminar — avalie: bugs, legibilidade, segurança, performance, testes ausentes, regressão, documentação.
Análise em etapas claras, objetivas e verificáveis. Formato Markdown com cabeçalhos por critério.
```

### Criar documentação técnica

```
Atue como Tech Lead. Documente o endpoint abaixo com tags <endpoint>, <parametros>, <retorno>.
Análise em etapas para validar tipagens.

CÓDIGO:
[cole o código]
```

### Planejar arquitetura

```
Você é Arquiteto de Software. Planeje [OBJETIVO DO SISTEMA].
Etapa 1: entidades de banco. Etapa 2: endpoints da API REST.
Restrição: [ex.: não usar NoSQL]
```

### Criar testes (few-shot)

```
Padrão:
Função: def soma(a, b): return a + b
Teste: def test_soma(): assert soma(2, 2) == 4

Analise sucesso e falha em etapas verificáveis e gere testes no mesmo padrão.

CÓDIGO:
[cole o código]
```

---

## Template — análise de erro de programação

```
Atue como Engenheiro de Software Sênior especialista em resolução de problemas.
Analise as informações abaixo, identifique a causa raiz e proponha a solução mais adequada.
Apresente uma análise estruturada em etapas claras, objetivas e verificáveis.
Siga as restrições e formate em Markdown com blocos de código nas sugestões.

### 1. CONTEXTO DO PROJETO
[descrição do módulo ou produto]

### 2. STACK TECNOLÓGICA
[linguagem, frameworks, versões]

### 3. OBJETIVO DA FUNCIONALIDADE
[o que o código deveria fazer]

### 4. COMPORTAMENTO ESPERADO
[resultado desejado]

### 5. COMPORTAMENTO ATUAL
[o que ocorre de errado]

### 6. TENTATIVAS JÁ REALIZADAS
[o que já foi testado sem sucesso]

### 7. RESTRIÇÕES IMPORTANTES
[o que a IA não deve sugerir]

---

### 8. CÓDIGO RELEVANTE
```[linguagem]
[cole o trecho]
```

### 9. MENSAGEM DE ERRO COMPLETA
[cole stack trace ou log]
```

---

## Template — revisão de Pull Request

```
Você é Engenheiro de Software Sênior. Atue como apoio preliminar na revisão deste Pull Request.
A análise é para revisores humanos — não substitui aprovação final.

Apresente análise estruturada em etapas claras, objetivas e verificáveis.
Para cada critério, aponte problemas ou declare: Nenhum problema encontrado nesta categoria.
Use Markdown e blocos de código nas sugestões.

### CONTEXTO DO PULL REQUEST
- Propósito: [descrição]
- Ordem de leitura: [arquivos]
- Issues: [ex.: Closes #142]

### CRITÉRIOS OBRIGATÓRIOS
1. Possíveis bugs
2. Legibilidade
3. Segurança
4. Performance
5. Testes ausentes
6. Riscos de regressão
7. Clareza da documentação

### CÓDIGO MODIFICADO (DIFF)
[cole o diff ou arquivos alterados]
```

---

## 10. Conclusão crítica sobre os limites da IA

A engenharia de prompts **maximiza** o valor dos modelos de linguagem, mas a IA continua sendo **ferramenta de apoio** e **não substitui** a pessoa desenvolvedora. O modelo gera respostas a partir de padrões estatísticos de texto; não compila o projeto nem compreende de forma infalível as regras de negócio da organização. **Todo código sugerido precisa ser testado** antes de integração. Pode haver dependências vulneráveis ou cenários de borda ignorados nos testes gerados.

Na revisão de código, a IA funciona como **apoio preliminar** — resumo, checklist, hipóteses — enquanto arquitetura, semântica de negócio, segurança e merge seguro dependem da equipe, com revisão humana, testes automatizados e ferramentas oficiais (Code Scanning, advisory de dependências, self-review — GitHub Docs).

**Regra prática:** trate toda saída como rascunho verificável.

---

## Referências rápidas

- [fontes.md](fontes.md) — detalhamento das cinco fontes do caderno  
- [prompts-testados.md](prompts-testados.md) — registro das solicitações ao NotebookLM  
- [cicatrizes.md](cicatrizes.md) — erros e correções do processo
