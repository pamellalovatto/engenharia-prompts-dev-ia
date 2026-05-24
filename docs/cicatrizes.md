# Cicatrizes do processo

Erros e dificuldades identificados durante a curadoria no NotebookLM e nos testes de prompts. Cada entrada registra o que falhou, a correção aplicada e o aprendizado para o dia a dia. A IA permanece como **ferramenta de apoio**; validação e decisão final são humanas.

---

## 1. Pedir respostas genéricas demais

**Situação**

Perguntas curtas no chat ou em ferramentas de código geram textos longos e pouco aplicáveis ao problema imediato.

**Prompt fraco**

```
Como funciona o React?
```

**Prompt melhorado**

```
Você é um Engenheiro Front-end Sênior. Explique o funcionamento do Virtual DOM no React para um desenvolvedor júnior em no máximo três parágrafos.
```

**Aprendizado**

Ser específico e definir persona + limite de tamanho restringe o espaço operacional do modelo (*Be specific*, instruções claras no início — Microsoft / OpenAI).

---

## 2. Não fornecer contexto do projeto

**Situação**

Sugestões de código em linguagem ou stack diferentes da do projeto.

**Prompt fraco**

```
Como faço um loop para requisições HTTP?
```

**Prompt melhorado**

```
Estou construindo um serviço em Node.js (v18) com TypeScript. Como faço um loop assíncrono para requisições HTTP?
```

**Aprendizado**

Incluir **conteúdo de suporte** (stack, versões, domínio) antes da tarefa principal (Microsoft).

---

## 3. Não informar código ou erro completo

**Situação**

Respostas que “adivinham” a implementação e aumentam alucinações.

**Prompt fraco**

```
Meu código de banco de dados está falhando ao salvar o usuário. Como arrumar?
```

**Prompt melhorado**

```
Analise o erro abaixo e sugira correção para a função fornecida.
Apresente análise estruturada em etapas claras, objetivas e verificáveis.

ERRO:
[cole stack trace]

CÓDIGO:
[cole função exata]
```

**Aprendizado**

**Conteúdo primário** + **grounding** com log e trecho reais (Microsoft / OpenAI).

---

## 4. Não definir formato esperado

**Situação**

Documentação ou listagens em texto corrido, difíceis de colar no repositório.

**Prompt fraco**

```
Faça a documentação para este código.
```

**Prompt melhorado**

```
Gere a documentação técnica do código.
Formate em Markdown com tabela para parâmetros de entrada.
```

**Aprendizado**

**Specifying the output structure** — Markdown, JSON ou XML conforme o uso (Microsoft / OpenAI).

---

## 5. Não informar restrições

**Situação**

“Otimizações” que introduzem dependências ou alteram assinaturas que quebram o sistema.

**Prompt fraco**

```
Otimize este código.
```

**Prompt melhorado**

```
Otimize este loop.
Restrições: utilize apenas JavaScript nativo (sem bibliotecas externas) e não altere o objeto retornado.
```

**Aprendizado**

Restringir o espaço operacional com regras explícitas (Microsoft / OpenAI — prompt guidance).

---

## 6. Não validar a resposta da IA

**Situação**

Código gerado integrado sem testes, com risco de vulnerabilidades ou lógica incorreta.

**Prompt fraco**

```
Escreva o sistema de login completo e me dê o código pronto.
```
*(seguido de uso direto sem revisão)*

**Prompt melhorado**

```
Escreva a função de login e, em seguida, liste possíveis falhas de segurança na própria sugestão.
```
*(seguido de compilação local, testes e revisão de dependências)*

**Aprendizado**

Combinar pedido de autoverificação no prompt com **self-review** e ferramentas de segurança do repositório (OpenAI / GitHub). O modelo gera texto; não substitui CI nem revisão humana.

---

## 7. PRs ou trechos grandes demais sem dividir a análise

**Situação**

Análise superficial por sobrecarga de contexto e perda de detalhes de segurança ou arquitetura.

**Prompt fraco**

```
Revise este Pull Request inteiro em busca de problemas de segurança, arquitetura e clean code:
[código imenso]
```

**Prompt melhorado**

```
Vamos revisar por partes. Primeiro, avalie apenas o componente de autenticação.
Critério desta rodada: possíveis vulnerabilidades de segurança.
DIFF:
[trecho focado]
```

**Aprendizado**

**Break the task down** (Microsoft) + **write small pull requests** (GitHub). Um critério ou arquivo por rodada.

---

## 8. Não diferenciar instruções, entrada e contexto

**Situação**

O modelo mistura ordens com dados a analisar, especialmente em prompts longos.

**Prompt fraco**

```
Você é sênior ache o erro no código const x = 2; console.log(y); porque está quebrando com undefined.
```

**Prompt melhorado**

```
Atue como Desenvolvedor Sênior. Identifique o erro.

--- CÓDIGO ---
const x = 2;
console.log(y);
--- FIM CÓDIGO ---

--- ERRO ---
y is not defined
--- FIM ERRO ---
```

**Aprendizado**

**Message roles** (OpenAI) + **sintaxe clara** — separadores, Markdown ou tags XML (Microsoft).

---

## 9. Não dar saída segura quando a informação não existir

**Situação**

Respostas plausíveis inventadas quando o material não contém a informação pedida.

**Prompt fraco**

```
Qual é o token de acesso que o servidor espera nesse arquivo obfuscado?
```

**Prompt melhorado**

```
Analise o arquivo para encontrar o token de acesso esperado.
Se a informação não estiver presente ou clara, responda apenas: Informação não encontrada.
```

**Aprendizado**

**Give the model an "out"** / comportamento para evidência ausente (Microsoft / OpenAI — prompt guidance).

---

## Síntese das cicatrizes

| Padrão de erro | Boa prática aplicada |
|----------------|----------------------|
| Vagueza | Especificidade, persona, limites |
| Falta de stack/contexto | Supporting content |
| Erro resumido em palavras | Grounding com log e código |
| Saída livre | Output structure (Markdown, XML, JSON) |
| Sem limites | Restrições explícitas |
| Confiança cega | Self-review + testes + segurança |
| Volume excessivo | Break down + PRs pequenos |
| Texto único misturado | Roles + delimitadores |
| Pergunta fechada sem escape | Saída segura (“não encontrado”) |

Esses padrões orientam os templates em [miniguia.md](miniguia.md) e os exemplos em [prompts-testados.md](prompts-testados.md).
