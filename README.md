# 🧠 AI-Powered Resume Screener — A RAG-Based HR Assistant

## 📄 Project Overview

This project is a **Retrieval-Augmented Generation (RAG)**-powered assistant that helps HR professionals screen resumes intelligently. Upload 10–20 resumes in `.pdf` or `.txt` format and ask natural-language questions like:

> “Find candidates with **TensorFlow** and **AWS** experience.”

The assistant retrieves the most relevant resumes and generates a human-readable answer using a language model.


---

## 🔧 Tech Stack

### 🧠 LLMs :
- Hugging Face:' google/flan-t5-small'

### 🗃️ Vector Store:
 `FAISS`

### 🔤 Embedding Models:
- `sentence-transformers/all-MiniLM-L6-v2` 

### 🧰 Frameworks & Libraries:
- `LangChain` ( pipeline)
- `PyMuPDF` (`fitz`) for PDF parsing


---

## 🛠️ How It Works

### 1. 🧾 Load & Preprocess Resumes
- Accepts `.pdf` or `.txt` files
- Extracts text using `PyMuPDF` or similar
- Splits text into manageable chunks (e.g., 500 tokens)

### 2. 🔍 Embed & Store
- Use `sentence-transformers` to convert chunks into embeddings
- Store vectors in  `FAISS`

### 3. ❓ Query & Retrieve
- Convert user question into embedding
- Perform vector search to find top-k relevant chunks

### 4. 💬 Generate Answer
- Format prompt with retrieved context
- Use selected LLM to produce final natural language answer

---

## 🧪 Example Use Case

### Sample Question:Find candidates with TensorFlow + AWS experience?
result : 'ML Enginee
