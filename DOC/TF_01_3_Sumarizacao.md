# Tema 3 — Sumarização de Texto com LLMs

## 🎯 Objetivo Específico

Treinar e/ou aplicar modelos baseados em transformers para realizar **sumarização automática** de textos longos ou curtos em português, como notícias, artigos acadêmicos ou textos de redes sociais. A tarefa consiste em **gerar um resumo coerente e informativo**, preservando os pontos principais do conteúdo original.

---

## 📚 Sugestões de Datasets Públicos em Português

### 1. **CSTNews**
- **Descrição**: Corpus de textos jornalísticos em português, com resumos humanos anotados.
- **Fonte**: [https://github.com/linhd-postags/cstnews-corpus](https://github.com/linhd-postags/cstnews-corpus)
- **Tamanho**: Pequeno (~140 documentos), mas ideal para fine-tuning controlado.

### 2. **PUD_BR + Wikipedia Headlines**
- **Descrição**: Pode-se usar o cabeçalho de notícias como resumo e o corpo como entrada.
- **Observação**: Requer pré-processamento heurístico.

### 3. **CNN/Brazilian News Dataset (Extração Customizada)**
- **Descrição**: Pode ser criado com scraping de portais como G1, UOL, ou Globo, com título como resumo e corpo como conteúdo.
- **Legalidade**: Apenas para uso educacional e experimental.

---

## 📦 Requisitos Objetivos para o Projeto

1. Escolher ou criar um dataset com **pares (texto original, resumo)**
2. Pré-processamento (remoção de HTML, truncamento de entrada se necessário)
3. Aplicar modelo pré-treinado com ou sem fine-tuning
4. Avaliar com métricas automáticas de sumarização
5. Comparar o desempenho entre abordagens extractivas e abstrativas (se possível)
6. Organizar o código em **notebook reprodutível**
7. Relatório final com análise qualitativa e quantitativa dos resumos gerados

---

## 📊 Métricas de Avaliação

### 1. **ROUGE (Recall-Oriented Understudy for Gisting Evaluation)**
- **ROUGE-1**: sobre uni-gramas
- **ROUGE-2**: sobre bi-gramas
- **ROUGE-L**: sobre subsequência mais longa comum
- Quanto mais alto, melhor.

### 2. **BLEU (opcional)**
- Tradicionalmente usada em tradução, pode ser aplicada como comparação n-gram entre resumo gerado e referência.

### 3. **Avaliação Qualitativa (humana)**
- Coerência, concisão e fidelidade ao texto original.

---

## 📝 Sugestão de Roteiro Técnico

1. **Importar e analisar o dataset de sumarização**
2. **Tokenizar com modelo compatível (T5, BART ou mT5)**
3. **Ajustar truncamento e padding (max_input_length, max_output_length)**
4. **Aplicar fine-tuning supervisionado** com `Trainer`
5. **Gerar resumos no conjunto de teste**
6. **Avaliar com `rouge_score` e/ou `evaluate` da Hugging Face**
7. **Mostrar exemplos comparando entrada, referência e saída gerada**

---

## 🧠 Modelos Recomendados

- `unicamp-dl/ptt5-base-portuguese-vocab` (T5 adaptado para português)
- `csebuetnlp/mT5_multilingual_XLSum` (mT5 treinado para sumarização multilíngue)
- `google/mt5-small` (pré-treinado multilíngue)

---
