# OpenIOM Skill Format Specification

**Version:** 1.0.0
**Last Updated:** 2026-02-17

This document defines the required format for all OpenIOM skills. Every skill in the library must follow this specification.

---

## Overview

An OpenIOM skill is a structured markdown file (`SKILL.md`) that describes a business operation in enough detail for an AI agent to understand and execute it. Skills are accompanied by a machine-readable metadata file (`metadata.yaml`) and optionally by locale overlays.

OpenIOM follows the [Agent Skills](https://agentskills.io) standard for the base file format. The `SKILL.md` uses YAML frontmatter followed by markdown content. OpenIOM extends the standard with additional frontmatter fields and content sections specific to operational skills.

---

## File Structure

Every skill lives in its own directory:

```
skill-name/
├── SKILL.md              # Required — the skill definition
├── metadata.yaml         # Required — machine-readable metadata
└── locales/              # Required — at least one locale overlay
    ├── UG.md
    ├── KE.md
    └── ...
```

The directory name must match the `name` field in the frontmatter (lowercase, hyphenated).

---

## SKILL.md Format

### Frontmatter (YAML)

The frontmatter provides machine-readable metadata at the top of the file:

```yaml
---
name: skill-name-here
description: >
  One to three sentences describing what this skill does and when to use it.
  Include keywords for discovery.
industry: industry-slug
sub-sector: sub-sector-slug
function: business-function
version: 1.0.0
authors:
  - name: Author Name
    url: https://example.com
supported_locales:
  - UG
  - KE
tags:
  - tag1
  - tag2
complexity: basic | intermediate | advanced
reference_framework:
  primary:
    name: Framework Name
    version: "Version"
    mapping: Specific mapping reference
  secondary:
    name: Secondary Framework Name
    mapping: Specific mapping reference
---
```

#### Required Frontmatter Fields

| Field | Type | Description | Constraints |
|-------|------|-------------|-------------|
| `name` | string | Skill identifier | Lowercase, hyphens only, max 64 chars, must match directory name |
| `description` | string | What the skill does and when to use it | Max 1024 chars |
| `industry` | string | Industry slug | Must match a directory in `skills/` |
| `sub-sector` | string | Sub-sector slug | Must match a directory under the industry |
| `function` | string | Business function (e.g., compliance, operations, finance) | Free text |
| `version` | string | Semantic version | Format: major.minor.patch |
| `authors` | array | List of authors with name and optional URL | At least one author |
| `supported_locales` | array | ISO 3166-1 alpha-2 country codes | At least one locale |
| `tags` | array | Discovery keywords | At least 2 tags |
| `complexity` | string | Skill complexity level | One of: basic, intermediate, advanced |
| `reference_framework` | object | Industry framework mapping | Must include at least `primary` with `name` and `mapping` |

---

### Content Sections

After the frontmatter, the skill body contains the following sections. Sections are marked as Required (must be present at launch), Recommended (should be added by v1.1), or Optional (nice to have).

#### Required Sections

##### 1. Purpose

What this skill does. 2-3 sentences.

```markdown
## Purpose

This skill enables an AI agent to [what it does] for [which context].
```

##### 2. When to Use

Bullet list of scenarios that trigger this skill.

```markdown
## When to Use

- Scenario 1
- Scenario 2
- Scenario 3
```

##### 3. Process Overview

Step-by-step operational logic. Each step should have a heading and bullet points describing actions.

```markdown
## Process Overview

### Step 1: Step Name
- Action 1
- Action 2

### Step 2: Step Name
- Action 1
- Action 2
```

##### 4. Required Inputs

Table of data the skill needs to execute.

```markdown
## Required Inputs

| Input | Type | Required | Notes |
|-------|------|----------|-------|
| field_name | type | Yes/No | Description |
```

##### 5. Outputs

Table of data the skill produces.

```markdown
## Outputs

| Output | Type | Description |
|--------|------|-------------|
| field_name | type | What it represents |
```

##### 6. Integration Points

Systems the skill connects to.

```markdown
## Integration Points

| System | Purpose | Direction |
|--------|---------|-----------|
| System name | What it's used for | Inbound/Outbound/Bidirectional |
```

##### 7. Dependencies & Handoffs

How this skill connects to other skills.

```markdown
## Dependencies & Handoffs

### Requires (inputs from other skills)

| Skill | Data Required | Mandatory |
|-------|--------------|-----------|
| skill-name | What data | Yes/No |

### Triggers (outputs to other skills)

| Condition | Triggers Skill | Data Passed |
|-----------|---------------|-------------|
| When X happens | target-skill | What data is passed |

### Workflow Position

[ASCII diagram showing where this skill sits in the workflow]
```

##### 8. Roles & Permissions

Who can do what.

```markdown
## Roles & Permissions

| Role | Permissions | Typical Title |
|------|------------|---------------|
| role_name | What they can do | Job title |

### Segregation of Duties

| Action | Cannot Be Performed By |
|--------|----------------------|
| action | restriction |
```

##### 9. Reporting

KPIs, data points, suggested reports, and alert triggers.

```markdown
## Reporting

### Key Performance Indicators

| KPI | Description | Data Source | Target | Frequency |
|-----|------------|-------------|--------|-----------|

### Data Points to Capture

| Data Point | Type | Captured At | Used In |
|-----------|------|-------------|---------|

### Suggested Reports

| Report | Frequency | Audience | Description |
|--------|-----------|----------|-------------|

### Alert Triggers

| Alert | Condition | Severity | Action |
|-------|-----------|----------|--------|
```

Minimum requirements: 3 KPIs, 5 data points, 2 suggested reports, 2 alert triggers.

##### 10. Error Handling

Failure scenarios and fallbacks.

```markdown
## Error Handling

### Failure Scenarios

| Scenario | Handling | Fallback | Severity |
|----------|---------|----------|----------|

### Critical Rules

1. Rule that must never be violated
2. Another critical rule
```

##### 11. Framework Alignment

How this skill maps to established industry frameworks. Required per the frameworks addendum.

```markdown
## Framework Alignment

### Primary Framework

- **Framework:** Framework Name (version)
- **Mapping:** Specific service domain, process area, or reference ID
- **Description:** How this skill aligns with the framework element

### Secondary Framework (if applicable)

- **Framework:** Secondary Framework Name
- **Mapping:** Specific reference
- **Description:** How this skill aligns

### Notes

Any caveats about the mapping (e.g., "preliminary mapping based on public documentation").
```

##### 12. Changelog

Version history.

```markdown
## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | YYYY-MM-DD | Initial release |
```

---

#### Recommended Sections (target: v1.1)

##### 13. Audit Requirements

What must be logged for compliance.

```markdown
## Audit Requirements

### Mandatory Audit Events

| Event | Data to Log | Triggered At | Immutable |
|-------|------------|--------------|-----------|

### Regulatory Retention Requirements

| Jurisdiction | Minimum Retention | Post-Relationship | Reference |
|-------------|-------------------|-------------------|-----------|

### Audit Trail Access

| Role | Access Level |
|------|-------------|
```

##### 14. Data Classification

Sensitivity tagging for all data points.

```markdown
## Data Classification

### Data Sensitivity Levels

| Data Point | Classification | Handling Requirements |
|-----------|---------------|---------------------|

### Classification Definitions

| Level | Description | Access |
|-------|------------|--------|
```

##### 15. Validation Scenarios

Test cases for implementation verification. Minimum 3 scenarios.

```markdown
## Validation Scenarios

| # | Scenario | Input Profile | Expected Outcome |
|---|----------|--------------|-----------------|
```

---

#### Optional Sections (target: v1.2)

##### 16. SLA Expectations

Target durations per step.

```markdown
## SLA Expectations

### Processing Time Targets

| Step | Target Duration | Maximum Duration | Notes |
|------|----------------|-----------------|-------|

### End-to-End Targets

| Scenario | Target | Maximum |
|----------|--------|---------|

### SLA Breach Handling

| Breach | Action |
|--------|--------|
```

---

## Versioning

Skills use [Semantic Versioning](https://semver.org/):

- **Patch (x.x.1):** Typo fixes, clarifications, minor accuracy corrections
- **Minor (x.1.0):** New locale overlays, additional validation scenarios, new KPIs
- **Major (1.0.0):** Process step changes, structural modifications, breaking changes to data contract

Platforms consuming skills should pin to a major version and review minor/patch updates before adopting.

---

## Style Guide

- Use clear, professional English
- Write in imperative mood for process steps ("Collect documents", not "Documents are collected")
- Use tables for structured data
- Use bullet lists for unstructured lists
- Use code blocks for data field names and system references
- Keep process steps actionable and specific
- Cite regulatory references with specific law names and section numbers
- Do not include platform-specific implementation details (no SQL, no Python, no dashboard layouts)
