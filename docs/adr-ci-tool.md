# ADR: Why We Chose Jenkins

**Status:** Accepted
**Date:** 2026-04-12
**Deciders:** DevOps Team

## Context
We needed a CI/CD tool to automate builds, tests and deployments across
Dev, UAT, QA, and Prod environments. The team evaluated three options:
Jenkins, GitLab CI, and Azure DevOps.

## Options Considered

| Tool | Pros | Cons |
|---|---|---|
| Jenkins | Self-hosted, full control, large plugin ecosystem | Requires maintenance overhead |
| GitLab CI | Tight Git integration, built-in registry | Tied to GitLab platform |
| Azure DevOps | Enterprise support, Azure native | Cost, vendor lock-in |

## Decision
**Jenkins** — chosen because the team requires self-hosted infrastructure
with no external SaaS dependency, and the plugin ecosystem covers all
current pipeline requirements.

## Consequences
- Team must maintain Jenkins server and updates
- Jenkins pipelines expressed as `Jenkinsfile` in each repo
- Shared libraries will be used to reduce duplication across pipelines
- All pipeline configs are version controlled in Git

## Review Date
This decision will be reviewed after 6 months or if requirements change
significantly.