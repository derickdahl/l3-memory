# Asana Integration Config

## Connection
- **User:** Derick Dahl (derickd@sonance.com)
- **Workspace:** sonance.com
- **Workspace GID:** 1201171894258423
- **Derick User GID:** 1202113197057207

## Key Projects
| Project | GID |
|---------|-----|
| Derick - Private | 1202127678978097 |
| Dashboard - Technology & Innovation | 1211377592740891 |
| ACTIVE BMT PROJECTS | 1205827966484333 |
| ACTIVE LUX RESI PROJECTS | 1205889896688896 |
| HUB | 1211762584253887 |

## Custom Fields (Executive OS Metrics)
| Field | GID | Type |
|-------|-----|------|
| Estimated Hours | 1213024019947593 | number |
| Actual Hours | 1212985786510254 | number |
| Completed By | 1213024025259682 | enum (Derick/L3/Derick + L3/Other) |
| Work Theme | 1213024021736217 | enum (Strategic/Operational/Creative/Administrative/Research/Communication) |
| Dept | 1209274176557554 | multi_enum (existing) |

## Token
Stored in: ~/.clawdbot/credentials/asana-token (not in git)

## API Reference
- Base URL: https://app.asana.com/api/1.0
- Auth: Bearer token in Authorization header
- Docs: https://developers.asana.com/docs
