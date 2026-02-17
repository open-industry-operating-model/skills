# OpenIOM Framework Reference Table

**Version:** 1.0.0
**Last Updated:** 2026-02-17

Every OpenIOM skill must map to an established industry framework. This document is the single source of truth for which framework governs which industry.

OpenIOM does not invent operating models. It maps to existing frameworks and adds what they lack: locale-specific detail, AI-ready definitions, compliance requirements, error handling, and inter-skill dependencies.

---

## Framework Assignments by Industry

| OpenIOM Industry | Primary Framework | Version | Scope | Secondary Framework |
|-----------------|-------------------|---------|-------|-------------------|
| Financial Services — Banking | BIAN (Banking Industry Architecture Network) | 13.0 | Service domains, business capabilities | APQC Banking PCF |
| Financial Services — Mobile Money | GSMA Mobile Money API & Guidelines | Current | API standards, operational guidelines | eTOM (TM Forum) |
| Financial Services — Insurance | ACORD (Association for Cooperative Operations Research and Development) | Current | Data standards, transaction frameworks | APQC Insurance PCF |
| Financial Services — Microfinance | BIAN (adapted) | 13.0 | Adapted service domains for MFI context | APQC Banking PCF |
| Telecommunications | eTOM (Enhanced Telecom Operations Map) / TM Forum Frameworx | 23.0 | Process framework, information framework | SID (Shared Information/Data Model) |
| FMCG / Retail — Supply Chain | SCOR DS (Supply Chain Operations Reference Digital Standard) | 14.0 | Plan, Source, Make, Deliver, Return, Enable | APQC Retail PCF |
| FMCG / Retail — Retail Operations | APQC Retail PCF | Current | Process classification | — |
| Hospitality | APQC Cross-Industry PCF | Current | Generic process baseline | — |
| Healthcare | HL7 FHIR (Fast Healthcare Interoperability Resources) | R4/R5 | Clinical data standards, workflows | APQC Healthcare PCF |
| Agriculture | APQC Cross-Industry PCF | Current | Generic process baseline | — |
| Logistics & Transport | SCOR DS | 14.0 | Supply chain processes | APQC Cross-Industry PCF |
| Manufacturing | SCOR DS + ISA-95 | Current | Supply chain + manufacturing operations | APQC Manufacturing PCF |
| Education | APQC Education PCF | Current | Education-specific processes | — |
| Government | APQC Government PCF | Current | Government-specific processes | — |
| Energy & Utilities | APQC Utilities PCF | Current | Utilities-specific processes | — |
| Professional Services | APQC Cross-Industry PCF | Current | Generic process baseline | — |

---

## Framework Descriptions

### BIAN (Banking Industry Architecture Network)

- **What it defines:** A service-oriented architecture framework for banking. Defines ~300 service domains that represent discrete business capabilities.
- **What it does NOT define:** Locale-specific regulations, compliance procedures, error handling, reporting KPIs, or implementation detail.
- **What OpenIOM adds:** Locale-specific regulatory requirements, accepted documents, verification systems, risk factors, reporting obligations, audit requirements, error handling, role definitions, and inter-skill dependencies.
- **Access:** Public landscape available at bian.org. Detailed service domain specifications may require membership.
- **URL:** https://bian.org

### eTOM / TM Forum Frameworx

- **What it defines:** A comprehensive process framework for telecommunications operators. Organizes processes into Strategy/Infrastructure/Product (SIP) and Operations domains.
- **What it does NOT define:** Locale-specific regulatory context, local technology stacks, or implementation-level procedures.
- **What OpenIOM adds:** Same as BIAN — locale-specific context, operational detail, compliance, error handling.
- **Access:** Process maps available at tmforum.org. Full framework requires TM Forum membership.
- **URL:** https://www.tmforum.org/oda/business/process-framework-etom/

### SCOR DS (Supply Chain Operations Reference Digital Standard)

- **What it defines:** A process reference model for supply chain management. Covers Plan, Source, Make, Deliver, Return, and Enable processes.
- **What it does NOT define:** Industry-specific variants, locale compliance, or technology-specific integration.
- **What OpenIOM adds:** Industry-specific operational detail (e.g., FMCG distribution vs. manufacturing), locale-specific compliance, local system integrations.
- **Access:** Managed by ASCM (Association for Supply Chain Management). Full standard requires membership.
- **URL:** https://www.ascm.org/

### APQC Process Classification Framework (PCF)

- **What it defines:** A taxonomy of business processes, organized hierarchically. Available in cross-industry and industry-specific versions (Banking, Healthcare, Education, Government, etc.).
- **What it does NOT define:** Operational procedures, compliance requirements, or implementation detail.
- **What OpenIOM adds:** Deep operational content for each process — steps, inputs/outputs, error handling, reporting, compliance, locale context.
- **Used when:** An industry has no dedicated framework (Hospitality, Agriculture, Professional Services) or as a secondary framework for supplementary process classification.
- **Access:** Public at apqc.org.
- **URL:** https://www.apqc.org/process-frameworks

### HL7 FHIR

- **What it defines:** A standard for exchanging healthcare information electronically. Defines resources, APIs, and clinical data structures.
- **What it does NOT define:** Hospital operational procedures, locale-specific healthcare regulations, or business process flows.
- **What OpenIOM adds:** Operational skill definitions for healthcare processes, with FHIR resource mappings where applicable, plus locale-specific regulatory context.
- **URL:** https://www.hl7.org/fhir/

### GSMA Mobile Money

- **What it defines:** API standards and operational guidelines for mobile money services.
- **What it does NOT define:** Country-specific mobile money regulations, local MNO technology stacks, or detailed operational procedures.
- **What OpenIOM adds:** Locale-specific mobile money operations, local regulatory requirements, MNO-specific integration details.
- **URL:** https://www.gsma.com/mobilefordevelopment/mobile-money/

### ACORD

- **What it defines:** Data standards and transaction frameworks for the insurance industry.
- **What it does NOT define:** Locale-specific insurance regulations, local market practices, or operational procedures.
- **What OpenIOM adds:** Operational skill definitions for insurance processes with locale-specific regulatory context.
- **URL:** https://www.acord.org/

---

## How Framework Alignment Works in Skills

Every OpenIOM skill must include:

### 1. In the frontmatter (`reference_framework` field):

```yaml
reference_framework:
  primary:
    name: "BIAN (Banking Industry Architecture Network)"
    version: "13.0"
    mapping: "Party Reference Data Management, Customer Offer"
  secondary:
    name: "APQC Banking PCF"
    mapping: "8.1.1 Establish KYC, 8.1.2 Perform due diligence"
```

### 2. In the skill body (`## Framework Alignment` section):

A narrative section explaining:
- How the skill maps to the framework's concepts
- What the framework defines vs. what OpenIOM adds
- Any caveats about the mapping (preliminary, adapted, etc.)

---

## For Industries Without Established Frameworks

When an industry lacks a dedicated operational framework (e.g., Hospitality, Agriculture), OpenIOM uses:

1. **APQC Cross-Industry PCF** as a structural baseline for organizing processes
2. **Domain-specific common practice** validated by industry practitioners
3. A note in the Framework Alignment section explaining the basis

The Framework Alignment section should document:
- Which APQC process categories the skill maps to
- That the operational content is based on industry common practice
- Names of domain experts or sources that validated the content

---

## Updating This Document

When adding a new industry or changing a framework assignment:

1. Update this table via PR
2. Include rationale for the framework choice
3. Get approval from a maintainer
4. Update all affected skills to reference the new framework
