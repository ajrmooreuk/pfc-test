# PFC-TEST — PF-Core Staging

PF-Core **test** tier — validated PFC assets, integration tested before production release.

| Field | Value |
|---|---|
| **Tier** | test (team mode — 1 review required) |
| **Triad** | [pfc-dev](https://github.com/ajrmooreuk/pfc-dev) · [pfc-test](https://github.com/ajrmooreuk/pfc-test) · [pfc-prod](https://github.com/ajrmooreuk/pfc-prod) |
| **Architecture** | Hub-and-Spoke (ARCH-CICD-001) |
| **Epic** | [Epic 58 (#837)](https://github.com/ajrmooreuk/Azlan-EA-AAA/issues/837) |

## Validation Gate (5 Checks)

| Check | What | Threshold |
|---|---|---|
| Vitest | Ontology Visualiser test suite | 2081 tests pass |
| Registry Lint | ont-registry-index.json structure | ≥40 ontologies |
| OAA Validate | All OAA v6/v7 ontology files valid JSON | ≥30 files |
| Skeleton Validate | App skeleton JSONLD structure | Valid JSON |
| EMC Compose | Category composition check | ≥8 categories |

## Promotion

```bash
# Promote from pfc-test → pfc-prod (requires SME approval)
gh workflow run promote.yml --repo ajrmooreuk/pfc-test -f direction=test-to-prod -f bump=minor
```
