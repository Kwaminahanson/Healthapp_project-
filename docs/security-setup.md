# Repository Security Setup

## Overview
This document describes the defense-in-depth security approach implemented
across the HealthPulse repositories.

## Security Layers

| Layer | Type | Tool | Status |
|---|---|---|---|
| Layer 1 | Local Git Hooks | detect-secrets + custom script | ✅ Active |
| Layer 2 | CI Pipeline Scan | Gitleaks (Task F) | 🔲 Pending |
| Layer 3 | Branch Protection | GitHub Rulesets | ✅ Active |

---

## Layer 1: Local Git Hooks

### Pre-commit Hook
Scans staged files for secrets before every commit using `detect-secrets`.

**Blocks:**
- AWS Access Keys
- Private keys
- High entropy strings
- Secret keywords

**Install:**
```bash
pip3 install pre-commit
pre-commit install
pre-commit install --hook-type pre-push

#Test Blocked content 
echo "AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG" >> test.txt
git add test.txt
git commit -m "test secret"
# Result: BLOCKED by detect-secrets


###Pre-push Hook 
#warns when pushing directly to main or develop
git push origin main
# Result: WARNING shown, push cancelled
