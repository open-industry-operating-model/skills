---
locale: UG
country: Uganda
skill: kyc-customer-onboarding
version: 1.0.0
regulator: Bank of Uganda (BoU)
last_updated: 2026-02-17
legal_framework:
  - Anti-Money Laundering Act 2013
  - Financial Institutions Act 2004
  - Bank of Uganda KYC Guidelines 2019
  - National Payment Systems Act 2020
  - Data Protection and Privacy Act 2019
  - The Anti-Terrorism Act 2002
  - NGO Act 2016
authors:
  - name: Tyms
    url: https://tyms.com
---

# Uganda — KYC Customer Onboarding

## Regulatory Authority

The **Bank of Uganda (BoU)** is the primary regulator for KYC compliance in commercial banking. The **Financial Intelligence Authority (FIA)** oversees AML/CFT compliance and receives suspicious transaction reports. The **National Information Technology Authority (NITA-U)** oversees data protection compliance under the Data Protection and Privacy Act 2019.

All commercial banks supervised by BoU must comply with the Anti-Money Laundering Act 2013 and the BoU KYC Guidelines 2019.

---

## Accepted Identity Documents

### Individual Customers

| Document | Status | Notes |
|----------|--------|-------|
| National Identity Card (NIN) | Primary — Required | Issued by NIRA. 14-digit National Identification Number. Required for all standard and enhanced KYC accounts. |
| Ugandan Passport | Accepted | For Ugandan citizens. Valid as primary ID alongside NIN. |
| Driving Permit | Accepted | Issued by Ministry of Works and Transport. Must include photo. |
| Refugee Identity Card | Accepted | Issued by Office of the Prime Minister (OPM). Accepted for simplified KYC tier under refugee provisions. |
| Village LC1 Letter | Supplementary only | Issued by Local Council I Chairman. Cannot be sole identity document. Used for address verification in rural areas. |
| Employee ID Card | Supplementary only | For employment verification. Not accepted as primary ID. |
| Student ID Card | Not accepted | Not accepted for banking KYC. |

### Business Customers

| Document | Status | Notes |
|----------|--------|-------|
| Certificate of Incorporation / Registration | Required | From URSB for companies, or district for sole proprietors |
| Memorandum and Articles of Association | Required | For companies limited by shares or guarantee |
| URA TIN Certificate | Required | Tax Identification Number from Uganda Revenue Authority |
| Trading License | Required | From KCCA (Kampala) or relevant district authority |
| Board Resolution for account opening | Required | Authorizing the opening of the bank account and nominating signatories |
| Beneficial ownership declaration | Required | For all shareholders/members with 25%+ ownership |
| Certificate of Compliance | Recommended | Annual compliance certificate from URSB |
| NGO Registration Certificate | Required (NGOs) | From the NGO Board, Ministry of Internal Affairs |
| Partnership Deed | Required (Partnerships) | For partnership accounts |

---

## Verification Systems

| System | Provider | Purpose | Access Method |
|--------|----------|---------|---------------|
| NIRA NIN Verification API | National Identification and Registration Authority | Real-time verification of National Identification Number against national database | Licensed API access. Banks must register with NIRA for API credentials. |
| URA TIN Verification | Uganda Revenue Authority | Verification of Tax Identification Number for business accounts | URA web services / API |
| URSB Company Registry | Uganda Registration Services Bureau | Verification of company registration, directors, shareholders | URSB online portal / API |
| BoU Licensed Institutions Register | Bank of Uganda | Verification of financial institution licenses | Public register at bankofuganda.go.ug |

---

## Mobile Money Considerations

Uganda has high mobile money penetration. For mobile money-linked accounts and mobile money KYC, BoU mandates tiered KYC:

| KYC Tier | Requirements | Transaction Limits | Account Limits |
|----------|-------------|-------------------|----------------|
| Minimum KYC | NIN only | UGX 1,000,000/day send, UGX 2,000,000/day receive | UGX 5,000,000 balance |
| Medium KYC | NIN + one additional document | UGX 4,000,000/day | UGX 10,000,000 balance |
| Full KYC | Complete documentation per standard banking KYC | Full limits per product | No balance cap per KYC |

**Mobile money integration points:**
- Verify registered SIM against MTN MoMo / Airtel Money databases
- Cross-reference mobile money KYC tier with banking KYC requirements
- For mobile money-to-bank account linking, banking KYC level applies

---

## Uganda-Specific Risk Factors

| Risk Factor | Level | Notes |
|------------|-------|-------|
| Cross-border transactions (DRC, South Sudan) | High | Conflict zones, active sanctions programs, limited KYC infrastructure in neighboring countries |
| Cross-border transactions (Kenya, Tanzania, Rwanda) | Medium | Standard EAC trade corridor. Lower risk but monitor for trade-based money laundering. |
| Cash-intensive businesses (northern Uganda, Karamoja) | High | Limited banking infrastructure in these regions. Higher cash dependency increases ML risk. |
| Politically Exposed Persons (PEPs) | High | Includes: Members of Parliament, Cabinet Ministers, Judiciary, Senior Military Officers (UPDF), Heads of Parastatals and Government Agencies, Senior officials of political parties |
| NGO / CBO accounts | Medium-High | Additional scrutiny required per NGO Act 2016. Foreign-funded NGOs require enhanced due diligence on funding sources. |
| Religious and charitable organizations | Medium | Enhanced due diligence on funding sources and beneficiaries. Monitor for terrorism financing risk. |
| Gold and mineral trading | High | Per ESAAMLG (Eastern and Southern Africa Anti-Money Laundering Group) mutual evaluation findings. Uganda is a transit point for conflict minerals. |
| Real estate transactions | Medium-High | Emerging money laundering risk sector per FIA risk assessment. Property used for layering. |
| Cross-border remittances | Medium | Monitor for structuring (breaking large amounts into smaller transfers to avoid thresholds). |
| Forex bureau transactions | Medium-High | Cash-intensive, cross-border nature increases ML risk. |
| Customer from Karamoja sub-region | Medium | Geographic risk factor. Pastoralist communities may have limited formal ID. Consider alternative ID acceptance within BoU guidelines. |

---

## Uganda-Specific Reporting Requirements

| Report | Recipient | Threshold / Trigger | Frequency | Legal Reference |
|--------|-----------|-------------------|-----------|-----------------|
| Suspicious Transaction Report (STR) | Financial Intelligence Authority (FIA) | Any transaction or activity suspected of ML/TF, regardless of amount | As occurs (within 2 working days of suspicion) | AML Act 2013, s.6 |
| Large Cash Transaction Report (CTR) | FIA | Cash transactions of UGX 20,000,000 or equivalent in foreign currency | As occurs | AML Act 2013, s.6(3) |
| Cross-border wire transfer report | Bank of Uganda | All cross-border wire transfers | As occurs | BoU Regulations |
| Electronic funds transfer report | FIA | Electronic transfers of UGX 20,000,000 or above | As occurs | AML Act 2013 |
| KYC compliance summary | BoU | Upon regulatory examination or request | On request | FIA Act 2004, BoU KYC Guidelines |
| Terrorism financing report | FIA | Any suspected terrorism financing activity | Immediately | Anti-Terrorism Act 2002 |

---

## Uganda-Specific Audit Retention

| Record Type | Retention Period | Legal Reference |
|-------------|-----------------|-----------------|
| KYC records (all customer documentation) | 10 years from end of business relationship | AML Act 2013, s.19 |
| Transaction records | 10 years from date of transaction | AML Act 2013, s.19 |
| STR records | 10 years from date of filing | FIA Guidelines |
| Internal audit reports | 10 years | AML Act 2013, s.19 |
| Customer communications | 7 years | Data Protection and Privacy Act 2019 |
| Board and committee minutes (compliance) | 10 years | FIA Act 2004 |
| Staff training records (AML/KYC) | 5 years from date of training | BoU KYC Guidelines |

---

## Data Protection (Uganda)

Under the **Data Protection and Privacy Act 2019** and supervised by NITA-U:

- **Consent:** Customer consent is required before collection and processing of personal data. Consent must be informed, specific, and freely given.
- **Data minimization:** Collect only data necessary for the stated purpose (KYC/AML compliance).
- **Purpose limitation:** Personal data collected for KYC cannot be used for marketing without separate consent.
- **Cross-border transfer:** Restricted. NITA-U approval may be required for transfer of personal data outside Uganda. Data adequacy assessment of the receiving country is required.
- **Data breach notification:** Report to NITA-U within 48 hours of becoming aware of a personal data breach. Notify affected individuals without undue delay.
- **Customer rights:** Right to access personal data held by the bank, right to correction of inaccurate data, right to deletion (subject to regulatory retention requirements overriding).
- **Data Protection Impact Assessment:** Required for high-risk processing activities (which includes large-scale KYC processing).

---

## Tax Compliance Integration

- **URA TIN:** Mandatory for all business accounts and recommended for individual accounts with taxable income
- **Withholding tax on interest:** 15% for residents, 15% for non-residents. Bank must deduct at source.
- **VAT registration verification:** For businesses claiming VAT, verify URA VAT registration (turnover > UGX 150,000,000)
- **Rental income tax:** For property-related accounts, verify compliance with rental income tax (12% on gross rental income for individuals, 30% for corporates)
- **Capital gains tax:** 6% on sale of assets. Relevant for investment-related account opening.
- **Digital tax stamps:** For manufacturing businesses, verify compliance with digital tax stamp requirements

---

## Language Considerations

- **Primary business language:** English
- **All formal KYC documentation:** Must be in English per BoU requirements
- **Customer-facing communications may need localization into:**
  - Luganda (Central region, Kampala)
  - Runyankole / Rukiga (Western Uganda)
  - Luo / Acholi (Northern Uganda)
  - Ateso (Eastern Uganda)
  - Lugbara (West Nile)
- **Consent forms** should be available in local languages to ensure informed consent per Data Protection Act
- **Document translation:** If source documents are in a language other than English, certified translation may be required

---

## Common Core Banking Systems in Uganda

| System | Vendor | Banks Using | Integration Notes |
|--------|--------|-------------|-------------------|
| Flexcube | Oracle | Stanbic Bank, dfcu Bank, Centenary Bank | REST/SOAP APIs, batch processing. Supports automated account opening. |
| T24 (Transact) | Temenos | Standard Chartered, Bank of Baroda | API-first architecture. Strong KYC module. |
| BankMaster | TCS | Absa Uganda | Legacy integration patterns. Batch-heavy. |
| Finacle | Infosys | Select institutions | Modular architecture. KYC workflow built-in. |
| Craft Silicon | Craft Silicon | Select SACCOs and MFIs | Primarily used by smaller institutions. |

---

## Uganda-Specific Validation Scenarios

| # | Scenario | Expected Outcome |
|---|----------|-----------------|
| U1 | LC1 letter presented as sole identity document | Reject as primary ID. Request NIN or other primary document. LC1 accepted as supplementary only. |
| U2 | Mobile money KYC tier upgrade (minimum to medium) | Request one additional document beyond NIN. Upon verification, increase transaction and balance limits per BoU tiered KYC. |
| U3 | URA TIN verification fails for business account | Flag for manual review. Request physical TIN certificate from customer. Do not activate business account until TIN is verified. |
| U4 | Refugee with OPM-issued Refugee Identity Card, no NIN | Accept under simplified KYC tier per BoU refugee provisions. Apply simplified KYC transaction limits. Schedule upgrade to standard KYC if refugee obtains NIN. |
| U5 | Customer from Karamoja region, pastoralist | Apply geographic risk factor (medium). If customer lacks NIN, explore alternative ID options within BoU guidelines. May require enhanced due diligence. |
| U6 | NGO with foreign donors | Enhanced due diligence required. Verify NGO Board registration. Scrutinize funding sources and donor countries. Apply NGO risk factor (medium-high). Check for sanctioned donor countries. |
| U7 | Customer is a Member of Parliament | PEP classification required. Enhanced due diligence. Approver-level decision. Cannot be auto-approved regardless of risk score. Document source of wealth. |
| U8 | Gold dealer from Busia (border town with Kenya) | Apply gold/mineral trading risk factor (high) and cross-border risk factor (medium for Kenya). Enhanced due diligence on source of funds and business operations. |
| U9 | Cross-border wire transfer to DRC above UGX 20M | Trigger large transaction report to FIA. Apply high geographic risk factor for DRC. Verify purpose of transfer. May trigger STR depending on customer profile. |
| U10 | Customer provides NIN but NIRA verification API is down | Queue for retry (max 3 attempts over 24 hours). Do not approve without completed NIN verification. Offer manual verification with physical NIN card as fallback if API remains unavailable after 24 hours. |
