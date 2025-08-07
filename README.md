# RAG-based-LLM  

## 🔍 Legal Search with Explanations
A powerful Streamlit web application for semantic search over legal documents with AI-generated explanations. This app combines state-of-the-art embedding models, approximate nearest neighbor (ANN) search, neural reranking, and LLM-based explanations to help users efficiently find and understand relevant legal provisions.

##🚀 Overview
This project implements a semantic legal document search system featuring:

* Ollama Embeddings: Uses Ollama's "nomic-embed-text" model to convert legal text into semantic vectors.
* ChromaDB ANN Search: Employs ChromaDB for fast approximate nearest neighbor retrieval with optimized HNSW indexing.
* Cross-Encoder Reranking: Applies a dense cross-encoder (ms-marco-MiniLM-L-6-v2) for refining initial results.
* LLaMA 2 LLM Explanation Generation: Calls Ollama's LLM (llama2:latest) to generate concise, human-readable explanations for each search result on demand.
* Streamlit UI: Interactive, clean interface with query input, configurable top-k results, rerank scoring, and explanation display.
