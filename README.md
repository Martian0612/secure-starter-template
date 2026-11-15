# 🛡️ Secure Starter Template

A lightweight GitHub starter template configured with baseline `.gitignore` rules, custom Gitleaks detection configs, and automated CI secret scanning using open-source tooling.

---

## ✨ What's Included

* **Baseline `.gitignore`:** Excludes `.env`, `.env.*`, `.pem`, `.key`, `.log`, `.sql`, and local database files (`.sqlite`, `.db`) from version control while keeping `.env.example` tracked.
* **Custom `.gitleaks.toml` Rules:** Extends Gitleaks' default ruleset with regex patterns for common secret variable assignments (`API_KEY`, `DB_PASSWORD`, `SECRET_KEY`) and sensitive file extensions.
* **Automated CI Secret Scanning (`.github/workflows/secret-scan.yml`):** Runs the open-source Gitleaks CLI on every `push` and `pull_request` across both public and private repositories without requiring third-party SaaS subscriptions.

---

## 🚀 How to Use This Template

1. Click **Use this template** > **Create a new repository** at the top of this page.
2. Select **Public** or **Private** visibility for your new project.
3. Clone your repository locally and maintain a `.env.example` file with placeholder variable names (e.g., `API_KEY=your_key_here`) so collaborators and AI coding assistants know the required environment structure without accessing real credentials.

---

## 📁 Repository Structure

```text
├── .github/
│   └── workflows/
│       └── secret-scan.yml   # Automated CI secret scanner using Gitleaks CLI
├── .gitleaks.toml            # Custom secret & filename detection rules
├── .gitignore                # Baseline ignore rules for secrets, logs, and DBs
├── LICENSE                   # MIT License
└── README.md                 # Template documentation
```

---

## 🔒 Defense-in-Depth Recommendation

CI workflows catch secrets after a push or pull request is opened. For stronger protection before commits leave your workstation, pair this repository template with a local **Gitleaks pre-commit hook** and a global `.gitignore_global` configuration.
