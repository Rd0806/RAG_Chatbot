# TechNova RAG Chatbot 🤖

A Retrieval-Augmented Generation (RAG) conversational agent built to securely and accurately answer queries based on a corporate IT policy handbook. 

This project demonstrates the end-to-end implementation of a RAG pipeline from scratch, including document ingestion, semantic chunking, custom vector storage, and Large Language Model (LLM) text generation. 

## 🏗️ System Architecture

1. **Document Processing:** Extracts raw text from PDF files (`pypdf`), cleans it, and splits it into overlapping semantic chunks to preserve context boundaries.
2. **Embedding Generation:** Transforms text chunks into high-dimensional vector representations using `SentenceTransformers`.
3. **Custom Vector Database:** A lightweight, custom-built vector store using `NumPy` that implements Euclidean distance calculations to perform rapid similarity searches.
4. **Generation:** Retrieves the top-k most relevant document chunks and injects them as context into a Hugging Face text-generation pipeline to ground the LLM's answers in factual, domain-specific data.

## 🛠️ Tech Stack

* **Language Model:** Hugging Face `pipeline` (configurable to support models like `SmolLM2-135M-Instruct` or `google/flan-t5-base`)
* **Embeddings:** `all-MiniLM-L12-v2` via `SentenceTransformers`
* **Vector Store:** Custom `NumPy` implementation 
* **Data Processing:** `pypdf`, `tqdm`

## 🚀 Getting Started

### Prerequisites
* Python 3.8+
* Jupyter Notebook or Google Colab (A T4 GPU is recommended for faster LLM inference).

### Installation
Clone the repository and install the required dependencies:

```bash
git clone [https://github.com/YOUR_USERNAME/technova-rag-chatbot.git](https://github.com/YOUR_USERNAME/technova-rag-chatbot.git)
cd technova-rag-chatbot
pip install sentence-transformers pypdf transformers huggingface_hub torch tqdm
