# RAG PDF AI Agent

A command-line Retrieval-Augmented Generation (RAG) assistant built with **Python**, **LlamaIndex**, and **OpenAI**. This tool allows you to ingest PDF documents, index their contents into a vector store, and query them through either an interactive chat loop or single-command prompts.

## Feature

* **Document Indexing:** Automatically reads and chunks PDF documents using LlamaIndex's `SimpleDirectoryReader` and `VectorStoreIndex`
* **Dual Execution Modes:** 
  * **Interactive Chat Mode:** Multi-turn conversational interface with persistent memory management (`ChatMemoryBuffer`)
  * **Single-Query Mode:** Quick, automated single-question answers with source chunk tracking (`similarity_top_k=5`)
* **Configurable LLM:** Powered by OpenAI models (defaulting to `gpt-4o-mini` for fast and accurate context retrieval)

## Tech Stack

* **Python 3.11**
* **LlamaIndex** (Core data framework for RAG)
* **OpenAI API** (LLM & Embeddings)
* **Python-Dotenv** (Environment configuration)
* **Argparse** (CLI argument management)

## Installation & Setup

1. **Clone the repository:**
   
   ```bash
   git clone [https://github.com/your-username/RAG_PDF_AI_Agent.git]
   cd RAG_PDF_AI_Agent
   ```

2. **Create and activate a virtual environment:**
   
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

3. **Install dependencies:**
   
```bash
pip install -r requirements.txt
```

4. **Configure your environment variables:**
   
Create a .env file in the root directory and add your OpenAI API key:

```bash
OPENAI_API_KEY=your_openai_api_key
```
## Usage

1. **Interactive Chat Mode**
   
Run the script with a PDF path to enter an ongoing conversational session:

```bash
python agent.py --pdf path/to/document.pdf
```
Type quit, exit, or q to end the session.

2. **Single-Question Mode**
   
Pass a specific question via the --question flag to get an immediate answer and view source node counts.

```bash
python agent.py --pdf path/to/document.pdf --question "What is the main finding?"
```
