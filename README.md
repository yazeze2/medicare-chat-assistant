# Medicare Chat Assistant

A work-in-progress LLM-powered assistant for answering Medicare billing, coverage, and policy questions. The project aims to combine a fine-tuned LLaMA 3–8B model with policy retrieval using Retrieval-Augmented Generation (RAG).

    This project is in the initial setup phase. No code or models are functional yet.

🚧 Goals

 - Fine-tune an open-source LLM (starting with LLaMA 3–8B) using Medicare billing and provider data
 - Implement a RAG pipeline to retrieve relevant Medicare coverage policies (NCDs/LCDs)
 - Deploy a FastAPI backend for querying the model
 - Optionally build a lightweight UI using Streamlit or Gradio

📁 Planned Directory Structure
```
medicare-chat-assistant/
│
├── api/ # FastAPI backend for chat interface
├── data/ # Medicare datasets (not committed to Git)
├── models/ # LoRA weights and base models (not committed to Git)
├── rag/ # Document indexing and retrieval (FAISS/ChromaDB)
├── tuning/ # Fine-tuning scripts for LLaMA 3–8B using LoRA
├── ui/ # Optional Streamlit or Gradio frontend
│
├── requirements.txt
├── README.md
├── .gitignore
```

Future Features (Planned)

 - Fine-tune using LoRA with Medicare claims data
 - Embed Medicare policy documents and set up vector search
 - Integrate model and retriever via API
 - Deploy web-based chat interface

 
=======
