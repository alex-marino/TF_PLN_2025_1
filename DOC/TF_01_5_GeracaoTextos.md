# Tema 5 — Geração de Texto com LLMs

## 🎯 Objetivo Específico

Treinar e/ou aplicar modelos de linguagem de grande escala (LLMs) para realizar **geração automática de texto** em português com base em instruções ou dados estruturados. A tarefa pode envolver:
- Geração de **descrições de produtos**
- Criação de **posts para redes sociais**
- Elaboração de **resumos livres** a partir de tópicos ou listas

A saída deve ser **coerente, relevante e linguística e semanticamente adequada**.

---

## 📚 Sugestões de Datasets Públicos ou Construção Própria

### 1. **BrWac + Wikipedia Topics**
- **Descrição**: Corpus extenso da web brasileira; pode-se extrair parágrafos e associar com títulos como prompts.
- **Fonte**: [https://www.linguateca.pt/Repositorio/BrWaC/](https://www.linguateca.pt/Repositorio/BrWaC/)

### 2. **Amazon Reviews (Descrição + Título)**
- **Descrição**: Criar prompts com base no título ou palavras-chave do produto e usar a descrição como target.

### 3. **Dataset próprio estruturado**
- **Descrição**: Criar planilha ou JSON com campos como `tópico` → `texto desejado`.
- **Exemplo**:  
  - Entrada: `"tópico": "cadeira gamer"`  
  - Saída: `"descrição": "Cadeira ergonômica com apoio lombar e design esportivo."`

---

## 📦 Requisitos Objetivos para o Projeto

1. Coletar ou montar dataset com **pares entrada → texto-alvo**
2. Aplicar tokenização e ajuste de sequência para **modelos de geração seq2seq**
3. Treinar modelo com `Trainer` ou usar `pipeline` para geração direta
4. Avaliar resultados com métricas automáticas e análise qualitativa
5. Testar interatividade com novos prompts
6. Entregar notebook, relatório e amostras de texto gerado

---

## 📊 Métricas de Avaliação

### 1. **BLEU**
- Mede a similaridade entre o texto gerado e a referência, baseado em n-grams.

### 2. **ROUGE**
- Avalia a sobreposição de conteúdo relevante (principalmente em resumos).

### 3. **Perplexidade (PPL)**
- Avalia a fluidez do modelo (quanto menor, melhor).

### 4. **Avaliação qualitativa**
- Clareza, criatividade, adequação ao prompt.

---

## 📝 Sugestão de Roteiro Técnico

1. **Carregar dataset com tópicos ou prompts**
2. **Tokenizar com modelo de geração (T5, GPT-2, mT5, etc.)**
3. **Ajustar `input_text` e `target_text`**
4. **Treinar com `AutoModelForSeq2SeqLM` ou `CausalLM`**
5. **Gerar novos textos a partir de instruções customizadas**
6. **Avaliar com métricas BLEU, ROUGE e perplexidade**
7. **Analisar exemplos bons e ruins de saídas geradas**

---

## 🧠 Modelos Recomendados

- `unicamp-dl/ptt5-base-portuguese-vocab` (T5 para português)
- `pierreguillou/t5-base-en-pt-small-train` (modelo traduzido/adaptado)
- `gpt2` ou `neuralmind/bert-base-portuguese-cased` (com ajustes)
- `tiiuae/falcon-rw-1b` (para tarefas de geração zero-shot)

---

