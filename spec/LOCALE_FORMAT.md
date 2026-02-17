# OpenIOM Locale Overlay Format Specification

**Version:** 1.0.0
**Last Updated:** 2026-02-17

This document defines the format for locale overlays — country-specific content that extends a base skill with local regulatory, operational, and cultural context.

---

## Overview

The locale system operates at two levels:

1. **Country Reference Data** (`locales/{CODE}/LOCALE_INFO.md`) — shared reference information about a country that applies across all skills
2. **Skill-Specific Locale Overlays** (`skills/{path}/locales/{CODE}.md`) — country-specific instructions that modify or extend a specific base skill

Both use ISO 3166-1 alpha-2 country codes (UG, KE, TZ, NG, etc.).

---

## How Locale Resolution Works

When a platform loads a skill for a specific locale:

1. Load the base `SKILL.md` (universal process)
2. Load the country's `LOCALE_INFO.md` (general country context)
3. Load the skill's locale overlay (e.g., `locales/UG.md`) if it exists
4. Merge: base + country context + skill-specific overlay = complete localized skill

If no locale overlay exists for a country, the base skill is used as-is with general country context.

---

## Merge Semantics

The merge follows these rules:

| Situation | Behavior |
|-----------|----------|
| Locale overlay has a section that exists in the base skill | Locale version **REPLACES** the base section entirely |
| Locale overlay has a section not in the base skill | Section is **ADDED** |
| Base skill has a section with no locale equivalent | Base version is **used as-is** |
| Country LOCALE_INFO.md | Attached as **supplementary context**, not merged into skill sections |

There is no partial merge within a section. If a locale overlay provides a "Risk Factors" section, it replaces the entire base "Risk Factors" section — it does not append to it.

---

## Country Reference Data (LOCALE_INFO.md)

### Location

```
locales/
├── UG/
│   └── LOCALE_INFO.md
├── KE/
│   └── LOCALE_INFO.md
└── TZ/
    └── LOCALE_INFO.md
```

### Format

```markdown
---
locale: UG
country: Uganda
last_updated: 2026-02-17
authors:
  - name: Author Name
    url: https://example.com
---

# Uganda — Country Reference

## Regulatory Bodies
[List of regulatory authorities with jurisdiction]

## National Identity Systems
[ID types, issuing authorities, verification APIs]

## Tax Authority
[Tax body, TIN system, key tax types]

## Data Protection
[Data protection law, authority, key requirements]

## Financial Infrastructure
[Payment systems, mobile money, banking infrastructure]

## Common Enterprise Technology
[Core banking systems, ERP systems, telecom platforms in use]

## Language & Culture
[Business languages, regional languages, cultural considerations]

## Currency
[Currency, exchange considerations]

## Key Industry Associations
[Relevant industry bodies]
```

### Content Guidelines

- This is reference data, not operational instructions
- Information should be stable (changes infrequently)
- Useful across many skills, not specific to one
- Must include sources/references for regulatory information
- Must include `last_updated` date

---

## Skill-Specific Locale Overlay

### Location

```
skills/financial-services/commercial-banking/kyc-customer-onboarding/
└── locales/
    ├── UG.md
    ├── KE.md
    └── TZ.md
```

### Frontmatter

```yaml
---
locale: UG
country: Uganda
skill: kyc-customer-onboarding
version: 1.0.0
regulator: Bank of Uganda (BoU)
last_updated: 2026-02-17
legal_framework:
  - Law Name and Year
  - Another Law
  - Regulatory Guidelines
authors:
  - name: Author Name
    url: https://example.com
---
```

#### Required Frontmatter Fields

| Field | Type | Description |
|-------|------|-------------|
| `locale` | string | ISO 3166-1 alpha-2 country code |
| `country` | string | Full country name |
| `skill` | string | Name of the base skill this overlay extends |
| `version` | string | Version of the locale overlay |
| `regulator` | string | Primary regulatory authority for this skill in this country |
| `last_updated` | date | Date this overlay was last verified/updated |
| `legal_framework` | array | List of relevant laws and regulations |
| `authors` | array | List of authors |

### What Locale Overlays Can Extend

A locale overlay can add country-specific content to any section of the base skill:

| Base Skill Section | Locale Extension |
|-------------------|-----------------|
| Process Steps | Additional steps required by local regulation |
| Required Inputs | Local document types, ID systems |
| Integration Points | Local systems and APIs |
| Roles & Permissions | Local regulatory role requirements |
| Reporting | Local regulatory reports, local thresholds |
| Error Handling | Locale-specific failure scenarios |
| Audit Requirements | Local retention periods, local reporting obligations |
| Data Classification | Local data protection law requirements |
| SLA Expectations | Local regulatory response time requirements |
| Validation Scenarios | Locale-specific edge cases |

### Content Structure

The locale overlay body should be organized by topic, not necessarily mirroring the base skill sections. Common sections include:

```markdown
# {Country} — {Skill Name}

## Regulatory Authority
[Primary regulator, oversight body]

## Accepted Identity Documents
[Tables of accepted documents by customer type]

## Verification Systems
[Local APIs and verification services]

## {Country}-Specific Risk Factors
[Risk factors unique to this locale]

## {Country}-Specific Reporting Requirements
[Local regulatory reports, thresholds, recipients]

## {Country}-Specific Audit Retention
[Local retention periods with legal references]

## Data Protection ({Country})
[Local data protection requirements]

## Tax Compliance Integration
[Local tax requirements relevant to this skill]

## Language Considerations
[Business language, regional language needs]

## Common Systems in {Country}
[Technology platforms commonly used in this market]

## {Country}-Specific Validation Scenarios
[Edge cases unique to this locale]
```

---

## Quality Requirements for Locale Overlays

All locale overlays must:

1. Cite specific laws, regulations, or guidelines by name and section number
2. Include a `last_updated` date in the frontmatter
3. Include the `legal_framework` field listing all relevant legislation
4. Be reviewed by someone with in-country domain expertise before merge
5. Not contain proprietary or confidential information
6. Not contain personally identifiable information (PII)
7. Use clear, professional English (even if the country's business language differs)

---

## Contribution Guidelines for Locales

Locale overlays are the primary mechanism for community contribution. A contributor in Nigeria can add `NG.md` overlays without touching the base skills or other locales.

See [CONTRIBUTING.md](../CONTRIBUTING.md) for the full contribution guide and the difficulty ladder.
