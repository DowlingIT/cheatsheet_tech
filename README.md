# Tech Cheat Sheets

Concise, printable cheatsheet pages for common developer tools and frameworks — boxed card layout, organized by task.

**[View the cheat sheets](https://DowlingIT.github.io/cheatsheet_tech/)**

## Topics covered

- **JavaScript** — JavaScript Core, Browser JS, Node.js, Express, Electron, TypeScript, React, NextJS, jQuery
- **Containers & K8s** — Docker, Compose, Swarm, Kubernetes, Helm, Kustomize
- **PHP** — PHP Core, Laravel, Livewire, Filament
- **Python** — Python Core, Django, FastAPI
- **Go** — Go Core
- **SQL** — SQL DML, SQL DDL, T-SQL, PostgreSQL, MySQL, SQLite
- **DevOps** — Git, GitHub, Bitbucket, GitLab
- **Editors** — Nano, Vim, VS Code

## Built with

- [Jekyll](https://jekyllrb.com/) + [GitHub Pages](https://pages.github.com/)
- [Mermaid](https://mermaid.js.org/) for diagrams
- CSS Grid for the boxed layout
- `@media print` styles for PDF export (File → Print → Save as PDF)

## Local development

**Prerequisites:** [Ruby](https://www.ruby-lang.org/en/downloads/) + Bundler (`gem install bundler`). On Windows use [RubyInstaller](https://rubyinstaller.org/) with DevKit.

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000/cheatsheet_tech/`.

## License

MIT
