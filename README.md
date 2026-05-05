# Machine Learning Knowledge Assistant (RAG)

An end-to-end **Retrieval-Augmented Generation (RAG)** system built on the book *Introduction to Machine Learning with Python* by Andreas C. Müller and Sarah Guido.

This project enables users to ask natural language questions and receive **accurate, context-grounded answers** from the book.

---

##  Project Overview

This application combines:

*  **Document Processing** (PDF → text chunks)
* **Semantic Search** (vector embeddings + FAISS)
* **LLM-based Answer Generation**

The system retrieves relevant sections from the book and uses them to generate **reliable, hallucination-minimized responses**.

---

## How It Works (RAG Pipeline)

1. **Load PDF**

   * Extract text from all pages

2. **Text Chunking**

   * Split into smaller overlapping chunks
   * Chunk size: `800`
   * Overlap: `100`

3. **Embedding Generation**

   * Model: `all-MiniLM-L6-v2`
   * Converts text into vector representations

4. **Vector Database**

   * FAISS stores embeddings
   * Enables fast similarity search

5. **Query Processing**

   * User query → embedding
   * Retrieve top-k relevant chunks

6. **Answer Generation**

   * Retrieved chunks passed to LLM
   * Prompt ensures grounded responses

---

##  Tech Stack

* **Python**
* **LangChain**
* **FAISS**
* **SentenceTransformers**
* **OpenAI API** (or local LLM)
* **Streamlit** (for UI)

---

##  Project Structure

```
.
├── rag_ml_assistant.py   # Core RAG pipeline
├── app.py                # Streamlit UI
├── intro-to-ml.pdf       # Dataset (ML book)
├── faiss_index/          # Stored vector DB
├── requirements.txt      # Dependencies
└── README.md             # Project documentation
```

---

##  Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/rag-ml-assistant.git
cd rag-ml-assistant
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

Or manually:

```bash
pip install langchain faiss-cpu sentence-transformers pypdf streamlit openai
```

---

##  Setup API Key

Set your OpenAI API key:

```bash
export OPENAI_API_KEY="your_api_key"
```

Or inside Python:

```python
import os
os.environ["OPENAI_API_KEY"] = "your_api_key"
```

---

##  Running the Application

### Option 1: CLI Mode

```bash
python rag_ml_assistant.py
```

---

### Option 2: Web UI (Recommended)

```bash
streamlit run app.py
```

---

##  Example Queries

Try asking:

* What is supervised learning?
* What is overfitting?
* Explain k-nearest neighbors
* What is cross-validation?
* What is clustering?

---

## Key Features

* ✅ Context-aware answers
* ✅ Reduced hallucination
* ✅ Fast semantic search
* ✅ Works on custom PDFs
* ✅ Interactive UI

---

## Limitations

* Answers depend on retrieved chunks
* Complex diagrams/math may not parse well
* Requires good chunking for best results

---

##  Future Improvements

* 🔹 Add page-number citations
* 🔹 Hybrid search (BM25 + embeddings)
* 🔹 Reranking for better accuracy
* 🔹 Local LLM support (Ollama, Llama)
* 🔹 Multi-document support

---

##  Dataset

* *Introduction to Machine Learning with Python*
* Source: O’Reilly Media

---

## Contributing

Pull requests are welcome!
For major changes, open an issue first to discuss what you'd like to change.

---

##  License

This project is for educational purposes.

---

##  Acknowledgements

* Authors of the ML book
* Open-source ML community
* LangChain & FAISS contributors



