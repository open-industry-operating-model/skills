# OpenIOM Industry Taxonomy

**Version:** 1.0.0
**Last Updated:** 2026-02-17

This document defines the industry organization for the OpenIOM skills library. Skills are organized by industry, then sub-sector, then individual skill.

---

## Active Industries (Phase 1)

### Financial Services

**Directory:** `skills/financial-services/`

| Sub-sector | Directory | Skills | Status |
|-----------|-----------|--------|--------|
| Commercial Banking | `commercial-banking/` | KYC Customer Onboarding, Reconciliation, AML Monitoring, Loan Origination, Regulatory Reporting | Active |
| Mobile Money | `mobile-money/` | Agent Management, Float Management, Transaction Monitoring | Planned |
| Microfinance | `microfinance/` | Group Lending, Collections | Planned |
| Insurance | `insurance/` | Claims Processing, Policy Underwriting | Phase 2 |

**Reference Framework:** BIAN (Banking Industry Architecture Network) for banking; GSMA standards for mobile money; ACORD for insurance.

### Telecommunications

**Directory:** `skills/telecommunications/`

| Sub-sector | Directory | Skills | Status |
|-----------|-----------|--------|--------|
| Revenue Assurance | `revenue-assurance/` | Revenue Assurance | Planned |
| Network Operations | `network-operations/` | Fault Management | Planned |
| Customer Service | `customer-service/` | Customer Onboarding | Planned |

**Reference Framework:** eTOM / TM Forum Frameworx

### FMCG / Retail

**Directory:** `skills/fmcg-retail/`

| Sub-sector | Directory | Skills | Status |
|-----------|-----------|--------|--------|
| Inventory | `inventory-management/` | Inventory Management | Planned |
| Distribution | `route-to-market/` | Route-to-Market | Planned |
| Finance | `distributor-reconciliation/` | Distributor Reconciliation | Planned |

**Reference Framework:** SCOR DS (Supply Chain Operations Reference Digital Standard) for supply chain; APQC Retail PCF for retail operations.

### Hospitality

**Directory:** `skills/hospitality/`

| Sub-sector | Directory | Skills | Status |
|-----------|-----------|--------|--------|
| Restaurants | `reservation-management/` | Reservation Management | Planned |
| Food & Beverage | `food-cost-analysis/` | Food Cost Analysis | Planned |
| Procurement | `procurement/` | Procurement | Phase 2 |

**Reference Framework:** APQC Cross-Industry PCF (no industry-specific framework exists).

---

## Planned Industries (Phase 2-3)

| Industry | Sub-sectors | Reference Framework | Target Phase |
|----------|------------|-------------------|-------------|
| Healthcare | Hospitals, Clinics, Pharmacies | HL7 FHIR, APQC Healthcare PCF | Phase 2 |
| Education | Schools, Universities, EdTech | APQC Education PCF | Phase 2 |
| Agriculture | Farming, Agri-Processing, Cooperatives | APQC Cross-Industry PCF | Phase 2 |
| Logistics & Transport | Fleet Management, Warehousing, Last-Mile | SCOR DS | Phase 2 |
| Real Estate | Property Management, Construction | APQC Cross-Industry PCF | Phase 3 |
| Professional Services | Legal, Accounting, Consulting | APQC Cross-Industry PCF | Phase 3 |
| Manufacturing | Production, Quality Control, Supply Chain | SCOR DS, ISA-95 | Phase 3 |
| Government / Public Sector | Revenue Collection, Service Delivery, Procurement | APQC Government PCF | Phase 3 |
| Energy & Utilities | Power Distribution, Water, Solar | APQC Utilities PCF | Phase 3 |
| NGO / Development | Program Management, Grants, M&E | APQC Cross-Industry PCF | Phase 3 |

---

## Directory Naming Conventions

- **Industries:** lowercase, hyphenated (e.g., `financial-services`, `fmcg-retail`)
- **Sub-sectors:** lowercase, hyphenated (e.g., `commercial-banking`, `revenue-assurance`)
- **Skills:** lowercase, hyphenated, descriptive (e.g., `kyc-customer-onboarding`, `food-cost-analysis`)

---

## Adding a New Industry

To propose a new industry:

1. Open a [new skill request issue](../../issues/new?template=new-skill-request.md)
2. Include: industry name, proposed sub-sectors, reference framework, and at least 2-3 initial skills
3. A maintainer will review and approve the industry addition
4. Once approved, create the directory structure and submit the first skills via PR
