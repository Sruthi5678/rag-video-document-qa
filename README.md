# 🎥 RAG-Based Video & Document Q&A System

### Ask Questions. Get Context-Aware Answers. Learn Faster.

A Retrieval-Augmented Generation (RAG) application that allows users to ask questions about YouTube videos, PDF documents, and webpages. It retrieves relevant information from the provided content and generates concise, context-grounded answers using a local Large Language Model (LLM).

---

## ✨ Features

* 🎥 **YouTube Video Q&A** — Extract transcripts from supported YouTube videos and ask questions about their content.
* 📄 **PDF Document Q&A** — Extract and analyze text from PDF documents.
* 🌐 **Webpage Q&A** — Retrieve readable text from webpages and answer questions about their content.
* 🔍 **Semantic Search** — Find relevant information using vector embeddings and FAISS.
* 🤖 **AI-Powered Answers** — Generate natural-language responses using LangChain and Ollama.
* 🎯 **Context-Grounded Responses** — Instruct the model to answer using retrieved content and avoid unsupported claims.
* 📚 **Source Information** — Display retrieved text sections and their source locations.
* ⚡ **Local Execution** — Run the language model locally without requiring paid OpenAI API credits.

---

## 🛠️ Tech Stack

| Component            | Technology                                 |
| -------------------- | ------------------------------------------ |
| Programming Language | Python                                     |
| LLM Framework        | LangChain                                  |
| Language Model       | Ollama — Llama 3.2 (1B)                    |
| Embedding Model      | Sentence Transformers — `all-MiniLM-L6-v2` |
| Vector Database      | FAISS                                      |
| PDF Processing       | PyPDF                                      |
| YouTube Transcripts  | YouTube Transcript API                     |
| Web Scraping         | BeautifulSoup, Requests                    |
| Text Splitting       | RecursiveCharacterTextSplitter             |
| Notebook Environment | Jupyter Notebook                           |

---

## 🧠 How It Works

The system follows a Retrieval-Augmented Generation workflow:

**1. Input Source**
The user provides a YouTube URL, PDF file path, or webpage URL.

**2. Content Extraction**
The application extracts readable text from the selected source.

**3. Text Chunking**
The extracted text is divided into smaller, overlapping chunks for efficient retrieval.

**4. Embedding Generation**
The Sentence Transformers model converts the text chunks into numerical vectors.

**5. Vector Indexing**
FAISS stores the vectors and enables similarity-based retrieval.

**6. Relevant Context Retrieval**
When the user asks a question, the system retrieves the most relevant chunks.

**7. Answer Generation**
LangChain passes the question and retrieved context to the local LLM through Ollama.

**8. Source Display**
The system displays the generated answer alongside the retrieved source information.

### Architecture

```text
YouTube URL / PDF / Webpage
            |
            v
     Content Extraction
            |
            v
       Text Chunking
            |
            v
   Sentence Transformers
        Embeddings
            |
            v
      FAISS Vector Store
            |
      User's Question
            |
            v
   Similarity-Based Retrieval
            |
            v
     Retrieved Context
            |
            v
       LangChain LCEL
            |
            v
      Ollama LLM
            |
            v
    Context-Grounded Answer
            |
            v
      Display Answer
      + Source Sections
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

* Python 3.10 or a compatible version
* Jupyter Notebook
* Ollama

### 1. Clone the Repository

```bash
git clone https://github.com/Sruthi5678/rag-video-document-qa.git
cd rag-video-document-qa
```

### 2. Install Python Dependencies

Run the following command in your terminal or notebook:

```bash
pip install langchain langchain-core langchain-community langchain-text-splitters langchain-huggingface langchain-ollama sentence-transformers faiss-cpu pypdf youtube-transcript-api beautifulsoup4 requests
```

### 3. Install and Run Ollama

Install Ollama from its official website:

https://ollama.com/

Download the required model:

```bash
ollama pull llama3.2:1b
```

Ensure Ollama is running before executing the notebook.

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `rag-based-qa.ipynb` and execute the cells in order.

The first run may take additional time because the embedding model needs to be downloaded.

---

## 💡 Example Questions

Once the content has been loaded, try asking:

* What are the main concepts discussed in this video?
* Summarize the key information in this document.
* What technologies are mentioned in this content?
* Explain the main topic in simple terms.
* What information does the provided source contain about a specific subject?

The answers depend on the information available in the selected source.

---

## 📁 Project Structure

```text
rag-video-document-qa/
│
├── rag-based-qa.ipynb   # Main Jupyter Notebook
└── README.md            # Project documentation
```

Additional files, such as `requirements.txt` and `.gitignore`, can be added as the project evolves.

---

## ⚠️ Limitations

* YouTube transcript extraction depends on transcript availability and access permissions.
* Some websites restrict automated content extraction.
* Scanned PDFs may require Optical Character Recognition (OCR).
* The quality of answers depends on the retrieved context and language model.
* Smaller local models may occasionally generate inaccurate or incomplete answers.
* Source retrieval helps ground answers but does not guarantee that every response is correct.

---

## 🔮 Future Enhancements

* Develop a responsive React frontend.
* Build REST APIs using FastAPI.
* Add JWT-based authentication.
* Support chat history and document management.
* Improve retrieval quality and answer evaluation.
* Add more precise source citations.
* Support additional document formats.
* Deploy a user-friendly application.

---

## 🎯 Project Objective

The goal of this project is to demonstrate how Retrieval-Augmented Generation combines semantic search and language models to make information retrieval from long-form content more efficient and interactive.

---

## 👩‍💻 Author

**Sruthi Vaddadi**

B.Tech Student | Aspiring Software Developer | AI/ML Enthusiast

GitHub: [@Sruthi5678](https://github.com/Sruthi5678)

---

⭐ If you find this project interesting, consider giving the repository a star!
