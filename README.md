# Workflow Tools Demo

## GitHub: free GitHub Pro for students

- [GitHub Education](https://github.com/education/students)
- [GitHub Student Developer Pack](https://education.github.com/pack)
- *Free* access to Copilot Student (essentially Pro)
  - Completions
  - Premium models
  - Agents
  - Premium requests
  - Can use within VS Code (see "GitHub Copilot Chat" under [VS Code Extensions](#extensions) in this document)

## VS Code

- [Settings Sync](https://code.visualstudio.com/docs/configure/settings-sync): sync settings, shortcuts, extensions, and more using GitHub account
- [Profiles](https://code.visualstudio.com/docs/configure/profiles): quickly switch between sets of customizations.
Useful to enable for different programming languages.
For example, independently set

  - Extensions
  - Settings
  - Keyboard shortcuts

### Handy shortcuts

- `ctrl+shift+p`: search VS Code commands
- `ctrl+p`: search files
- `ctrl+,`: open settings

### Extensions

- [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop): (see [LaTeX](#latex) in this document)
- [Overleaf Workshop](https://marketplace.visualstudio.com/items?itemName=iamhyc.overleaf-workshop): (see [LaTeX](#latex) in this document)
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): spell check using built-in dictionaries (e.g., English) and custom dictionaries
  - This repo contains a convenient setup.
    1. Install the VS Code extension.
    1. Copy [`.cspell.config.mjs`](.cspell.config.mjs) into your desired working directory.
    1. Place text files in a `.cspell/` directory to define custom dictionaries (see [`example`](.cspell/) in this repo).
- [Ruff](https://marketplace.visualstudio.com/items?itemName=charliermarsh.ruff): see [`ruff`](#ruff-formatting-and-linting) in this document
  - `shift+alt+f`: format document (`.py` or `.ipynb`)
  - `shift+alt+o`: sort imports (`.py` or `.ipynb`) (custom shortcut described in [`.vscode/keybindings.json`](.vscode/keybindings.json))
- [GitHub Copilot Chat](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat): Access to AI chat, agents, etc. within VS Code
  - [Overview](https://code.visualstudio.com/docs/copilot/chat/copilot-chat)
  - Use GitHub Pro as student (see [GitHub](#github-free-github-pro-for-students) in this document)
  - Disable in specific workspaces (e.g., a class with a no-AI policy)
    1. Open the "Extensions" tab in VS Code
    1. Find "GitHub Copilot Chat"
    1. Click the gear icon
    1. Click "Disable (Workspace)"
- [Zoom Bar](https://marketplace.visualstudio.com/items?itemName=wraith13.zoombar-vscode): finer control over zoom level
- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens): extra tools for `git`/GitHub
  - May be overkill due to VS Code's improving built-in git support
- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint): Lints Markdown files (`.md`)
- [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one): Additional Markdown support
- [Rewrap Revived](https://marketplace.visualstudio.com/items?itemName=dnut.rewrap-revived): wrap comments to a specified line length

## Python

### `uv`: dependency management (replacing `pip`)

- [Homepage](https://docs.astral.sh/uv/)
- 10–100x faster than `pip` (implemented in Rust)
- Manages Python virtual environment
- Familiar for `pip` users
- [Install](https://docs.astral.sh/uv/getting-started/installation/) with single command
  - Linux/macOS: `curl -LsSf https://astral.sh/uv/install.sh | less`

```bash
### Basic usage

# Initialize new directory
mkdir my-code && cd my-code
uv init

# Add dependency
uv add numpy scipy matplotlib

# Ensure dependencies are up-to-date
uv sync

# Run commands using virtual environment (if not activated)
uv run my_python_script.py
```

### `ruff`: formatting and linting

- [Homepage](https://docs.astral.sh/ruff/)
- Insanely fast (10–100x faster than other linters; implemented in Rust)
- Easily format code so you don't have to
  - line length
  - function calls
  - Nested lists/tuples/dicts
- Lints code
- Easily configure non-default formatting and linting rules with `ruff.toml` file (see [example](`ruff.toml`) in this repo)
- Configure with `pre-commit` git hook to ensure every commit is formatted and linted (see [`pre-commit`](#pre-commit-run-tools-before-every-git-commit) in this document)
- [Install](https://docs.astral.sh/ruff/installation/) with `uv`
  - `uv add --dev ruff` (`--dev` for "development")
- Get VS Code extension to configure keyboard shortcuts for formatting files (see "Ruff" under [VS Code Extensions](#extensions) in this document)

### `nb-clean`: clean Jupyter notebooks

- [PyPI homepage](https://pypi.org/project/nb-clean/)
- Strip metadata from Jupyter notebooks so `git diff` shows only code changes
- Configure with `pre-commit` git hook to ensure every commit is cleaned (see [`pre-commit`](#pre-commit-run-tools-before-every-git-commit) in this document)
- Install with `uv`
  - `uv add --dev nb-clean`

```bash
# Clean all notebooks in the current directory (`.`)
# (and recursively in subdirectories),
# leaving outputs untouched (`-o`)
uv run nb-clean clean -o .
```

## `git`

### `pre-commit`: run tools before every `git commit`

- [Homepage](https://pre-commit.com/)
- Configure with `ruff` to format and lint code (see [`ruff`](#ruff-formatting-and-linting) in this document)
- Configure with `nb-clean` to clean Jupyter notebooks (see [`nb-clean`](#nb-clean-clean-jupyter-notebooks) in this document)
- Ensure only formatted and linted code gets committed, avoiding extraneous changes (e.g., style, whitespace, metadata)
- Install
  - Install: `uv add --dev pre-commit` (`--dev` for "development")
  - Configure hooks in `.pre-commit-config.yaml` file (see [example](.pre-commit-config.yaml) in this repo): `uv run pre-commit install`

## LaTeX

### LaTeX Workshop: LaTeX tools for VS Code

- [VS Code extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
- Edit, format, and compile LaTeX within VS Code
- No compile time limit
- Two-way sync: click/hotkey within `.tex` or PDF file to jump to corresponding location in the other
- Use `git` on `.tex` files
- Hover over equations, figures, references and citations for previews
- `ctrl+alt+m`: open preview panel (for editing `equation` environments, etc.)

### Overleaf Workshop: work on Overleaf documents within VS Code

- [VS Code extension](https://marketplace.visualstudio.com/items?itemName=iamhyc.overleaf-workshop)
- Work on *live* Overleaf documents from within VS Code

## Zotero: reference management

- [Homepage](https://www.zotero.org/)
- [Install](https://www.zotero.org/download/)
- Organize references (e.g., academic papers)
- Generate reference list or `.bib` file in a few clicks
- Import references from Google Scholar, arXiv, etc. in a few clicks with [browser extension](https://www.zotero.org/download/)
- [Better BibTeX extension](https://retorque.re/zotero-better-bibtex/): better support for `BibTeX`

## Docker: configure and deploy reproducible build or work environments

- [Docker Engine](https://docs.docker.com/engine/)
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) adds a graphical user interface on top of Docker Engine
- Very common in industry (along with related "containerization" software)
- Similar to virtualization/virtual machines but much lighter weight
