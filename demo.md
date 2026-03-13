# Demo

- GitHub Pro for students
- VS Code
  - Settings Sync
  - Profiles
  - GitHub Copilot Chat
  - `.vscode/` has example settings and keyboard shortcuts
    - User, remote, and workspace settings, each overriding previous
- Create repo

    ```bash
    mkdir my-code && cd my-code
    uv init
    uv add numpy
    uv add --dev ipykernel ruff nb-clean pre-commit
    uv sync
    ```

- Python
  - Copy into Jupyter notebook

    ```python
    # Warning: unformatted code below

    def summarize_numbers(values:list[int]) -> dict[str,float]:
        total=sum(values)
        average = total/len(values) if values else 0
        return {"total":total, "average":average}

    numbers = [[1,2,3,4,5],[2,3,4,5,6]]#Without trailing comma
    more_numbers = [[1,2,3,4,5],[2,3,4,5,6],]#With trailing comma

    [summarize_numbers(nums) for nums in numbers],[summarize_numbers(nums) for nums in more_numbers]
    ```

  - Run > Commit > Run again > Commit again > Show diff
  - Copy `.pre-commit-config.yaml`
  - `uv run pre-commit install`
  - Stage
  - Attempt to commit
  - Show cleaned up code and metadata
  - Format: `shift+alt+f`
- Code Spell Checker
  - `ctrl+.` to add blue-underlined words to dictionaries
- LaTeX / LaTeX Workshop
  - Copy `writing/`
  - Compile and show output
  - Show hover tooltip
    - Citation
    - Figure
    - Reference
    - Equation environment
  - Show panel preview (`ctrl+alt+m`)
  - Two-way sync (double-click in PDF / `ctrl+alt+k` in `.tex`)
  - Format: `shift+alt+f`
- Overleaf Workshop
  - "Log in"
  - Create blank project `Demo` in browser
  - Open in browser and VS Code
- Zotero
  - Import paper with browser extension
  - Annotate PDF
  - Export `.bibtex`
    - Right-click collection or item
    - Click "Export Collection..." or "Export Item..."
  - Add to LaTeX demo
