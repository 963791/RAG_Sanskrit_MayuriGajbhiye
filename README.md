# Sanskrit Document Retrieval-Augmented Generation (RAG) System

This project implements a **CPU-only Retrieval-Augmented Generation (RAG) system** for answering queries from Sanskrit documents.

The system performs document ingestion, preprocessing, vector-based retrieval, and extractive answer generation using a lightweight and efficient pipeline.

---

## 🚀 Features

- 📄 Supports Sanskrit documents (.txt, .pdf)
- 🔍 Vector-based retrieval using FAISS
- 🧠 Semantic search using multilingual embeddings
- ⚡ CPU-only execution (no GPU required)
- 🔁 Accepts Sanskrit and transliterated queries
- 📚 Extractive answer generation (no hallucination)
- 🧩 Modular and clean RAG pipeline

---

## 🏗️ System Architecture


User Query
↓
Preprocessing (Sanskrit/Transliteration Handling)
↓
Embedding Generation
↓
FAISS Vector Retrieval
↓
Top-K Relevant Context Chunks
↓
Extractive Answer Selection
↓
Final Output


---

## 📁 Project Structure

```

RAG\_Sanskrit\_<YourName>/
│
├── code/
│   ├── ingest.py
│   ├── preprocess.py
│   ├── build\_index.py
│   ├── retriever.py
│   ├── answer\_extractor.py
│   └── query.py
│
├── data/
│   └── Sanskrit documents (.txt / .pdf)
│
├── index/
│   └── FAISS index files
│
├── report/
│   └── Technical report (PDF)
│
├── requirements.txt
└── README.md

⚙️ Installation
1. Create virtual environment
python -m venv venv
2. Activate environment

Windows:

venv\Scripts\activate
3. Install dependencies
pip install -r requirements.txt
▶️ How to Run
Step 1: Build Index
cd code
python build_index.py
Step 2: Run Query System
python query.py
💡 Example Queries
कालीदासः कः आसीत् ?
kalidasa kaḥ āsīt?
शंखनादः किम् आनयति ?
🧪 Example Output
Answer:
चतुरः खलु कालीदासः

Retrieved Contexts:
1. न खलु जानाति पण्डितः यत् कालीदासः एव सः
2. चतुरः खलु कालीदासः
3. सः अपि तदैव पृष्टवान् ...
🧠 Model Details
Component	Technology
Embeddings	sentence-transformers (multilingual model)
Retrieval	FAISS (vector search)
Pipeline	Custom Python RAG implementation
Execution	CPU only
⚠️ Limitations
Extractive (not generative) answers
Depends on quality of source documents
Limited Sanskrit linguistic understanding
No GPU acceleration
🔮 Future Improvements
Hybrid BM25 + FAISS retrieval
Better Sanskrit transliteration handling
Cross-encoder re-ranking
Streamlit web UI
Fine-tuned Sanskrit LLM integration