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

extract for me the query and result : {'query': 'Find candidates with TensorFlow + AWS experience?', 'result': 'ML Engineer', 'source_documents': [Document(id='a1f8335b-9343-482b-ba75-45426c5da54f', metadata={'producer': 'PyFPDF 1.7.2 http://pyfpdf.googlecode.com/', 'creator': 'PyPDF', 'creationdate': 'D:20250723120639', 'source': 'resume/resumes/Resumes_Part2.pdf', 'total_pages': 2, 'page': 0, 'page_label': '1'}, page_content='Bob Lee\nCloud ML Engineer\nSkills: AWS, TensorFlow, Keras, Python\nExperience:\n- Designed AI solutions using TensorFlow models on AWS'), Document(id='58aaae29-9a43-4ae7-a22e-4cd3e3f9276a', metadata={'producer': 'PyFPDF 1.7.2 http://pyfpdf.googlecode.com/', 'creator': 'PyPDF', 'creationdate': 'D:20250723121831', 'source': 'resume/resumes/Resumes_Part3.pdf', 'total_pages': 2, 'page': 1, 'page_label': '2'}, page_content='Emily Davis\nSenior Data Scientist\nSkills: TensorFlow, AWS Sagemaker, SQL\nExperience:\n- Led team developing ML models in TensorFlow'), Document(id='87fe1233-003b-4c49-9475-154a28f20b45', metadata={'producer': 'PyFPDF 1.7.2 http://pyfpdf.googlecode.com/', 'creator': 'PyPDF', 'creationdate': 'D:20250723120639', 'source': 'resume/resumes/Resumes_Part1%20(1).pdf', 'total_pages': 3, 'page': 1, 'page_label': '2'}, page_content='Jane Smith\nData Scientist\nSkills: PyTorch, AWS, TensorFlow, SQL\nExperience:\n- Trained NLP models using TensorFlow\n- Deployed classification models using AWS EC2 and S3')]}
