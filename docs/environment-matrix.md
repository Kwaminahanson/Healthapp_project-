# Environment Matrix

## Overview

| Environment | Purpose | Branch | URL | Auto-Deploy |
|---|---|---|---|---|
| Dev | Active development | `develop` | dev.internal.company.com | ✅ Yes |
| QA | Automated test execution | `release/*` | qa.internal.company.com | ✅ Yes |
| UAT | Business/user acceptance | `release/*` | uat.internal.company.com | 🔲 Manual |
| Prod | Live production traffic | `main` | app.company.com | 🔲 Manual |

## Promotion Flow
## Environment Details

### Dev
- Debug logging enabled
- No real PII data
- Developers push freely
- Auto-deploys on every commit to `develop`

### QA
- Automated test suites run on every deploy
- Mirrors prod configuration
- QA Engineer owns this environment
- Auto-deploys on every commit to `release/*`

### UAT
- Anonymized production-like data
- Stakeholder and business user access
- Requires QA sign-off before promotion
- Manual deployment approval required

### Prod
- Live customer traffic
- All logs forwarded to SIEM
- Access restricted to Release Manager and Lead
- Requires UAT sign-off and change approval

## Configuration Notes
| Setting | Dev | QA | UAT | Prod |
|---|---|---|---|---|
| Debug Logging | ✅ On | ✅ On | ❌ Off | ❌ Off |
| Real PII Data | ❌ No | ❌ No | ⚠️ Anonymized | ✅ Yes |
| Auto Deploy | ✅ Yes | ✅ Yes | ❌ No | ❌ No |
| Approval Required | ❌ No | ❌ No | ✅ Yes | ✅ Yes |