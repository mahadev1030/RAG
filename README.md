**Project: RAG Codes 1**

This workspace collects notebooks, reference PDFs, and example text files used to explore Retrieval-Augmented Generation (RAG) workflows, indexing, retrieval, reranking, and evaluation.

Below is a short description of each file and quick instructions for opening and running the notebooks.

**Files in this workspace**

- `Advanced RAG With Re-Rank.ipynb`
  - Notebook demonstrating an advanced RAG pipeline that includes a reranking stage after initial retrieval. Useful for improving answer relevance when using multiple retrievers or large candidate pools.

- `Advanced RAG_QueryRewriting.ipynb`
  - Notebook focused on query-rewriting techniques to improve retrieval quality (e.g., query expansion, reformulation with LLMs, or prompt-based rewriting).

- `Data Loading, Indexing, Retrieval and Generation.ipynb`
  - End-to-end pipeline notebook showing data ingestion, creating an index (vector store), retrieval, and generation steps. Good as a starting template for projects.

- `RAG Guided Project.ipynb`
  - Guided project-style notebook that walks through a project-oriented RAG build with explanations and exercises.

- `RAGEvaluation.ipynb`
  - Notebook containing evaluation metrics and experiments to measure the quality of RAG outputs (e.g., retrieval accuracy, generation relevance, reranker impact).

** Quick start (open & run)**

1. Install a recent Python (3.8+) and create an isolated environment (venv or conda).

   Example using venv:

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   pip install --upgrade pip
   ```

2. Install Jupyter and common packages used for RAG experiments. The exact set of packages depends on which notebooks you open, but this minimal set will let you run them and install extras as needed:

   ```bash
   pip install jupyterlab notebook ipywidgets
   pip install transformers sentence-transformers faiss-cpu langchain datasets
   # If you plan to run evaluation or accelerate training:
   pip install accelerate evaluate
   ```

   Note: Some packages (like `faiss-cpu`) may require platform-specific wheels. If you use macOS ARM, prefer the appropriate wheel or use conda.

3. Start Jupyter Lab / Notebook from the workspace root and open any notebook:

   ```bash
   jupyter lab
   ```

4. When a notebook needs external APIs (OpenAI, Anthropic, etc.), set the appropriate environment variables before running the cells. For example:

   ```bash
   export OPENAI_API_KEY="your_key_here"
   ```

**Suggested workflow**

- Start with `Data Loading, Indexing, Retrieval and Generation.ipynb` to create your index and confirm retrieval works on a small subset of documents.
- Try `Advanced RAG_QueryRewriting.ipynb` if retrieval relevance is poor; rewriting queries often improves recall for short user queries.
- Use `Advanced RAG With Re-Rank.ipynb` to add a reranking stage when you have many candidates.
- Run `RAGEvaluation.ipynb` to measure the impact of changes (retriever type, embedding model, reranker) on metrics you care about.

**Data & licensing notes**

- Several files (for example `Harry Potter 1 - Sorcerer's Stone.txt`) may be copyrighted. Do not redistribute copyrighted text without permission—use these files only for personal study or with proper licensing.
- Public-domain or freely-redistributable files (if any) are fine to reuse. When in doubt, treat the file as restricted and avoid sharing it publicly.

**Next steps / improvements**

- Add a `requirements.txt` or `environment.yml` file to pin exact versions used by the notebooks.
- Add small README sections per-notebook describing which cells to run first and which optional dependencies are required.
- Add automated tests or a small script to build the index and run a smoke test query to validate the environment.

**Contact / maintenance**

If you want me to:

- generate a `requirements.txt` tuned to these notebooks,
- add a smoke-test script that builds an index from one file and runs a sample query,
- or create brief per-notebook READMEs with required/exact packages and expected runtime — tell me which and I'll add them.
