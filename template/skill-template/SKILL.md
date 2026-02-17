---
name: skill-name-here
description: >
  What this skill does and when to use it. 1-3 sentences.
  Include keywords for discovery.
industry: industry-slug
sub-sector: sub-sector-slug
function: business-function
version: 1.0.0
authors:
  - name: Your Name
    url: https://example.com
supported_locales:
  - XX
tags:
  - tag1
  - tag2
  - tag3
complexity: basic | intermediate | advanced
reference_framework:
  primary:
    name: "Framework Name (e.g., BIAN, eTOM, SCOR)"
    version: "Version number"
    mapping: "Specific service domain or process area"
  secondary:
    name: "Secondary framework (e.g., APQC PCF)"
    mapping: "Specific process ID"
---

# Skill Title

## Purpose

This skill enables an AI agent to [what it does] for [which context/industry].

## When to Use

- Scenario 1
- Scenario 2
- Scenario 3

## Process Overview

### Step 1: Step Name

- Action description
- Action description

### Step 2: Step Name

- Action description
- Action description

### Step 3: Step Name

- Action description
- Action description

## Required Inputs

| Input | Type | Required | Notes |
|-------|------|----------|-------|
| field_name | string/date/enum/object/file[] | Yes/No | Description |

## Outputs

| Output | Type | Description |
|--------|------|-------------|
| field_name | type | What it represents |

## Integration Points

| System | Purpose | Direction |
|--------|---------|-----------|
| System name | What it's used for | Inbound / Outbound / Bidirectional |

---

## Dependencies & Handoffs

### Requires (inputs from other skills)

| Skill | Data Required | Mandatory |
|-------|--------------|-----------|
| skill-name or "None (entry point skill)" | What data | Yes/No |

### Triggers (outputs to other skills)

| Condition | Triggers Skill | Data Passed |
|-----------|---------------|-------------|
| When X happens | target-skill-name | data_field_1, data_field_2 |

### Workflow Position

```
[Upstream Event]
       |
       v
[THIS SKILL]
       |
       +-- Outcome A --> [Downstream Skill A]
       +-- Outcome B --> [Downstream Skill B]
```

---

## Roles & Permissions

| Role | Permissions | Typical Title |
|------|------------|---------------|
| operator | What they can do | Job title |
| reviewer | What they can do | Job title |
| approver | What they can do | Job title |
| auditor | What they can do | Job title |
| admin | What they can do | Job title |

### Segregation of Duties

| Action | Cannot Be Performed By |
|--------|----------------------|
| Specific action | Role restriction |

---

## Reporting

### Key Performance Indicators

| KPI | Description | Data Source | Target | Frequency |
|-----|------------|-------------|--------|-----------|
| kpi_name | What it measures | Which step | Target value | Daily/Weekly/Monthly |

### Data Points to Capture

| Data Point | Type | Captured At | Used In |
|-----------|------|-------------|---------|
| field_name | type | Which step | Which reports |

### Suggested Reports

| Report | Frequency | Audience | Description |
|--------|-----------|----------|-------------|
| Report name | Frequency | Who sees it | What it shows |

### Alert Triggers

| Alert | Condition | Severity | Action |
|-------|-----------|----------|--------|
| Alert name | When to fire | Low/Medium/High/Critical | What to do |

---

## Error Handling

### Failure Scenarios

| Scenario | Handling | Fallback | Severity |
|----------|---------|----------|----------|
| What can fail | How to handle | Fallback approach | Low/Medium/High/Critical |

### Critical Rules

1. Rule that must never be violated — explanation
2. Another critical rule — explanation

---

## Framework Alignment

### Primary Framework

- **Framework:** Framework Name (version)
- **Mapping:** Specific service domain, process area, or reference ID
- **Description:** How this skill aligns with the framework element. What the framework defines vs. what OpenIOM adds.

### Secondary Framework

- **Framework:** Secondary Framework Name
- **Mapping:** Specific reference
- **Description:** How this skill maps to the secondary framework

### Notes

Any caveats about the mapping accuracy or completeness.

---

## Audit Requirements

### Mandatory Audit Events

| Event | Data to Log | Triggered At | Immutable |
|-------|------------|--------------|-----------|
| Event name | What data to capture | Which step | Yes/No |

### Regulatory Retention Requirements

| Jurisdiction | Minimum Retention | Post-Relationship | Reference |
|-------------|-------------------|-------------------|-----------|
| Global (FATF baseline) | Period | From end of relationship | Reference |
| Locale-specific | Period | From end of relationship | Law, section |

### Audit Trail Access

| Role | Access Level |
|------|-------------|
| Role name | What they can see |

---

## Data Classification

### Data Sensitivity Levels

| Data Point | Classification | Handling Requirements |
|-----------|---------------|---------------------|
| field_name | PII / Sensitive PII / Confidential / Internal / Restricted | How to handle |

### Classification Definitions

| Level | Description | Access |
|-------|------------|--------|
| Public | Non-sensitive | All roles |
| Internal | Business-internal | Authenticated users |
| Confidential | Sensitive business | Specific roles |
| PII | Personally identifiable | Need-to-know |
| Sensitive PII | High-risk personal | Strict access control |
| Restricted | Highest sensitivity | Named individuals only |

---

## Validation Scenarios

| # | Scenario | Input Profile | Expected Outcome |
|---|----------|--------------|-----------------|
| 1 | Standard happy path | Description | Expected result |
| 2 | Edge case | Description | Expected result |
| 3 | Error scenario | Description | Expected result |

---

## SLA Expectations

### Processing Time Targets

| Step | Target Duration | Maximum Duration | Notes |
|------|----------------|-----------------|-------|
| Step name | Target | Maximum | Context |

### End-to-End Targets

| Scenario | Target | Maximum |
|----------|--------|---------|
| Scenario description | Target time | Maximum time |

### SLA Breach Handling

| Breach | Action |
|--------|--------|
| What breach | What to do |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | YYYY-MM-DD | Initial release. Description of what's included. |
