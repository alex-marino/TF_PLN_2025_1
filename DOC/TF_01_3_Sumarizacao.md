# Tema 2 — Extração de Entidades Nomeadas com LLMs

## 🎯 Objetivo Específico

Treinar e avaliar modelos baseados em transformers (como BERTimbau, XLM-RoBERTa ou DistilBERT) para realizar a **extração de entidades nomeadas** em textos jornalísticos ou documentos públicos em português. A tarefa consiste em identificar entidades como **pessoas, locais, organizações, eventos, entre outras**.

---

## 📚 Sugestões de Datasets Públicos em Português

### 1. **HAREM (Linguateca)**
- **Descrição**: Conjunto de textos anotados com entidades nomeadas para a língua portuguesa (europeu e brasileiro).
- **Fonte**: [https://www.linguateca.pt/HAREM/](https://www.linguateca.pt/HAREM/)
- **Formato**: XML com anotações padronizadas para tarefas NER.

### 2. **PortugueseNER (Peixeleao)**
- **Descrição**: Corpus com frases e anotações BIO para pessoas, locais e organizações.
- **Fonte**: [GitHub - peixeleao/PortugueseNER](https://github.com/peixeleao/PortugueseNER)
- **Formato**: `.tsv` com estrutura já pronta para treinamento com Hugging Face.

### 3. **BrWaC + Anotações Fracas**
- **Descrição**: Corpus extenso da web brasileira. Pode ser usado com anotações fracas (distant supervision).
- **Fonte**: [Corpus BrWaC](https://www.linguateca.pt/Repositorio/BrWaC/)
- **Observação**: Requer heurísticas ou uso de modelos pré-treinados para gerar pseudo-rótulos.

---

## 📦 Requisitos Objetivos para o Projeto

1. **Pré-processamento dos textos** (remoção de ruído, formatação BIO ou similar)
2. Uso de um **modelo transformer para token classification**
3. Divisão do dataset em **treino, validação e teste**
4. Treinamento com `Trainer` da Hugging Face ou outro framework compatível
5. Avaliação com métricas específicas de NER (F1, precision, recall por entidade)
6. Visualização das entidades reconhecidas em trechos de texto
7. Relatório com **análise dos erros, limitações do modelo e sugestões de melhoria**
8. Organização do código em **notebook limpo, com comentários e reprodutibilidade**
9. Explicitação do **mapa de entidades anotadas** e categorias suportadas

---

## 📊 Métricas de Avaliação

### 1. **Precision, Recall e F1-score por entidade**
- Avaliação padrão em tarefas de NER.
- Exemplo: F1 para "LOC", "PER", "ORG" separadamente.

### 2. **Média ponderada (macro e micro)**
- Úteis para avaliar equilíbrio e impacto de classes desbalanceadas.

### 3. **Visualização de exemplo**
- Textos com entidades destacadas, para validação qualitativa.

---

## 📝 Sugestão de Roteiro Técnico

1. **Importação e exploração inicial do dataset**
2. **Conversão para formato BIO (se necessário)**
3. **Tokenização com modelo pré-treinado**
4. **Definição de etiquetas e mapeamento de rótulos**
5. **Fine-tuning com `Trainer` do Hugging Face**
6. **Avaliação automática com `seqeval` ou similar**
7. **Visualização de entidades extraídas**
8. **Discussão dos resultados e limitações**

---

## 🧠 Modelos Recomendados

- `pucpr/bert-base-portuguese-cased-ner` (já treinado para NER)
- `pierreguillou/ner-bert-base-cased-pt`
- `neuralmind/bert-base-portuguese-cased` (com fine-tuning)
- `xlm-roberta-base` (multilíngue com bom desempenho em português)

---
