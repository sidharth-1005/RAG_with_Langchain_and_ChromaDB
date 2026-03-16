RAG with LangChain and ChromaDB
A retrieval-augmented generation (RAG) system that lets you query documents using natural language. Built with LangChain, ChromaDB, and a locally running LLM — no paid APIs required.
How it works

Documents are loaded and split into chunks
Each chunk is embedded using HuggingFace's all-MiniLM-L6-v2 model
Embeddings are stored in a ChromaDB vector database
At query time, the most relevant chunks are retrieved and passed to a local LLM via Ollama
The LLM generates an answer based only on the retrieved context

Stack

LangChain — document loading, text splitting, prompt management
ChromaDB — vector storage and similarity search
HuggingFace Embeddings — local, free embeddings (all-MiniLM-L6-v2)
Ollama — local LLM inference (Llama 3.2)

Setup

Install dependencies:

pip install -r requirements.txt

Install Ollama from ollama.com and pull the model:

ollama pull llama3.2

Build the vector database:

python create_database.py

Query the database:

python query_data.py "How does Alice meet the Mad Hatter?"
