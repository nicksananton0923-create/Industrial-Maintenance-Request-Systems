# System Architecture — Industrial Electrical Maintenance and Breakdown Analysis

## Data Model

Star schema with the electrical asset register at the centre.

### Master file
- `asset-register.csv`

### Transaction files
- `pm-schedule.csv`
- `inspection-checklist.csv`
- `breakdown-record.csv`
- `root-cause-analysis.csv`

## Standards Alignment

- IEC 60364 (Electrical installations of buildings)
- IEC 60364-6 (Verification)
- IEC 62305 (Lightning protection)
- IEEE 1584 (Arc flash hazard analysis)
