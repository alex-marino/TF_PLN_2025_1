# Tema 1 — Classificação de Sentimentos com Transformers

## 🎯 Objetivo Específico

Treinar e avaliar modelos baseados em transformers (como BERTimbau, mBERT ou DistilBERT) para realizar a **classificação de sentimentos** em textos curtos em português (ex.: positivos, negativos, neutros).

---

## 📚 Sugestões de Datasets Públicos em Português

### 1. **SentiCorpus-PT**  
- **Descrição**: Corpus anotado com sentimentos (positivo, negativo, neutro) baseado em resenhas de produtos e notícias.  
- **Fonte**: [GitHub - NILC/SentiCorpus-PT](https://github.com/NILCIC/SentiCorpus-PT)  
- **Tamanho**: ~7.000 exemplos

### 2. **OpLexicon**  
- **Descrição**: Lexicon de polaridade, mas pode ser usado como base para labeling em frases de tweets ou reviews.  
- **Fonte**: [GitHub - NILC/OpLexicon](https://github.com/NILCIC/OpLexicon)

### 3. **B2W Reviews Dataset**  
- **Descrição**: Mais de 100 mil reviews de produtos da Americanas.com com classificação de 1 a 5 estrelas.  
- **Fonte**: [Kaggle - B2W Reviews](https://www.kaggle.com/datasets/b2wreviews/b2w-reviews-dataset)  
- **Transformação**: Estrelas 1–2 → Negativo, 3 → Neutro, 4–5 → Positivo

### 4. **Tweets Sentiment Corpus PT-BR**  
- **Descrição**: Tweets em português com sentimentos anotados.  
- **Fonte**: [TweepFake Dataset + Sentiment Extensions](https://www.kaggle.com/datasets/marlesson/twitter-sentiment-analysis-dataset)  

---

## 📦 Requisitos Objetivos para o Projeto

1. **Pré-processamento adequado** do texto (remoção de ruído, tokenização, etc.)
2. Utilização de **modelo transformer pré-treinado** com ajuste fino (fine-tuning)
3. Divisão do dataset em **conjunto de treino, validação e teste**
4. Implementação de **métrica de avaliação apropriada** para classificação balanceada/desbalanceada
5. Visualização da performance do modelo (matriz de confusão, curva ROC, etc.)
6. Justificativa da escolha do modelo e dos hiperparâmetros
7. Implementação em **notebook organizado e comentado**
8. Relatório claro com **análise dos erros e sugestões de melhoria**
9. O modelo final deve ser **reprodutível** (definir semente aleatória, ambiente)

---

## 📊 Métricas de Avaliação

### 1. **Acurácia**
- Percentual de previsões corretas.
- Útil se o dataset for balanceado.

### 2. **Precisão, Recall e F1-score (macro e por classe)**
- Mais informativas quando há **classes desbalanceadas**.
- `F1-macro` deve ser a principal métrica.

### 3. **Matriz de Confusão**
- Ajuda a entender os erros do modelo por categoria de sentimento.

### 4. **Curva ROC e AUC (opcional)**
- Se for uma tarefa binária (positivo vs. negativo).

---

## 📝 Sugestão de Roteiro Técnico

1. **Importação e análise exploratória do dataset**
2. **Mapeamento das classes (sentimentos)**
3. **Tokenização com tokenizer do modelo escolhido (ex.: BERTimbau)**
4. **Fine-tuning com `Trainer` do HuggingFace ou `PyTorch Lightning`**
5. **Avaliação no conjunto de teste**
6. **Visualização das métricas**
7. **Conclusão e discussão sobre possíveis melhorias**

---

## 🧠 Modelos Recomendados

- `neuralmind/bert-base-portuguese-cased` (BERTimbau)
- `xlm-roberta-base` (multilíngue)
- `distilbert-base-multilingual-cased` (leve e rápido)

---

