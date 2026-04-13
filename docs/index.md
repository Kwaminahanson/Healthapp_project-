# HealthApp Project Docs

Welcome to the central documentation hub for my DevOps deployment pipeline project.

## About This Site
This documentation follows the **docs-as-code** approach.
All pages are Markdown files versioned in Git alongside the deployment repo.
Any changes pushed to the `docs/` folder automatically trigger a new build via CI.

## Quick Links
- [Team Roster & Roles](team-roster.md)
- [ADR: CI Tool Selection](adr-ci-tool.md)
- [Environment Matrix](environment-matrix.md)
- [Runbook Template](runbook-template.md)

## Tech Stack
| Tool | Purpose |
|---|---|
| MkDocs + Material | Documentation site generator |
| Docker | Build and serve the docs site |
| Nginx | Production web server |
| GitHub Actions | CI pipeline - auto build on push |
| AWS EC2 | Hosting the docs site |