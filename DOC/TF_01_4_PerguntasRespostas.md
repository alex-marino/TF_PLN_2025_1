# Tema 4 — Sistema de Perguntas e Respostas (QA)

## 🎯 Objetivo Específico

Treinar e/ou aplicar modelos baseados em transformers para construir um **sistema de perguntas e respostas** (Question Answering, QA) capaz de localizar ou gerar respostas com base em um **corpus específico de texto**. A tarefa pode assumir duas formas principais:
- **Extractiva**: a resposta é um trecho exato do texto fornecido.
- **Abstrativa**: a resposta é gerada com base no entendimento do texto, podendo ter reescrita.

---

## 📚 Sugestões de Datasets Públicos em Português

### 1. **SQuAD traduzido (portuguesequad)**
- **Descrição**: Versão traduzida do SQuAD 1.1 com perguntas e trechos contextuais em português.
- **Fonte**: [https://github.com/portuguese-nlp/portuguese-squad](https://github.com/portuguese-nlp/portuguese-squad)
- **Formato**: JSON compatível com HuggingFace.

### 2. **Piaf (pt-br subset)**
- **Descrição**: Conjunto de perguntas sobre textos retirados de Wikipedia e artigos, disponível em múltiplas línguas.
- **Fonte**: [Hugging Face Datasets - Piaf](https://huggingface.co/datasets/etalab-ia/piaf)

### 3. **Corpus personalizado**
- **Descrição**: Pode-se criar um corpus com textos públicos (leis, documentos institucionais, etc.) e manualmente anotar pares de perguntas e respostas.

---

## 📦 Requisitos Objetivos para o Projeto

1. Escolher um corpus ou dataset com **contexto e perguntas/respostas anotadas**
2. Implementar um modelo de QA extractivo ou abstrativo
3. Pré-processar os textos (tokenização, truncamento, etc.)
4. Realizar o treinamento (opcional) com `Trainer` da Hugging Face
5. Implementar um sistema interativo (ex.: usuário faz pergunta → resposta gerada)
6. Avaliar a performance com métricas padrão de QA
7. Relatório com análise quantitativa e exemplos qualitativos de perguntas e respostas

---

## 📊 Métricas de Avaliação

### 1. **Exact Match (EM)**
- Percentual de respostas exatamente iguais à referência.

### 2. **F1-score (overlap de tokens)**
- Mede sobreposição parcial entre resposta gerada e esperada (mais tolerante que EM).

### 3. **Human Evaluation (opcional)**
- Avaliação qualitativa da relevância e precisão da resposta.

---

## 📝 Sugestão de Roteiro Técnico

1. **Carregar e explorar o dataset (ex.: portuguesequad)**
2. **Tokenizar usando modelo de QA (ex.: BERT, RoBERTa, T5)**
3. **Pré-processar com mapeamento de contextos e spans de resposta**
4. **Aplicar fine-tuning com `Trainer` ou `pipeline` de QA**
5. **Avaliar no conjunto de teste com `exact_match` e `f1`**
6. **Montar interface de exemplo para testar perguntas do usuário**
7. **Apresentar exemplos de sucesso e falha**

---

## 🧠 Modelos Recomendados

- `mrm8488/bert-base-portuguese-cased-finetuned-squad-v1` (QA em português)
- `neuralmind/bert-base-portuguese-cased` (com fine-tuning)
- `t5-base` ou `unicamp-dl/ptt5-base-portuguese-vocab` (para QA generativo)
- `deepset/roberta-base-squad2` (boa base para adaptação)

---

