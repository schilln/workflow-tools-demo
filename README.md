# Workflow Tools Demo

## `git`

### `pre-commit`: run tools before every `git commit`

- [Homepage](https://pre-commit.com/)
- Configure with `Ruff` (below) to format and lint code
- Configure with `nb-clean` (below) to clean Jupyter notebooks
- Ensure only formatted and linted code gets committed, avoiding extraneous changes (e.g., style, whitespace, metadata)

## GitHub: free GitHub Pro for students

- [GitHub Education](https://github.com/education/students)
- [GitHub Student Developer Pack](https://education.github.com/pack)
- *Free* access to Copilot Student (essentially Pro)
  - Completions
  - Premium models
  - Agents
  - Premium requests
  - Can use within VS Code

## Python

### `uv`: dependency management (replacing `pip`)

- [Homepage](https://docs.astral.sh/uv/)
- [Install](https://docs.astral.sh/uv/getting-started/installation/) with single command
- 10–100x faster than `pip` (implemented in Rust)
- Manages Python virtual environment
- Familiar for `pip` users

### `ruff`: formatting and linting

- [Homepage](https://docs.astral.sh/ruff/)
- [Install](https://docs.astral.sh/ruff/installation/) with `uv`
- Insanely fast (10–100x faster than other linters; implemented in Rust)
- Easily format code so you don't have to
  - line length
  - function calls
  - Nested lists/tuples/dicts
- Lints code
- Easily configure non-default formatting and linting rules
- Configure with `pre-commit` git hook to ensure every commit is formatted and linted

### `nb-clean`: clean Jupyter notebooks

- [PyPI homepage](https://pypi.org/project/nb-clean/)
- Strip metadata from Jupyter notebooks so `git diff` shows only code changes
- Configure with `pre-commit` git hook to ensure every commit is cleaned

## LaTeX

### LaTeX Workshop: LaTeX tools for VS Code

- [VS Code extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
- Edit, format, and compile LaTeX within VS Code
- No compile time limit
- Two-way sync: click/hotkey within `.tex` or PDF file to jump to corresponding location in the other
- Use `git` on `.tex` files

### Overleaf Workshop: work on Overleaf documents within VS Code

- [VS Code extension](https://marketplace.visualstudio.com/items?itemName=iamhyc.overleaf-workshop)
- Work on *live* Overleaf documents from within VS Code

## VS Code

- [Settings Sync](https://code.visualstudio.com/docs/configure/settings-sync): sync settings, shortcuts, extensions, and more using GitHub account

### Extensions

- [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop): see [LaTeX](#latex) section above
- [Overleaf Workshop](https://marketplace.visualstudio.com/items?itemName=iamhyc.overleaf-workshop): see [LaTeX](#latex) section above
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): spell check using built-in dictionaries (e.g., English) and custom dictionaries
- [Zoom Bar](https://marketplace.visualstudio.com/items?itemName=wraith13.zoombar-vscode): finer control over zoom level
- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens): extra tools for `git`/GitHub
  - May be overkill due to VS Code's improving built-in git support

## Zotero: reference management

- [Homepage](https://www.zotero.org/)
- [Install](https://www.zotero.org/download/)
- Organize references (e.g., academic papers)
- Generate reference list or `.bib` file in a few clicks
- Import references from Google Scholar, arXiv, etc. in a few clicks with [browser extension](https://www.zotero.org/download/)
- [Better BibTeX extension](https://retorque.re/zotero-better-bibtex/): better support for `BibTeX`
