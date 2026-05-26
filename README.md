# Cattle Vaccination Architecture Docs

Architecture diagrams for APHA's bovine tuberculosis (bTB) cattle vaccination and testing systems, modelled using [LikeC4](https://likec4.dev/).

## Viewing the diagrams

```bash
nvm use        # Node 26.x required
npm install    # first time only
npm run serve  # opens interactive diagram viewer at http://localhost:5173
```

## Diagrams

| # | View | Description |
|---|------|-------------|
| 0 | As Is | Current state — Sam/iSam on PEGA, LIMS, livestock movement systems |
| 1 | Minimal Vaccination Recording | Future: bTB vaccination records on Salesforce + public status checker on CDP |
| 2 | Test Viewing | Future: test visit, sample and incident records on Salesforce |
| 3 | Minimal SICCT Test Recording | Future: combined vaccination + SICCT test recording |

Each view also has a companion **Deployment** diagram showing which platform hosts each component.

## Structure

```
index.c4              # Element type and relationship specifications (shared vocabulary)
elements/
  actors.c4           # People: APHA staff, VDP vets/testers, public
  apha-existing.c4    # As-is APHA systems: Sam, iSam, LIMS
  apha-future-shared.c4  # Shared future components: Single View of Customer, Integration Bridge
  apha-future-vax.c4  # Future vaccination components
  apha-future-test.c4 # Future testing components
  epi.c4              # Epidemiological data context (cattleTbData, RADAR)
  livestock.c4        # External livestock movement systems (CTS, ScotEID)
  platforms.c4        # Deployment platform definitions
views/
  0-as-is.c4
  1-vax-minimal.c4
  2-test-viewer.c4
  3-sicct-minimal.c4
```

## Domain glossary

| Term | Meaning |
|------|---------|
| bTB | Bovine tuberculosis |
| SICCT | Single Intradermal Comparative Cervical Tuberculin — the skin test used to detect bTB in cattle |
| APHA | Animal and Plant Health Agency |
| VDP | Veterinary Delivery Partnership — private vets contracted to deliver APHA services |
| OV | Official Veterinarian |
| ATT | Approved Tuberculosis Tester |
| Sam / iSam | APHA's PEGA-based disease and customer management system; iSam is the limited external-facing view |
| LIMS | Laboratory Information Management System |
| CTS | Cattle Tracing System — livestock movement system for England and Wales |
| ScotEID | Scottish livestock movement system |
| CDP | APHA's Customer Data Platform |
| DSG | Data Science Group platform, hosting epidemiological datasets (cattleTbData, RADAR) |
| SVoC | Single View of Customer |
