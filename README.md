# OpenIOM — The Open Industry Operating Model

**AI agent skills for how businesses actually operate.**

## Table of Contents

- [Introduction](#introduction)
- [Industries & Locales](#industries--locales)
- [Skills Reference](#skills-reference)
- [How to Use OpenIOM](#how-to-use-openiom)
- [Contributing](#contributing)
- [License](#license)
- [Governance](#governance)

---

## Introduction

Business success comes down to operations. OpenIOM is an open-source library of AI skills that encode how business operations actually work, organized by industry, function, and country. Each skill is a structured, detailed definition of a business process that any AI platform can consume. OpenIOM follows the [Agent Skills](https://agentskills.io) format and works with Claude, GPT, Gemini, and any platform that supports agent skills.

Every skill maps to established industry standards: [BIAN](https://bian.org/) for banking, [eTOM](https://www.tmforum.org/) for telecoms, [SCOR](https://www.ascm.org/) for supply chain, [HL7 FHIR](https://www.hl7.org/fhir/) for healthcare, and [APQC PCF](https://www.apqc.org/process-frameworks) across industries. What OpenIOM adds is the execution detail: process steps, compliance requirements, roles, error handling, KPIs, and audit trails, with hyperlocal overlays for specific countries and regions.

Because operations are always local, every skill supports locale overlays. KYC requirements differ between countries. Tax compliance varies by jurisdiction. Payment systems, accepted documents, and reporting obligations all depend on where you operate. The global standard defines the process. The locale overlay defines how it works in your market.

---

## Industries & Locales

### Industries

| Industry | Sub-sectors | Status |
|----------|------------|--------|
| Financial Services | Commercial Banking, Mobile Money, Microfinance | Active |
| Telecommunications | Network Operations, Revenue Assurance, Customer Service | Active |
| FMCG / Retail | Inventory, Distribution, Sales | Active |
| Hospitality | Restaurants, Hotels | Active |

→ Full catalog: [industries/TAXONOMY.md](industries/TAXONOMY.md) · Framework mappings: [industries/FRAMEWORKS.md](industries/FRAMEWORKS.md)

### Country Locales

| Code | Country | Status |
|------|---------|--------|
| UG | Uganda | Available |
| KE | Kenya | In progress |
| TZ | Tanzania | In progress |

The framework supports any country. Contributions welcome.

---

## Skills Reference

Each skill is a structured document (not code) that covers everything an operator or AI agent needs to execute a process properly. Skills are organized into four layers:

**The Work:** what gets done. Purpose and triggers, process steps, required inputs and outputs, SLA expectations.

**The Rules:** what governs it. Roles and permissions, error handling and fallbacks, audit requirements, data classification.

**The Connections:** what it touches. Integration points, upstream and downstream dependencies, framework alignment (BIAN, eTOM, SCOR, etc.).

**The Measurement:** how you know it's working. KPIs and reporting, alert triggers, validation scenarios.

→ Full format specification: [spec/SKILL_FORMAT.md](spec/SKILL_FORMAT.md) · Templates: [template/](template/)

---

## How to Use OpenIOM

### For AI Engineers & Developers

Point your AI agent at any skill file. Each skill is self-contained:

```
skills/financial-services/commercial-banking/kyc-customer-onboarding/SKILL.md
```

For country-specific detail, load the locale overlay alongside it:

```
skills/financial-services/commercial-banking/kyc-customer-onboarding/locales/UG.md
```

And optionally the country-level reference:

```
locales/UG/LOCALE_INFO.md
```

Your agent now understands how KYC works in that specific market: the regulations, the accepted documents, the verification systems, the risk factors, and the edge cases.

### For Operations & Domain Experts

Skills are written in Markdown, a simple text format. If you can write an SOP or a process manual, you can read and improve a skill. You don't need to write code.

The easiest way to start: pick an existing skill and write the locale overlay for your country. You know what these processes look like in your organization and your jurisdiction. That knowledge is exactly what this project needs.

---

## Contributing

We welcome contributions from operations managers, compliance officers, domain consultants, industry practitioners, and developers.

→ See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide.

### Why Open Source

Operational knowledge shouldn't be locked inside proprietary platforms. When a compliance officer improves a KYC skill based on a new regulatory directive, every organization using that skill benefits. When an ops manager adds a new country locale for revenue assurance, the entire industry moves forward.

The more practitioners who contribute, the better the library gets for everyone.

---

## License

- **Skills, schemas, and specifications:** [Apache 2.0](LICENSE)
- **Locale overlays:** [CC BY-SA 4.0](LICENSE-LOCALES), ensuring country-specific knowledge stays open

---

## Governance

OpenIOM is maintained under a BDFL model, with plans to transition to a steering committee as the community grows. See [GOVERNANCE.md](GOVERNANCE.md) for details.
