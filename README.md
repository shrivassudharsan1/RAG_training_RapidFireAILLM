# RAG Training with RapidFireAI on FiQA Dataset

**Notebook:** [Open in Colab](https://colab.research.google.com/drive/1dZqV2osju1Q2xMQiQszst7eECwqrou36?usp=sharing)

This project builds a **Retrieval-Augmented Generation (RAG)** system using the FiQA (Financial Question Answering) dataset and evaluates retrieval quality across multiple pipeline configurations with RapidFireAI.

---

## Dataset

- Subset of **1,721 documents** sampled from FiQA (57k total).  
- **664 evaluation queries** used due to compute limits.  
- Metrics focus on: **MRR, Precision, Recall, F1, NDCG@5**.

---

## Model

- **Qwen2.5-0.5B-Instruct**  
  Chosen for speed and Colab compatibility.

---

## Experiment

The following parameters were varied:

- **Chunk size:** 150–200  
- **Overlap:** 20–60  
- **top_k:** 1–5  
- **top_n:** 1–2  

### Best Configuration (Variant A)

- Chunk size: 150  
- Overlap: 20  
- top_k: 2  
- top_n: 1  
- **MRR:** 0.655  

*Observation:* Small chunks performed better than large overlapping ones.

---

## Results Summary

| Chunk | Overlap | top_k | top_n | MRR  |
|-------|---------|-------|-------|------|
| 150   | 20      | 2     | 1     | 0.655|
| 150   | 20      | 2     | 2     | 0.655|
| 200   | 60      | 2     | 1     | 0.645|
| 200   | 60      | 2     | 2     | 0.645|

<img width="642" height="483" alt="image" src="https://github.com/user-attachments/assets/147a53d0-41c8-473e-bdc6-6d80eacc2d46" />

---

## Takeaways

- Chunk size had the strongest impact on retrieval performance.  
- Increasing top_n did not improve results on a small dataset.  
- RapidFireAI enabled **fast, parallel evaluation** across many configurations.

---

## Usage

See the linked Colab notebook for full execution steps.

---

## About

Designed and evaluated a retrieval-augmented generation (RAG) pipeline on the FiQA financial QA dataset, benchmarking multiple retrieval strategies (sparse + dense) using **MRR** and **Precision@K** to optimize answer relevance and retrieval quality.

---

## Topics

nlp, information-retrieval, transformers, question-answering, rag, fiqa, retrival-augmented-generation, rapidfireai
