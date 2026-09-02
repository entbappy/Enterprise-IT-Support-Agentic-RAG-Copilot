1. **`requirements.txt`** — Add all required libraries such as LangGraph, OpenAI, Pinecone, Tavily, FastAPI, document loaders, etc.

2. **`.env`** — Configure API keys, Pinecone index/namespace, OpenAI model, embedding model, and other environment settings.

3. **`app/core/config.py`** — Load all `.env` configurations into the application using a centralized settings class.

4. **`data/sample_kb/`** — Add sample company IT documents such as VPN, password reset, MFA, and troubleshooting policies.

5. **`app/services/ingestion.py`** — Build the document loading and chunking pipeline for PDF, TXT, Markdown, and DOCX files.

6. **`app/rag/vectorstore.py`** — Configure OpenAI embeddings, connect with Pinecone, store document vectors, and create the retriever.

7. **`ingest_sample_kb.py`** — Create a simple script that loads the sample documents, chunks them, and uploads them into Pinecone.

8. **`app/rag/state.py`** — Define the LangGraph shared state containing the question, retrieved documents, grades, answer, retries, citations, and trace.

9. **`app/rag/workflow.py`** — Build the main Agentic RAG workflow: **Route → Retrieve → Grade → Web Search → Rewrite/Retry → Generate Answer**.

10. **`app/services/audit.py`** — Add audit logging so you can track questions, sources used, and the agent's execution path.

11. **`app/api/routes.py`** — Create FastAPI endpoints for chatting with the Agentic RAG system, uploading documents, health checks, and audit information.

12. **`app/main.py`** — Create the main FastAPI application and connect the API routes, templates, and static files.

13. **`templates/index.html`** — Build the main UI structure for chat, Agentic RAG workflow visualization, document upload, sources, and agent trace.

14. **`static/css/style.css`** — Add styling to make the application look like a professional enterprise AI product.

15. **`static/js/app.js`** — Connect the frontend with FastAPI and display answers, citations, source routes, execution traces, and upload results dynamically.

16. **`run.py`** — Create the final application entry point to start the FastAPI server.

