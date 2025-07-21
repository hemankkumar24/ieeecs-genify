# 🔍 RAG App using LangChain, ChromaDB, and Ollama

This project is a beginner-friendly demo of a **Retrieval-Augmented Generation (RAG)** application. It loads a PDF, converts it into searchable vector form using embeddings, and allows you to ask questions about its content using a locally running language model (Ollama).

---

## 📦 What is RAG?

**RAG (Retrieval-Augmented Generation)** is a technique that improves AI-generated answers by first retrieving relevant context (like from a PDF), then passing that to a language model. This makes answers **more accurate and grounded in real data**.

---

## ⚙️ How it Works

1. **Load a PDF** using `PDFPlumberLoader`.
2. **Split text** into manageable chunks with `CharacterTextSplitter`.
3. **Convert text chunks to embeddings** using a pre-trained HuggingFace model (`all-MiniLM-L6-v2`).
4. **Store vectors** in a local database using `Chroma`.
5. **Query relevant chunks** based on your question.
6. **Pass chunks to Ollama**, which generates an answer using a local LLM (e.g., LLaMA 3 via Ollama).

---

## 🚀 How to Run This

### 1. Clone this repository

```bash
git clone https://github.com/hemankkumar24/ieeecs-genify.git
cd ieeecs-genify
```

### 2. Install Dependencies

Create a virtual environment and install dependencies:

```bash
pip install langchain langchain-community chromadb pdfplumber
pip install sentence-transformers  # required for HuggingFace embeddings
```

### 3. Install Ollama and Model

Download and install [Ollama](https://ollama.com/) for your OS.

Then pull a model:

```bash
ollama pull llama3.2
ollama run llama3.2
```

### 4. Run the Notebook

Open the Jupyter Notebook and follow the steps. Make sure your Ollama server is running.

---

## 🧠 Libraries Used

| Library | Use |
|--------|-----|
| `langchain` | Core RAG pipeline (splitting, prompts, etc.) |
| `langchain_community.vectorstores.Chroma` | Vector store to save/query document chunks |
| `langchain_community.embeddings.HuggingFaceEmbeddings` | Converts text into embeddings |
| `langchain_community.document_loaders.PDFPlumberLoader` | Extracts text from PDFs |
| `langchain_community.chat_models.ChatOllama` | Connects to Ollama’s LLM |
| `chromadb` | Local vector database |
| `sentence-transformers` | Required for HuggingFace embeddings |
| `ollama` | Local LLM backend |

---

## 📂 Files

- `basic-rag-application.ipynb` – Main notebook where RAG pipeline is built.
- `pdf_used.pdf` – The PDF used as context (replaceable).

---

## 📌 Notes

- Ollama runs models locally. Make sure to start the Ollama server before using the notebook.
- You can swap in any PDF and ask context-based questions.
- This is a basic prototype—perfect for learning how real-world AI assistants work!

---

## ✨ Credits

Made by IEEE CS with ❤️


