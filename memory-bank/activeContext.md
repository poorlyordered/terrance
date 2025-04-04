# Active Context: Terrance (Based on Archon V6) - Initial Setup & Rename

## Current Focus

-   Updating the Memory Bank documentation to reflect the project name change from "Archon" to "Terrance".
-   Ensuring consistency across all core Memory Bank files.

## Recent Changes

-   **Dependencies Installed:** Successfully ran `venv\Scripts\pip.exe install -r requirements.txt` to install all project dependencies into the virtual environment. This resolved initial Pylance warnings in `streamlit_ui.py` related to missing imports (`dotenv`, `streamlit`, `logfire`).
-   **Memory Bank Creation:** Created the initial core Memory Bank files based on the original Archon `README.md`.
-   **Project Rename:** Updated `projectbrief.md`, `productContext.md`, `systemPatterns.md`, and `techContext.md` to use the name "Terrance" instead of "Archon", noting that the codebase is based on Archon V6.

## Next Steps

1.  Update the final core Memory Bank file: `progress.md` with the new name.
2.  Confirm completion of the rename task with the user.
3.  Await further instructions.

## Active Decisions & Considerations

-   Following the user's request to rename the project to "Terrance" within the Memory Bank documentation.
-   Maintaining references to the original "Archon" project where relevant (e.g., codebase origin, file paths, script names).

## Important Patterns & Preferences

-   **Memory Bank First:** Always consult and update the Memory Bank before proceeding with tasks.
-   **Iterative Documentation:** Update Memory Bank files as new information is discovered or significant changes are made.
-   **Tool-Based Actions:** Utilize available tools (like `read_file`, `write_to_file`, `execute_command`) to interact with the project.

## Learnings & Insights

-   The project uses a virtual environment (`venv/`) for managing Python dependencies.
-   Directly invoking `venv\Scripts\pip.exe` is a reliable way to install packages into the venv on Windows when command chaining fails.
-   The project structure is modular, separating UI (`streamlit_ui.py`), core logic (`archon/`), services (`graph_service.py`), resources (`agent-resources/`), and deployment (`Dockerfile`, `run_docker.py`). Note that directory/file names like `archon/` and `run_docker.py` retain their original names from the Archon project.
