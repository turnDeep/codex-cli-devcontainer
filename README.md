# Codex CLI Dev Container Environment

This repository provides a ready-to-use VS Code Dev Container for experimenting with the Codex CLI.
It installs the CLI globally inside the container and forwards common ports for authentication flows.

## Quick Start

1. Open the project in VS Code.
2. Run **Dev Containers: Reopen in Container**.
3. After build completes, verify the CLI:
   ```bash
   codex --version
   ```
4. (Optional) Configure your API key in a `.env` file:
   ```bash
   CODEX_API_KEY=your-api-key-here
   ```

## Configuration

- CLI settings live in [`/.codex/settings.json`](.codex/settings.json).
- The dev container definition is in [`.devcontainer/`](.devcontainer/).
- Ports `3000`, `3002`, `5000` and `8080` are forwarded for tools that require a browser callback.

Happy coding with Codex CLI! 🚀
