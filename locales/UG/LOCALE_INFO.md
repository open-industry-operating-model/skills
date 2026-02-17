---
locale: UG
country: Uganda
last_updated: 2026-02-17
authors:
  - name: Tyms
    url: https://tyms.com
---

# Uganda — Country Reference

This document provides reference information about Uganda that applies across multiple OpenIOM skills. Skill-specific locale overlays reference and build on this information.

---

## Regulatory Bodies

| Authority | Abbreviation | Jurisdiction | Website |
|-----------|-------------|-------------|---------|
| Bank of Uganda | BoU | Banking, microfinance, mobile money, forex, payment systems | bankofuganda.go.ug |
| Financial Intelligence Authority | FIA | AML/CFT compliance, suspicious transaction reporting | fia.go.ug |
| Uganda Revenue Authority | URA | Tax collection, TIN issuance, customs | ura.go.ug |
| National Information Technology Authority | NITA-U | Data protection, IT governance, cross-border data transfer | nita.go.ug |
| Insurance Regulatory Authority of Uganda | IRA | Insurance industry regulation | ira.go.ug |
| Uganda Communications Commission | UCC | Telecommunications, broadcasting, postal services | ucc.co.ug |
| Capital Markets Authority | CMA | Securities, stock exchange, collective investment schemes | cmauganda.co.ug |
| Uganda Registration Services Bureau | URSB | Company registration, business names, IP | ursb.go.ug |
| Kampala Capital City Authority | KCCA | Trading licenses in Kampala | kcca.go.ug |
| National Identification and Registration Authority | NIRA | National identity cards, civil registration | nira.go.ug |

---

## National Identity Systems

### Identity Documents

| Document | Issuing Authority | Digital Verification | Notes |
|----------|------------------|---------------------|-------|
| National Identity Card (NIN) | NIRA | Yes — NIRA API | Primary ID for all citizens aged 16+. 14-digit National Identification Number. |
| Ugandan Passport | Directorate of Citizenship and Immigration | Limited | For international travel, accepted as secondary banking ID |
| Driving Permit | Ministry of Works and Transport | Limited | Photo ID, accepted for KYC |
| Refugee Identity Card | Office of the Prime Minister (OPM) | Limited | Issued to registered refugees, accepted for simplified KYC |
| Village LC1 Letter | Local Council I Chairman | No | Supplementary document only; not accepted as sole ID |

### Verification APIs

| System | Provider | Purpose | Access |
|--------|----------|---------|--------|
| NIRA National ID Verification | NIRA | Real-time NIN verification against national database | Licensed access via NIRA API |
| URA TIN Verification | URA | Tax Identification Number verification for businesses | Via URA web services |
| URSB Company Registry | URSB | Company registration verification | Via URSB online portal |

---

## Tax Authority and Compliance

### Uganda Revenue Authority (URA)

- **TIN (Tax Identification Number):** Mandatory for all business accounts and individuals with taxable income
- **VAT Registration:** Required for businesses with annual turnover exceeding UGX 150,000,000
- **Withholding Tax on Interest:** 15% for residents, 15% for non-residents
- **Digital Tax Stamps:** Required for certain manufactured goods
- **e-Invoicing:** Being rolled out; integration with URA EFRIS (Electronic Fiscal Receipting and Invoicing Solution)

### Key Tax Types

| Tax | Rate | Applies To |
|-----|------|-----------|
| Corporate Income Tax | 30% | Companies |
| PAYE (Pay As You Earn) | Progressive: 0-40% | Employment income |
| VAT | 18% | Goods and services above threshold |
| Withholding Tax | 6-15% | Various (services, interest, rent) |
| Excise Duty on Mobile Money | 0.5% of transaction value | Mobile money withdrawals |

---

## Data Protection

### Data Protection and Privacy Act, 2019

- **Authority:** NITA-U (National Information Technology Authority - Uganda)
- **Key Principles:**
  - Consent required for data collection and processing
  - Data minimization — collect only what is necessary
  - Purpose limitation — use data only for stated purpose
  - Right to access, correct, and delete personal data
- **Cross-border Transfer:** Restricted; NITA-U approval may be required for transfers outside Uganda
- **Breach Notification:** Within 48 hours to NITA-U
- **Penalties:** Fines and/or imprisonment for violations

---

## Financial Infrastructure

### Banking System

| Category | Details |
|----------|---------|
| Central Bank | Bank of Uganda (BoU) |
| Commercial Banks | ~25 licensed commercial banks |
| Microfinance | ~4 MDIs (Microfinance Deposit-taking Institutions), multiple SACCOs |
| Mobile Money | MTN MoMo, Airtel Money (dominant), others |
| Payment Systems | RTGS (Uganda National Interbank Settlement System — UNISS), EFT, VISA/Mastercard networks |
| Agent Banking | Licensed by BoU, growing network |

### Core Banking Systems in Use

| System | Vendor | Used By |
|--------|--------|---------|
| Flexcube | Oracle | Stanbic Bank, dfcu Bank, Centenary Bank |
| T24 (Transact) | Temenos | Standard Chartered, Bank of Baroda |
| BankMaster | TCS | Absa Uganda |
| Finacle | Infosys | Select institutions |
| Craft Silicon | Craft Silicon | Select SACCOs and MFIs |

### Mobile Money Infrastructure

| Provider | Platform | Subscribers (approx.) |
|----------|----------|----------------------|
| MTN Uganda | MTN MoMo | 15M+ |
| Airtel Uganda | Airtel Money | 8M+ |

- Mobile money KYC is tiered by BoU regulation
- Interoperability between providers is active
- Mobile money agents serve as primary financial access point in rural areas

---

## Common Enterprise Technology

### ERP Systems

| System | Used By |
|--------|---------|
| SAP | Large enterprises, MNCs (MTN, Stanbic) |
| Oracle | Banking sector |
| Microsoft Dynamics | Mid-market enterprises |
| Sage | SMEs |
| QuickBooks | Small businesses |

### Telecom Platforms

| System | Vendor | Used By |
|--------|--------|---------|
| Ericsson Charging System | Ericsson | MTN Uganda |
| Huawei CBS | Huawei | Airtel Uganda |

---

## Language and Culture

### Business Languages

| Context | Language |
|---------|----------|
| Official and business language | English |
| Regulatory filings and legal documents | English |
| Customer-facing communications (central region) | Luganda |
| Regional languages | Runyankole/Rukiga (western), Luo (northern), Ateso (eastern), Lugbara (West Nile) |

### Cultural Considerations

- In-person relationships remain important for B2B business
- Mobile-first: high smartphone penetration, mobile money ubiquitous
- Rural areas: limited banking infrastructure, agents and mobile money are primary financial channels
- Trust in institutions varies; personal relationships and referrals carry significant weight

---

## Currency

| Detail | Value |
|--------|-------|
| Currency | Ugandan Shilling (UGX) |
| ISO 4217 Code | UGX |
| Central Bank | Bank of Uganda |
| Exchange Regime | Managed float |
| Common denominations | 1,000; 2,000; 5,000; 10,000; 20,000; 50,000 notes |

---

## Key Industry Associations

| Association | Focus |
|-------------|-------|
| Uganda Bankers' Association (UBA) | Commercial banking |
| Association of Microfinance Institutions of Uganda (AMFIU) | Microfinance |
| Uganda Insurance Association | Insurance |
| Uganda Manufacturers Association (UMA) | Manufacturing, FMCG |
| Uganda Hotel Owners Association (UHOA) | Hospitality |
| Uganda Communications Operators Association | Telecommunications |
| Private Sector Foundation Uganda (PSFU) | Cross-industry private sector |
| AI Association of Uganda | AI and technology |
