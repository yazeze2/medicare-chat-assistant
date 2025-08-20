# Medicare Chat Assistant

A work-in-progress LLM-powered assistant for answering Medicare billing, coverage, and policy questions. The project aims to combine a fine-tuned LLaMA 3–8B model with policy retrieval using Retrieval-Augmented Generation (RAG).

    This project is in the initial setup phase. No code or models are functional yet.

🚧 Goals

 - Leverage an open-source LLM (LLaMA 3–8B) as the reasoning engine for Medicare questions.
 - Implement a **Retrieval-Augmented Generation (RAG)** pipeline to ground responses in official Medicare documentation (e.g., Medicare & You, NCDs, LCDs).
 - Experiment with **chunking** and **retrieval** strategies (fixed-size, heading-aware, semantic) to optimize recall and precision.
 - Develop a lightweight **evaluation framework** to measure retrieval quality, answer faithfulness, and citation accuracy.
 - Maintain year-specific cost and deductible values via configuration files (amounts_YYYY.yaml) to keep answers current.
 - Deploy a FastAPI backend to expose the assistant as an API for integration and testing.
 - Optionally build a lightweight user interface (Streamlit or Gradio) for demos and interactive exploration.

📁 Planned Directory Structure
```
medicare-assistant/
├─ README.md
├─ LICENSE
├─ .gitignore
├─ requirements.txt                # optional convenience for contributors
├─ pyproject.toml                  # installable package metadata (setuptools)
├─ src/
│  └─ medicare_assistant/          # importable package
│     ├─ __init__.py
│     ├─ version.py
│     ├─ prompts.py
│     ├─ amounts.py
│     ├─ rag/
│     │  ├─ __init__.py
│     │  ├─ chunking.py            # placeholder (to implement)
│     │  ├─ retriever.py           # placeholder (to implement)
│     │  └─ pipeline.py            # placeholder (to implement)
│     └─ ingest/
│        ├─ __init__.py
│        └─ pdf.py                 # placeholder (to implement)
├─ tests/
│  └─ test_imports.py              # starter test
├─ notebooks/
│  ├─ 01_baseline_no_rag.ipynb     # model sanity checks (no RAG)
│  └─ 02_development.ipynb         # to explore and use for dev
│  └─ 03_ingest_and_ask.ipynb      # end-to-end demo (ingest → ask)
├─ data/
│  ├─ raw/                         # source PDFs/HTML (ignored in git)
│  ├─ processed/                   # extracted text (ignored in git)
│  └─ config/
│     └─ amounts_2025.yaml         # year-specific amounts (not packaged)
├─ models/                         # local GGUF models for llama.cpp (ignored)
└─ chroma_db/                      # persisted vector store (ignored)

```

Future Features (Planned)

 - Fine-tune using LoRA with Medicare claims data
 - Embed Medicare policy documents and set up vector search
 - Integrate model and retriever via API
 - Deploy web-based chat interface

Data Sources

This project uses official Medicare references curated for retrieval-augmented generation:
- **Medicare & You 2025 Handbook** – high-level beneficiary guide.
- **CMS Manuals (Pubs. 100-02, 100-04)** – detailed benefit and claims processing rules.
- **National Coverage Determinations (NCDs)** – national-level coverage policies.
- **HCPCS Code Set (2025)** – billing and procedure codes.
- **Medicare Cost Reference (YAML)** – structured deductibles, premiums, and coinsurance for 2025.
- **Enrollment Periods Reference (CMS)** – rules for IEP, GEP, SEP, and OEP.
(See [`data/README.md`](data/README.md) for details.) 
=======
