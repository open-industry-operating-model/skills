# OpenIOM — The Open Industry Operating Model

**AI agent skills for how businesses actually operate.**

OpenIOM is an open-source library of AI agent skills for business operations — organized by industry, business function, and locale. Every skill encodes deep domain expertise into a structured, machine-readable definition that any AI platform can consume.

OpenIOM is not a new standard. It follows the [Agent Skills](https://agentskills.io) format and works with Claude, GPT, Gemini, and any platform that supports agent skills. What makes OpenIOM different is the **content**: real-world operational knowledge covering processes, compliance, reporting, error handling, roles, audit requirements, and inter-skill dependencies — with hyperlocal detail for specific countries and regions.

**Core principle: Global standard, hyperlocal execution.**

Every skill has a universal base layer (how the process works anywhere) and locale overlays (how it works specifically in Uganda, Kenya, Indonesia, etc.).

---

## Why OpenIOM Exists

AI platforms are powerful general-purpose tools, but they lack structured operational knowledge. They understand "KYC" as a concept but don't know:

- What KYC specifically requires in Uganda vs. Kenya vs. Indonesia
- Which documents are accepted by the Bank of Uganda vs. the Central Bank of Kenya
- How mobile money KYC differs from traditional banking KYC
- What KPIs define a healthy KYC operation
- Who has authority to approve high-risk applications
- What must be logged for audit and compliance

This knowledge exists in the heads of domain experts and scattered internal documents. OpenIOM codifies it into structured, open, machine-readable skills.

---

## Quick Start

### Use a skill with your AI agent

Every skill is a self-contained markdown file that an AI agent can read and follow. Point your agent at any `SKILL.md` file:

```
skills/financial-services/commercial-banking/kyc-customer-onboarding/SKILL.md
```

For country-specific context, also load the locale overlay:

```
skills/financial-services/commercial-banking/kyc-customer-onboarding/locales/UG.md
```

And the country reference:

```
locales/UG/LOCALE_INFO.md
```

The agent now has deep operational knowledge of how KYC works in Ugandan commercial banking — including regulatory requirements, accepted documents, verification systems, risk factors, reporting obligations, and error handling.

### Browse available skills

See [industries/TAXONOMY.md](industries/TAXONOMY.md) for the full list of industries and skills.

### Contribute

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add skills, locale overlays, or corrections.

---

## What's in a Skill

Each OpenIOM skill goes far beyond simple process steps. A complete skill includes:

| Section | What It Covers |
|---------|---------------|
| Purpose & When to Use | What the skill does and when to invoke it |
| Process Steps | The core operational logic |
| Required Inputs & Outputs | Data contract |
| Integration Points | Systems it connects to |
| Dependencies & Handoffs | Upstream and downstream skills |
| Roles & Permissions | Who can do what, segregation of duties |
| Reporting | KPIs, data points, suggested reports, alert triggers |
| Error Handling | Failure scenarios, fallbacks, critical rules |
| Framework Alignment | Mapping to industry standards (BIAN, eTOM, SCOR, etc.) |
| Audit Requirements | What to log, retention periods |
| Data Classification | Sensitivity tagging for data points |
| Validation Scenarios | Test cases for implementation verification |
| SLA Expectations | Target durations per step |

---

## Repository Structure

```
open-iom/skills
├── README.md
├── LICENSE                          # Apache 2.0 (skills, schemas, spec)
├── LICENSE-LOCALES                  # CC BY-SA 4.0 (locale overlays)
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── GOVERNANCE.md
│
├── spec/                            # Format specifications
│   ├── SKILL_FORMAT.md
│   ├── LOCALE_FORMAT.md
│   └── METADATA_SCHEMA.yaml
│
├── template/                        # Templates for new skills
│   ├── skill-template/
│   │   ├── SKILL.md
│   │   ├── metadata.yaml
│   │   └── locales/
│   │       └── LOCALE_TEMPLATE.md
│   └── README.md
│
├── industries/                      # Industry taxonomy and frameworks
│   ├── TAXONOMY.md
│   └── FRAMEWORKS.md
│
├── skills/                          # The skills library
│   ├── financial-services/
│   │   ├── commercial-banking/
│   │   │   ├── kyc-customer-onboarding/
│   │   │   │   ├── SKILL.md
│   │   │   │   ├── metadata.yaml
│   │   │   │   └── locales/
│   │   │   │       └── UG.md
│   │   │   └── ...
│   │   ├── mobile-money/
│   │   └── microfinance/
│   ├── telecommunications/
│   ├── fmcg-retail/
│   └── hospitality/
│
└── locales/                         # Country-level reference data
    ├── UG/
    │   └── LOCALE_INFO.md
    ├── KE/
    │   └── LOCALE_INFO.md
    └── TZ/
        └── LOCALE_INFO.md
```

---

## Industries Covered

| Industry | Sub-sectors | Status |
|----------|------------|--------|
| Financial Services | Commercial Banking, Mobile Money, Microfinance | Active |
| Telecommunications | Network Operations, Revenue Assurance, Customer Service | Active |
| FMCG / Retail | Inventory, Distribution, Sales | Active |
| Hospitality | Restaurants, Hotels | Active |

See [industries/TAXONOMY.md](industries/TAXONOMY.md) for the full taxonomy and [industries/FRAMEWORKS.md](industries/FRAMEWORKS.md) for industry framework mappings.

---

## Locales

| Code | Country | Status |
|------|---------|--------|
| UG | Uganda | Available |
| KE | Kenya | In progress |
| TZ | Tanzania | In progress |

---

## Framework Alignment

OpenIOM does not invent new operating models. Every skill maps to established industry frameworks where they exist:

| Industry | Primary Framework |
|----------|------------------|
| Banking / Financial Services | BIAN (Banking Industry Architecture Network) |
| Telecommunications | eTOM / TM Forum Frameworx |
| Supply Chain / FMCG | SCOR DS (ASCM) |
| Healthcare | HL7 FHIR |
| Industries without frameworks | APQC Cross-Industry PCF |

See [industries/FRAMEWORKS.md](industries/FRAMEWORKS.md) for the complete framework reference table.

---

## Relationship to Tyms

OpenIOM is an open-source project founded and maintained by [Tyms](https://tyms.com) (Intelligent Tyms Inc.). The skills are free for anyone to use on any platform.

**Tyms** is the commercial platform that orchestrates OpenIOM skills into coordinated AI-powered operations — handling multi-agent coordination, enterprise integrations (Flexcube, T24, Finacle), implemented dashboards and reports, configured alerts and audit trails, and client-specific customization.

**Analogy:** OpenIOM skills are like Docker images (free, open, portable). Tyms is like managed Kubernetes (the commercial platform that orchestrates them at scale).

---

## License

- **Skills, schemas, and specifications:** [Apache 2.0](LICENSE)
- **Locale overlays:** [CC BY-SA 4.0](LICENSE-LOCALES)

---

## Contributing

We welcome contributions from domain experts, consultants, developers, and industry practitioners. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide.

The easiest way to start: **add a locale overlay for your country** to an existing skill. This takes domain knowledge, not code.

---

## Governance

OpenIOM is currently maintained by Tyms under a BDFL (Benevolent Dictator for Life) model, with plans to transition to a steering committee as the community grows. See [GOVERNANCE.md](GOVERNANCE.md) for details.
