# Rag-based-LLM

---

## 🔍 Legal Search with Explanations

A powerful Streamlit web application for semantic search over legal documents with AI-generated explanations. This app combines state-of-the-art embedding models, approximate nearest neighbor (ANN) search, neural reranking, and LLM-based explanations to help users efficiently find and understand relevant legal provisions.


---

## 🚀 Overview
This project implements a semantic legal document search system featuring:
- **Ollama Embeddings**: Uses Ollama's `"nomic-embed-text"` model to convert legal text into semantic vectors.  
- **ChromaDB ANN Search**: Employs ChromaDB for fast approximate nearest neighbor retrieval with optimized HNSW indexing.  
- **Cross-Encoder Reranking**: Applies a dense cross-encoder (`ms-marco-MiniLM-L-6-v2`) for refining initial results.  
- **LLaMA 2 LLM Explanation Generation**: Calls Ollama's LLM ( `llama2:latest`) to generate concise, human-readable explanations for each search result on demand.  
- **Streamlit UI**: Interactive, clean interface with query input, configurable top-k results, rerank scoring, and explanation display.



---
## ✨ Features

- **Efficient Embedding & Index Caching**: Uses Streamlit's `@st.cache_resource` decorator to avoid repeated embedding computation and index rebuilding across sessions.  
- **Batch Processing with Progress Bar**: Shows real-time progress during initial embedding and indexing.  
- **Configurable Top-K Results**: Adjustable slider to control number of displayed and reranked results.  
- **On-Demand Explanation Generation**: Explanations by LLM are generated only when users request them, ensuring responsiveness.  
- **Streamlined UI with Styling**: Displays cosine distances, rerank scores, legal metadata (`act` and `section`), document excerpts, and AI-generated explanations in a visually appealing manner.

---

## 💼 Use Cases

- Legal researchers and practitioners seeking semantically relevant excerpts from legal text.  
- Developers exploring how to combine semantic search, neural reranking, and LLM explanation generation.  
- Organizations wanting explainable AI-powered legal search to enhance workflows.

---

## ⚙️ How It Works

- **Data Loading**: Reads legal documents from `bns.csv` (with `description`, `act`, and `section` columns).  
- **Embedding Generation**: Uses Ollama’s embedding model to convert documents into vector representations.  
- **Indexing**: Builds an ANN index in ChromaDB optimized with HNSW parameters.  
- **Query Processing**: Retrieves candidate documents based on vector similarity.  
- **Reranking**: Applies a Cross-Encoder model to reorder candidate results by refined relevance score.  
- **Explanation Generation**: On user request, generates a concise relevance explanation per result using Ollama’s LLaMA 2 model.  
- **Display**: Presents results with metadata, similarity scores, reranking, and explanations.

---

## 📦 Requirements


- Python 3.8 or higher  
- Python packages:  
  - `streamlit`  
  - `pandas` 
  - `chromadb`  
  - `sentence-transformers`  
  - `requests`  
  - `numpy`  
- Ollama server running locally or accessible remotely with:  
  - `"nomic-embed-text"` embedding model available  
  - `"llama2:latest"` LLM model available  
- A CSV file (`bns.csv`) containing legal documents with the necessary columns.


---

## 🛠️ Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/chitranshi18/Rag-based-LLM.git
   cd Rag-based-LLM

2. **Install required Python packages:**
   ```bash
   pip install streamlit pandas chromadb sentence-transformers  
      
4. **Ensure Ollama server is running at the configured API URL:**
(http://localhost:11434/api by default) with the required models loaded.)

5. ** Place your bns.csv file in the root directory. The file should contain legal document descriptions and metadata (act, section, description).


---

## 🚀 Running the App

Launch the Streamlit app with:
   ```bash
   streamlit run app.py  

** Enter your legal query in the input area.
** Adjust the "Number of top results" slider.
** Click "Run Semantic Search" to retrieve and rerank relevant legal documents.
** Click "Show Explanation" on any result to generate a concise AI explanation of relevance.


---

## 📝 Project Structure

- `app.py`: Main Streamlit application implementing the full search pipeline.  
- `bns.csv`: Legal documents dataset (user-provided).  
- `logo.jpg`: Optional sidebar logo image.  
- `README.md`: Documentation and usage instructions.


---

## ⚙️ Configuration

Adjustable Parameters (within `app.py`)

- `OLLAMA_EMBED_MODEL`: Ollama embedding model name (default: `"nomic-embed-text"`).  
- `OLLAMA_LLM_MODEL`: Ollama LLM model for explanations (default: `"llama2:latest"`).  
- `OLLAMA_API_URL`: Base URL for Ollama API calls.  
- `CHROMA_COLLECTION_NAME`: ChromaDB collection name.  
- `BATCH_SIZE`: Number of documents processed per batch during indexing.  
- `HNSW parameters`: Settings for efficient ANN index construction and search.  
- `Top-K slider`: User-controlled display and rerank result count.


---

## 🛡️ Error Handling & Reliability

- Cached loading of embedding function and reranker models with Streamlit caching.  
- User-friendly error messages for missing CSV files or Ollama API connectivity issues.  
- Explanation generation with 60-second timeout and error fallback messages.  
- Progress indicators and status text for batch embedding.


---

## 💡 Acknowledgements

This project leverages:

- **Ollama** for embeddings & language models  
- **ChromaDB** for vector similarity search  
- **Sentence Transformers** cross-encoder models for reranking  
- **Streamlit** for creating the web app UI


---

## 📄 License

This project is licensed under the MIT License. See LICENSE for details.


---

## 🤝 Contribution

Contributions, issues, and feature requests are welcome! Feel free to open an issue or submit a pull request.


---

## 🔗 Contact
For questions or support, please contact csrivastava182000@gmail.com.


---

Enjoy exploring and extending your legal search with AI-powered explanations! 🚀



