# Rag_based_LLM

---

# 🧠 Legal Search with Explanations

A powerful Streamlit web application for semantic search over legal documents with AI-generated explanations. This project integrates cutting-edge embedding models, ANN search, neural reranking, and LLM-based explanation generation to help users efficiently find and understand relevant legal provisions.

---

## 🚀 Overview

- **Ollama Embeddings**: Uses `nomic-embed-text` to convert legal text into semantic vectors.
- **ChromaDB ANN Search**: Fast approximate nearest neighbor retrieval using HNSW indexing.
- **Cross-Encoder Reranking**: Refines initial results with `ms-marco-MiniLM-L-6-v2`.
- **LLaMA 2 LLM Explanation Generation**: Generates concise, human-readable explanations using `llama2:latest`.
- **Streamlit UI**: Clean interface with query input, top-k result configuration, rerank scoring, and explanation display.

---

## ✨ Features

- **Efficient Embedding & Index Caching**: Avoids recomputation using `@st.cache_resource`.
- **Batch Processing with Progress Bar**: Real-time feedback during embedding and indexing.
- **Configurable Top-K Results**: Slider to adjust number of displayed and reranked results.

---

## 💼 Use Cases

1. Legal researchers and practitioners seeking semantically relevant excerpts from legal text.
2. Developers exploring semantic search, neural reranking, and LLM explanation generation.
3. Organizations wanting explainable AI-powered legal search to enhance workflows.

---

## ⚙️ How It Works

1. **Data Loading**: Reads legal documents from `bns.csv` (columns: description, act, section).
2. **Embedding Generation**: Converts documents into vector representations using Ollama.
3. **Indexing**: Builds ANN index in ChromaDB with HNSW optimization.
4. **Query Processing**: Retrieves candidates based on vector similarity.
5. **Reranking**: Applies Cross-Encoder model for refined relevance scoring.
6. **Explanation Generation**: Generates relevance explanations using LLaMA 2.
7. **Display**: Shows metadata, similarity scores, reranked results, and explanations.

---

## 📦 Requirements

- Python 3.8 or higher

---

## 📁 Repository Info

- **Project Name**: `RAG_based_LLM`
- **Author**: 
- **Language**: Python
