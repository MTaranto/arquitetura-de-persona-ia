
# 🧩 Injeção de Contexto Cronológico e Leitura Sequencial

## 🛑 O Problema (A Dor do Negócio)
Modelos de Linguagem processam *tokens* (fragmentos de palavras) mapeando probabilidades, o que frequentemente causa um efeito conhecido como "fragmentação de contexto" ou amnésia. Em interações longas ou instruções complexas de negócios, a IA tende a misturar regras antigas com novas, ignorando a ordem dos fatores e quebrando a lógica de processos que exigem passos sequenciais rigorosos.

## 💡 A Solução Arquitetural
Para garantir a integridade da linha do tempo e a coesão das regras, apliquei o framework de **Leitura Sequencial**. Em vez de despejar um bloco massivo de texto no *System Prompt*, as diretrizes são particionadas em blocos lógicos isolados e acompanhadas de uma trava de execução. A IA é instruída de forma imperativa a processar a informação na exata ordem em que é apresentada, simulando um fluxo de *pipeline* de dados.

## 🛠️ O Código de Instrução (Snippet)

Abaixo, o modelo de instrução utilizado para forçar a coerência narrativa e procedimental da IA antes de carregar o banco de dados da persona:

```text
[DIRETRIZ DE COESÃO - LEITURA SEQUENCIAL OBRIGATÓRIA]
As informações de contexto a seguir estão divididas em partes lógicas isoladas. É imperativo e obrigatório que você processe a leitura estritamente na ordem apresentada.

Objetivo da Trava:
1. Manter a integridade cronológica das instruções de negócio e de persona.
2. Evitar a sobreposição de regras conflitantes.
3. Garantir que a evolução do contexto seja absorvida de forma linear (Causa e Efeito).

A partir deste ponto, absorva o tom, a lógica e o histórico apenas seguindo o fluxo direcional imposto.
