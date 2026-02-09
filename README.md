# 🧠 The AI Psychologists: Mental Wellness Copilot

Developed in collaboration with [@paulpop30](https://github.com/paulpop30), [@rsilaghi](https://github.com/rsilaghi), and [@AlexResiga](https://github.com/AlexResiga), this project is a private, **RAG-based (Retrieval-Augmented Generation)** assistant designed to provide students with safe, grounded, and evidence-based mental health support.

By leveraging curated resources from the **National Institute of Mental Health (NIMH)** and other student-focused organizations, the Copilot provides reliable answers to psychological and emotional queries while ensuring privacy through local execution.

---

## 🚀 Key Features

* **Private RAG Assistant:** Trained on curated mental health materials to provide grounded and safe responses.
* **Document Structure-Based Chunking:** Detects headings via font size analysis to ensure text chunks are semantically logical and topic-aligned.
* **Recursive Refinement:** Splits large sections into optimized chunks (~700 characters) with a 100-character overlap to preserve context.
* **Context Window Enrichment:** Fetches neighboring chunks during retrieval to provide the LLM with a broader understanding of the topic.
* **Safety Protocols:** Integrated toxicity filtering flags harmful keywords (e.g., suicide, self-harm) and redirects users to professional help.
* **Custom UI:** A user-friendly web interface built with **Gradio** for seamless student interaction.

---

## 🛠️ System Architecture & Tech Stack

* **LLM:** `phi-4-reasoning-plus` (Running locally via LM Studio).
* **Embeddings:** `nomic-embed-text-v1.5`.
* **Vector Database:** **ChromaDB**.
* **Orchestration:** LangChain.
* **Evaluation:** Ragas framework for measuring Faithfulness and Relevancy.

---

## 📋 Prerequisites & Setup

### 1. Local LLM Configuration (LM Studio)
This project requires **LM Studio** to host the models locally:
1.  Download and install [LM Studio](https://lmstudio.ai/).
2.  Search for and download:
    * **LLM:** `phi-4-reasoning-plus`
    * **Embedding Model:** `nomic-embed-text-v1.5`
3.  Start the **Local Server** in LM Studio (defaulting to `http://localhost:1234`).

### 2. Installation
First, clone the repository to your machine, then install the necessary libraries:

pip install pypdf pymupdf langchain langchain-community langchain-openai chromadb requests gradio ragas datasets scikit-learn

### How to Run

1. Prepare Data: Ensure your PDF resources are located in the database_pdfs/ folder as referenced in the notebook.

2. Jupyter Notebook: Open fml_FINAL1.ipynb.

3. Execute Cells: Run the boxes in order. The notebook is structured into logical steps:

        * Data Importing and PDF selection criteria.

        * Vector database preparation (Chunking & Embedding).

        * RAG Chain construction and memory integration.

        * Gradio UI launch.

        * Prompt Engineering evaluation.

### Evaluation & Prompt Engineering

We systematically evaluated 10 different prompt templates (Baseline, Role, Safety, Empathy, etc.) using the Ragas framework.

    - Winning Prompt: The "Reflective" template.

    - Performance: Achieved the best balance of Faithfulness (accuracy to source) and Relevancy (addressing student concerns).



!!! This tool is an AI assistant and not a replacement for professional medical advice, diagnosis, or treatment. If you or someone you know is in immediate distress, please contact the National Suicide Prevention Lifeline or professional emergency services.

For more details, here is a PowerPoint presentation: [Presentation(1).pptx](https://github.com/user-attachments/files/20861454/Presentation.1.pptx)
