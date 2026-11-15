# 🛡️ Secure Starter Template

A lightweight GitHub starter template configured with baseline `.gitignore` rules, custom Gitleaks detection configs, local pre-commit hooks, and automated CI secret scanning.

---

## ✨ What's Included

* **Baseline `.gitignore`:** Excludes `.env`, `.env.*`, `.pem`, `.key`, `.log`, `.sql`, and local database files (`.sqlite`, `.db`) from version control while keeping `.env.example` tracked.
* **Custom `.gitleaks.toml` Rules:** Extends Gitleaks' default ruleset with regex patterns for secret variable assignments (`API_KEY`, `DB_PASSWORD`, `SECRET_KEY`), sensitive file extensions, and line-level allowlists for documentation placeholders.
* **Local Pre-Commit Hook (`.pre-commit-config.yaml`):** Runs Gitleaks `v8.30.1` with your custom `.gitleaks.toml` rules before commits leave your workstation.
* **Automated CI Secret Scanning (`.github/workflows/secret-scan.yml`):** Executes the pinned Gitleaks `v8.30.1` CLI binary on every `push` and `pull_request` across public, private, and organization repositories without third-party license dependencies.
* **Template README Initializer (`.github/workflows/init-template.yml`):** On pushes to `main` in a repository created from this template, changes the README to the new repository name and removes the initializer workflow.

---

## 🚀 How to Use This Template

1. Click **Use this template** > **Create a new repository** at the top of this page.
2. Select **Public** or **Private** visibility for your new project.
3. Clone your repository locally and activate the pre-commit hook:
   ```bash
   pip install pre-commit && pre-commit install
   ```
4. Maintain a `.env.example` file with placeholder variable names (e.g., `API_KEY=your_key_here`) so collaborators and AI coding assistants know the required environment structure without accessing real credentials.

---

## 📁 Repository Structure

```text
├── .github/
│   └── workflows/
│       ├── init-template.yml  # Initializes README with repository name, then removes itself
│       └── secret-scan.yml    # Pinned Gitleaks v8.30.1 CLI workflow
├── .gitleaks.toml            # Custom secret, filename, and allowlist rules
├── .gitignore                # Baseline ignore rules for secrets, logs, and DBs
├── .pre-commit-config.yaml   # Local pre-commit hook config (v8.30.1)
├── LICENSE                   # MIT License
└── README.md                 # Template documentation
```

---

## 🔒 Defense-in-Depth Recommendation

This template protects both local commits (via `.pre-commit-config.yaml`) and remote pushes (via GitHub Actions). For machine-wide protection across all repositories, pair this setup with a global `.gitignore_global` and a global `core.hooksPath` configuration.

---

**Last updated:** 2026-11-15  
**© Martian0612**
