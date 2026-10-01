# PDF-Document-Q-A-Engine-RAG-Application-
DF Document Q&amp;A Engine (RAG Application) using Python, LangChain, ChromaDB, Gemini API, HuggingFace

**Enterprise PDF Q&A Engine (RAG Pipeline)**

An enterprise-grade Retrieval-Augmented Generation (RAG) pipeline designed to ingest unstructured PDF documents, perform semantic text chunking, build a vector database index, and deliver context-grounded, zero-hallucination answers with accurate source citations using LangChain, ChromaDB, HuggingFace Embeddings, and Google Gemini API.

---

## Features

- PDF Ingestion & Processing: Efficient parsing of complex PDF documents via PyPDFLoader and RecursiveCharacterTextSplitter.
- Local Embedding Generation: Utilizes HuggingFace's open-source all-MiniLM-L6-v2 model for high-performance vector embeddings without third-party embedding API costs.
- Vector Indexing: Persists and retrieves high-dimensional vector embeddings using ChromaDB.
- Context-Grounded LLM Inference: Integrates Google Gemini API (ChatGoogleGenerativeAI) with strict prompt constraints to eliminate hallucinations.
- Source Attribution: Provides precise page numbers and context snippets for every generated answer.
- Interactive CLI Interface: Command-line interactive Q&A session with built-in query handling and rate limiting.

---

## Architecture Overview

[ PDF Document ]
       |
       v
[ PyPDFLoader ] ---> [ Recursive Text Splitter ]
                                |
                                v
                   [ HuggingFace Embeddings ]
                                |
                                v
                     [ Chroma Vector DB ]
                                |
                                v
[ User Query ] ---> [ Vector Similarity Search ]
                                |
                                v
                  [ Context + Query Prompt ]
                                |
                                v
                     [ Google Gemini API ]
                                |
                                v
              [ Answer + Page Citations Output ]

---

## Tech Stack

- Programming Language: Python 3.10+
- Framework: LangChain (langchain_community, langchain_core)
- Vector Store: ChromaDB (langchain_community.vectorstores.Chroma)
- Embeddings: HuggingFace sentence-transformers/all-MiniLM-L6-v2
- Large Language Model: Google Gemini API (langchain_google_genai)
- Environment: Google Colab / Local Execution

---

## Project Structure

.
|-- main.py                     # Main RAG Service script & execution loop
|-- requirements.txt            # Python dependencies
|-- .gitignore                  # Git ignore rules for DB and API keys
|-- README.md                   # Project documentation

---

## Getting Started

### 1. Prerequisites

Make sure you have:
- Python 3.10 or higher installed.
- A Google Gemini API Key (Get one from Google AI Studio).

---

### 2. Installation

Clone this repository and install the dependencies:

```bash
# Clone the repository
git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git)
cd YOUR_REPOSITORY_NAME

# Create a virtual environment
python -m venv venv
source venv/bin/activate    # On Windows use: venv\Scripts\activate

# Install required packages
pip install -r requirements.txt
