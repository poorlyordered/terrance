# Technical Context: Terrance (Based on Archon V6)

## Core Technologies

-   **Language:** Python 3.11+
-   **Agent Frameworks:**
    -   LangGraph: For orchestrating the multi-agent workflow.
    -   Pydantic AI: Used by the coding agent for generating structured agent code (initially, future versions may support others).
-   **Web UI:** Streamlit
-   **API Service:** FastAPI (for `graph_service.py`)
-   **Vector Database:** Supabase (Postgres with pgvector) for RAG.
-   **Containerization:** Docker
-   **LLMs:** Supports OpenAI, Anthropic, OpenRouter API keys, or local models via Ollama. (Note: Streaming in UI currently only confirmed for OpenAI).
-   **IDE Integration:** Model Context Protocol (MCP)

## Key Dependencies (from `requirements.txt`)

*Note: This is not exhaustive, but highlights major libraries.*

-   `langgraph`: Core workflow orchestration.
-   `pydantic-ai`: Used for agent code generation structure.
-   `streamlit`: Powers the user interface.
-   `fastapi`: Runs the agent generation service.
-   `uvicorn`: ASGI server for FastAPI.
-   `supabase`: Client library for interacting with Supabase DB.
-   `openai`, `anthropic`, `groq`, `mistralai`, `cohere`: LLM client libraries.
-   `langchain-core`, `langsmith`: Core LangChain components.
-   `docker`: Python library for interacting with Docker daemon (used by `run_docker.py` for the original Archon structure).
-   `python-dotenv`: For loading environment variables from `.env` files.
-   `logfire`: Used for logging/tracing (indicated by import in `streamlit_ui.py`).
-   `mcp`: MCP SDK library.
-   `beautifulsoup4`, `html2text`, `lxml`: Used by documentation crawler (`archon/crawl_pydantic_ai_docs.py`).
-   `tiktoken`: For token counting (likely used with OpenAI models).

## Development Setup (Based on Archon)

**Recommended:** Docker

1.  Clone repo.
2.  Run `python run_docker.py`. This script (from Archon) handles:
    -   Building the `mcp/Dockerfile` image.
    -   Building the main `Dockerfile` image (for the Archon structure).
    -   Stopping/removing existing containers.
    -   Starting both containers with correct port mappings (UI: 8501, Graph Service: 8100).
    -   Uses `.env` file if present for environment variables during build/run.

**Alternative:** Local Python

1.  Clone repo.
2.  Create and activate a virtual environment (`python -m venv venv`, `venv\Scripts\activate` on Windows).
3.  Install dependencies: `pip install -r requirements.txt`.
4.  Run the UI: `streamlit run streamlit_ui.py`.

## Environment Configuration

-   Managed primarily through the Streamlit UI (**Environment** tab).
-   Settings are saved to `workbench/env_vars.json` (created at runtime, gitignored).
-   Requires API keys for chosen LLMs (OpenAI, Anthropic, etc.) and Supabase credentials.

## Technical Constraints & Considerations

-   **Python Version:** Requires 3.11+.
-   **Streaming Support:** UI streaming currently limited (primarily OpenAI).
-   **Database:** Currently relies on Supabase/pgvector. Future versions might support others.
-   **Framework Focus:** V6 primarily targets building Pydantic AI agents, though future versions aim for broader framework support (e.g., LangGraph agents in V7).
-   **Docker Dependency:** While optional, Docker is the recommended and likely more stable setup due to managing multiple components (UI, Graph Service, MCP Server).
-   **Initial Setup:** Requires several steps via the Streamlit UI (Env, DB, Docs, Service) before agent creation is possible.

## Tool Usage Patterns (from Archon)

-   **`run_docker.py`:** Central script for managing the Dockerized application lifecycle (as defined by Archon).
-   **`streamlit run streamlit_ui.py`:** Command to start the UI in a local setup.
-   **`pip install -r requirements.txt`:** Standard dependency installation for local setup.
-   **Git:** Used for version control and updates (`git pull`).
