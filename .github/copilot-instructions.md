# Copilot Project Instructions

These instructions are for GitHub Copilot and Copilot Chat to provide optimal code suggestions and assistance for the `document-to-podcast` repository.

## Project Overview
- **Type:** Python application
- **Purpose:** Convert documents (Markdown, PDF, DOCX, HTML) into podcasts using local AI models.
- **Key Directories:**
  - `src/document_to_podcast/` — main source code
  - `tests/` — all tests (unit, integration, e2e)
  - `docs/` — documentation

## Copilot-Specific Guidance
- **Always follow existing code style and patterns.**
- **Prioritize Python 3.10 compatibility.**
- **When generating code:**
  - Use type hints and docstrings.
  - Add/modify tests for all new or changed code.
  - Update documentation if public APIs or CLI change.
- **For new document types:**
  - Update data loaders and cleaners in `src/document_to_podcast/preprocessing/`.
  - Add/modify tests in `tests/unit/preprocessing/`.
- **For new model integrations:**
  - Add to `src/document_to_podcast/inference/`.
  - Add/modify tests in `tests/unit/inference/`.
- **For CLI changes:**
  - Update `src/document_to_podcast/cli.py` and related docs/tests.

## Dev Container
- Use `.devcontainer/devcontainer.json` for environment setup.
- Python 3.10 is required.
- `.github/setup.sh` is run post-create.

## Best Practices
- Keep dependencies minimal and up to date.
- Write clear, atomic commits.
- Ensure all new features/bugfixes are tested.
- Use clear, descriptive docstrings and comments.

## Copilot Chat
- When asked for help, prefer solutions that match the above structure and practices.
- If unsure, ask for clarification or suggest best practices based on the project context.

---
_Last updated: 2025-08-05_
