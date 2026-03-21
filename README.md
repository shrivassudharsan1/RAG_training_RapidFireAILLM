# RAG Training with RapidFireAI on FiQA Dataset

![Python](https://img.shields.io/badge/python-3.10-blue) ![Colab](https://img.shields.io/badge/Open_in-Colab-orange)

## Overview

This project implements a **Retrieval-Augmented Generation (RAG)** system on the FiQA (Financial Question Answering) dataset using **RapidFireAI**. The goal is to evaluate multiple retrieval pipeline configurations and optimize answer relevance using metrics like **MRR, Precision, Recall, F1, and NDCG@5**.

---

## Dataset

- **Subset size:** 1,721 documents sampled from the full FiQA dataset (~57k documents).  
- **Evaluation queries:** 664 (limited by compute resources).  
- **Metrics:** MRR, Precision@K, Recall, F1, NDCG@5.  

---

## Model & Pipeline

- **Language model:** `Qwen2.5-0.5B-Instruct` (fast, Colab-compatible).  
- **Retriever:** Sparse & dense embeddings.  
- **Key parameters:**  
  - `chunk_size`: 150–200  
  - `overlap`: 20–60  
  - `top_k`: 1–5  
  - `top_n`: 1–2  

**Pipeline Diagram:**
