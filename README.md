# 📄 AI-Powered PDF Summarizer

🚀 **AI-Powered PDF Summarizer** is a tool that extracts and summarizes **research papers** from **ArXiv PDFs** using **Ollama (Gemma 3 LLM)**. The system provides structured, downloadable summaries to help researchers and professionals quickly grasp key findings.

![PDF Summarizer UI](https://github.com/arjunprabhulal/gemma3_pdf_summarizer/raw/main/PDF_Summarizer.png)

---

## 🛠 Features

- 🌐 **Input an  ArXiv PDF URL** to fetch and summarize papers.
- 📑 **Extracts technical content** (architecture, implementation, results).
- 🔍 **Optimized for large text processing** with **parallel summarization**.
- 🎨 **Modern UI** built with **Streamlit**.
- 📥 **Download summary as a Markdown file**.

---

## 🚀 Tech Stack

| Component         | Technology |
|------------------|------------|
| **Frontend**     | [Streamlit](https://streamlit.io/) |
| **Backend**      | [FastAPI](https://fastapi.tiangolo.com/) |
| **LLM Platform** | [Ollama](https://ollama.com/) |
| **LLM Model**    | [Google Gemma 3](https://developers.googleblog.com/en/introducing-gemma3/) |
| **PDF Processing** | [PyMuPDF (fitz)](https://pymupdf.readthedocs.io/) |
| **Text Chunking** | [LangChain RecursiveCharacterTextSplitter](https://python.langchain.com/docs/modules/data_connection/document_transformers/text_splitters/) |
---

## 🎬 Demo

1️⃣ **Enter an ArXiv PDF URL**  
2️⃣ **Click "Summarize PDF"** 🚀  
3️⃣ **Get a structured summary** with **technical insights** 📝  
4️⃣ **Download as Markdown** 📥  

---

## 🔧 Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/arjunprahulal/gemma3_pdf_summarizer.git
cd gemma3_pdf_summarizer

```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Install Ollama and Gemma 3 LLM


Install Ollama - MacOS/Linux

```bash
curl -fsSL https://ollama.com/install.sh | sh

```

Download Gemma 3 Model

```bash
ollama pull gemma3:27b
```

### 3️⃣ Start the Backend (FastAPI)

```bash
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

### 4️⃣ Start the Frontend (Streamlit)

```bash
streamlit run frontend.py
```

---

## 📜 API Endpoints

### 🔹 Health Check

```http
GET /health
```

Response:
```json
{"status": "ok", "message": "FastAPI backend is running!"}
```

### 🔹 Summarize
Summarize an ArXiv Paper
```
POST /summarize_arxiv/
```
Request Body:
```
{
  "url": "https://arxiv.org/pdf/2401.02385.pdf"
}
```
Response:
```
{
  "summary": "Structured summary of the research paper..."
}
```
