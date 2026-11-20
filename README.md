# 💬 BRIHA · Hybrid AI Chatbot

![Part of BRIHA](https://img.shields.io/badge/Part_of-BRIHA-8B5CF6?style=for-the-badge&labelColor=0B1024)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![llama.cpp](https://img.shields.io/badge/llama.cpp-000000?style=flat-square) ![Sentence Transformers](https://img.shields.io/badge/Sentence_Transformers-FF6F00?style=flat-square) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

> ⚡ **Part of [BRIHA](https://github.com/asad110abbas)** · Briha Research, built by Syed Asad Abbas.

A conversational agent that combines **semantic search over a knowledge base** with a **locally-run LLM**, so
answers stay grounded in your own data while still sounding natural, all without paid APIs.

## How it works
```mermaid
flowchart LR
    Q[User question] --> E[Sentence-Transformer embedding]
    E --> S{Cosine similarity vs. knowledge base}
    S -- strong match --> R[Rule / stored answer]
    S -- weak match --> L[Local LLM via llama.cpp]
    R --> A[Answer]
    L --> A
```

## Highlights
- **Hybrid intelligence:** predictable rule-based answers for known intents, plus an LLM for open questions
- **Semantic retrieval:** knowledge base embedded with Sentence-Transformers and matched with cosine similarity (scikit-learn)
- **Runs locally:** GGUF model served through `llama-cpp-python`, so no API keys and no per-token cost
- **Fast startup:** embeddings cached with `pickle`

## Notebook walkthrough
1. **Move model into the Colab workspace**
2. **Embed the knowledge base** (pandas → Sentence-Transformers)
3. **Create the model** (llama.cpp)
4. **Answer pipeline** with similarity threshold and fallback

## Run
Open `AI Hybrid ChatBot.ipynb` in Jupyter or Google Colab and run the cells top to bottom.
```bash
pip install llama-cpp-python sentence-transformers scikit-learn pandas
```
