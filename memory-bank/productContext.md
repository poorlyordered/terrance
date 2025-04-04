# Product Context: Terrance

## Purpose & Vision

Terrance aims to be the first **"Agenteer"** – an AI system capable of autonomously building, refining, and optimizing other AI agents. Its purpose is twofold:
1.  **Practical Tool:** To accelerate and simplify the development of AI agents for developers.
2.  **Educational Framework:** To demonstrate and explore advanced concepts in agentic systems, including planning, feedback loops, and domain knowledge integration.

## Problem Solved

Building robust AI agents is complex, requiring expertise in:
-   AI frameworks (e.g., Pydantic AI, LangGraph)
-   Agentic design patterns (planning, reasoning, refinement)
-   Tool integration and usage
-   Prompt engineering
-   Iterative development and testing

Terrance aims to automate much of this complexity, allowing developers to focus on defining the *what* (agent requirements) rather than the *how* (low-level implementation details). It addresses the challenge of rapidly evolving AI frameworks and the need for efficient agent creation.

## How It Should Work (User Experience - Based on Archon V6)

The primary user interaction occurs through the Streamlit UI:

1.  **Setup:** Users are guided through configuring environment variables (API keys, models), setting up a Supabase vector database, crawling necessary documentation (e.g., Pydantic AI), and starting the core agent service. MCP integration is optional.
2.  **Agent Creation:**
    -   Users describe the desired AI agent in the Chat interface.
    -   Terrance's *Reasoner LLM* defines the high-level scope.
    -   The *Advisor Agent* suggests relevant prebuilt tools or examples from the library.
    -   The *Primary Coding Agent* generates the initial agent code based on the scope, documentation (RAG), and selected tools/examples.
3.  **Refinement:**
    -   Users review the generated agent code.
    -   They can provide specific feedback for revisions *or* trigger autonomous refinement.
    -   Autonomous refinement involves specialized agents (Prompt Refiner, Tools Refiner, Agent Refiner) improving different aspects of the generated code.
    -   The Primary Coding Agent incorporates feedback (user or agent) and iterates.
4.  **Completion:** Once satisfied, the user receives the final, refined agent code with instructions for running it.

## Target User Experience Goals

-   **Guided & Intuitive:** The Streamlit UI should make the complex process accessible.
-   **Efficient:** Reduce the time and effort required to build functional AI agents.
-   **Transparent:** Provide visibility into the agent generation process (scope, logs).
-   **Flexible:** Support various LLMs (OpenAI, Anthropic, OpenRouter, Ollama) and integration patterns (MCP).
-   **Educational:** Allow users to learn about agentic architectures by observing Terrance's process.
-   **Extensible:** Encourage community contributions to the tool/example library.
