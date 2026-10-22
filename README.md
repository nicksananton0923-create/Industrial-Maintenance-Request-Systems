# Industrial Electrical Maintenance and Breakdown Analysis

## Table of Contents
1. [Project Purpose](#1-project-purpose)
2. [Problem Statement](#2-problem-statement)
3. [Project Objectives](#3-project-objectives)
4. [Current Project Status](#4-current-project-status)
5. [Confirmed Technologies and Components](#5-confirmed-technologies-and-components)
6. [Proposed Components](#6-proposed-components)
7. [System Operation](#7-system-operation)
8. [Architecture or Workflow](#8-architecture-or-workflow)
9. [Installation or Setup Instructions](#9-installation-or-setup-instructions)
10. [Testing Status](#10-testing-status)
11. [Safety Considerations](#11-safety-considerations)
12. [Known Limitations](#12-known-limitations)
13. [Future Improvements](#13-future-improvements)
14. [Repository Structure](#14-repository-structure)
15. [Licence Information](#15-licence-information)
16. [Status Label Convention](#16-status-label-convention)

## 1. Project Purpose

This project provides a documentation framework for industrial electrical maintenance and breakdown analysis. The framework covers asset registration for electrical equipment (switchgear, transformers, motors, drives, panels), preventive maintenance schedules, breakdown records, root cause analysis, and reliability metrics. The package includes CSV templates, a fictional sample dataset, and procedural documentation aligned with IEC 60364 (electrical installations) and IEC 62305 (lightning protection).

## 2. Problem Statement

Industrial electrical equipment is critical to plant operation, and unplanned breakdowns can cause significant production loss. Effective maintenance documentation is required to track PM completion, analyse breakdown patterns, identify recurring root causes, and demonstrate regulatory compliance. Without a consistent documentation framework, the data needed for these analyses is scattered and incomplete.

## 3. Project Objectives

- Provide CSV templates for industrial electrical asset registration.
- Provide PM schedule and inspection checklist templates.
- Provide breakdown record and root cause analysis templates.
- Provide reliability metric calculation templates (MTBF, MTTR, availability).
- Provide procedural documentation aligned with IEC 60364 / 62305.
- Clearly label all data as FICTIONAL.

## 4. Current Project Status

| Item | Status |
|---|---|
| CSV templates | IMPLEMENTED |
| Sample dataset (fictional) | IMPLEMENTED |
| Procedural documentation | IMPLEMENTED |
| Deployment in a real plant | NOT VERIFIED |

## 5. Confirmed Technologies and Components

CSV data format, Markdown documentation, IEC 60364 / 62305 references.

## 6. Proposed Components

| Component | Role | Notes |
|---|---|---|
| CSV editor | Template population | Any |
| CMMS (optional) | Production deployment | e.g. Maximo, SAP PM |
| Insulation tester (Megger) | Insulation resistance tests | Required for PM |
| IR camera | Thermographic inspection | Required for PM |
| Power quality analyser | Power quality measurement | Optional |

## 7. System Operation

The framework operates as a set of interlinked CSV files with the electrical asset register at the centre. Each asset (switchgear, transformer, motor, drive, panel) has a unique ID that links to its PM schedule, inspection checklist, breakdown records, and root cause analysis. Reliability metrics are computed from the breakdown records and the asset's operating hours.

## 8. Architecture or Workflow

Star schema with the electrical asset register at the centre, linked by `asset_id`.

```
            [pm-schedule.csv]               [inspection-checklist.csv]
                    \                          /
                     \                        /
                      v                       v
                      [asset-register.csv]
                      ^                ^
                      |                |
        [breakdown-record.csv]    [root-cause-analysis.csv]
```


## 9. Installation or Setup Instructions

1. Copy templates from `templates/` to a working directory.
2. Populate `asset-register.csv` with the plant's electrical assets.
3. For each asset, populate the PM schedule and inspection checklist.
4. Record breakdowns in `breakdown-record.csv` and perform root cause analysis.
5. Periodically compute reliability metrics from the breakdown records.

## 10. Testing Status

Tests performed on the fictional sample dataset:

1. CSV schema validation — TESTED — passes.
2. Cross-file referential integrity — TESTED — passes.
3. Reliability metric calculation — TESTED.
4. Real plant deployment — NOT YET TESTED.

## 11. Safety Considerations

Industrial electrical maintenance involves high-voltage and high-current equipment. The following safety considerations are mandatory:

- **Lockout-tagout (LOTO)** is mandatory for any electrical work. The site's LOTO procedure must be followed strictly.
- **Live working** is generally prohibited. Work on energised equipment requires a specific permit and specialised PPE (arc-rated suit, insulated gloves, face shield).
- **Arc flash analysis** should be performed for switchgear above 240 V. The analysis determines the incident energy at the working distance and the required PPE category.
- **Insulation testing** (Megger) requires the equipment to be isolated and discharged before and after the test.
- **Thermographic inspection** is typically performed under load (energised). Use a qualified thermographer with appropriate PPE.
- **Earth fault loop impedance** testing requires the equipment to be energised; follow the test instrument manufacturer's safety instructions.
- **Confined space entry** may be required for transformer inspection; follow the site's CSE procedure.

This framework is documentation only. All electrical work must be performed by a qualified electrician.

## 12. Known Limitations

- Documentation only; does not perform inspections.
- No CMMS integration.
- No arc flash analysis (requires a separate study).
- No power quality monitoring (covered separately in Project 17).
- Reliability metrics are indicative, not predictive.
- Local regulations may require additional record types.

## 13. Future Improvements

- Add equipment-class-specific inspection checklists (switchgear, transformers, motors, drives, panels, UPS).
- Add an arc flash analysis template per IEEE 1584.
- Add a CMMS migration guide.
- Add a Python script for reliability metric calculation.
- Add a power quality monitoring integration.

## 14. Repository Structure

```
16-industrial-electrical-maintenance/
├── README.md
├── LICENSE
├── docs/
│   ├── project-overview.md
│   ├── requirements.md
│   ├── system-architecture.md
│   ├── logic-and-operation.md
│   ├── components-and-bill-of-materials.md
│   ├── testing-and-validation.md
│   ├── safety-considerations.md
│   ├── development-roadmap.md
│   └── limitations.md
├── templates/
│   ├── asset-register.csv
│   ├── pm-schedule.csv
│   ├── inspection-checklist.csv
│   ├── breakdown-record.csv
│   └── root-cause-analysis.csv
├── data/
│   ├── sample-asset-register.csv
│   └── sample-breakdown-records.csv
└── procedures/
    ├── pm-methodology.md
    └── reliability-metrics.md
```

## 15. Licence Information

Released under the MIT Licence. See the `LICENSE` file for the full text.

## 16. Status Label Convention

This project uses the following status labels throughout its documentation. Each label has a strict meaning and is not used interchangeably with any other label.

| Label | Meaning |
|---|---|
| **CONFIRMED** | Directly supported by available project information or inspected source code. |
| **PROPOSED** | A suggested design or implementation. Has not been verified against built hardware. |
| **NOT VERIFIED** | Information that has not been confirmed. Requires verification before use. |
| **IMPLEMENTED** | A feature or system that has actually been created and exists in the source code. |
| **TESTED** | A test that has genuinely been performed with recorded results. |
| **NOT YET TESTED** | Code, hardware, or functionality that still requires testing. |

If a section does not carry any status label, the content of that section is informational prose and does not make a claim of verification, testing, or implementation.

## Data and Confidentiality Notice

All sample data in this repository is **FICTIONAL**. Plant names use generic identifiers such as "Plant A", "Building 3", "Line 2", or "Western Plant". No real employer name, real equipment serial number, real employee name, real maintenance record, or any other confidential information is included. Templates are provided as reusable CSV schemas that can be populated with real site data by the adopting organisation. The fictional data is intended solely to demonstrate the template structure and calculation methodology.
