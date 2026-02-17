# Contributing to OpenIOM

Thank you for your interest in contributing to OpenIOM. This library is built by domain experts, industry practitioners, consultants, and developers who want to make AI agents genuinely useful for business operations.

---

## Before You Start

1. Read the [skill format specification](spec/SKILL_FORMAT.md) and [locale format specification](spec/LOCALE_FORMAT.md)
2. Look at an existing skill (e.g., [KYC Customer Onboarding](skills/financial-services/commercial-banking/kyc-customer-onboarding/SKILL.md)) to see the expected quality and depth
3. Check the [industry taxonomy](industries/TAXONOMY.md) and [framework mappings](industries/FRAMEWORKS.md) to understand how skills are organized

---

## Contribution Difficulty Ladder

### Easy (30 minutes, domain knowledge only)

**Add a locale overlay to an existing skill**

If you have domain expertise in a specific country, you can add a locale overlay that provides country-specific context for an existing skill. For example, adding a Nigeria overlay (`NG.md`) to the KYC skill.

What you need to provide:
- Regulatory authority and legal framework
- Accepted documents and ID systems
- Local verification systems and APIs
- Country-specific risk factors
- Local reporting requirements and thresholds
- Audit retention periods per local law
- Language and cultural considerations
- Common technology stacks in that market

See the [locale template](template/skill-template/locales/LOCALE_TEMPLATE.md) and an existing overlay like [UG.md](skills/financial-services/commercial-banking/kyc-customer-onboarding/locales/UG.md) for reference.

**Fix a typo, inaccuracy, or outdated reference**

If you spot an error — a wrong regulatory reference, an outdated threshold, a misspelled term — open a PR with the fix. Include a source or reference for the correction.

**Add a validation scenario**

Add a new test case to an existing skill's Validation Scenarios section. Describe the scenario, input profile, and expected outcome.

### Medium (1-3 hours, domain knowledge required)

**Add reporting KPIs or alert triggers**

If you know an industry tracks a metric that an existing skill doesn't capture, add it to the Reporting section with: KPI name, description, data source, target, and frequency.

**Add error handling scenarios**

If you know a failure mode that an existing skill doesn't cover, add it to the Error Handling section with: scenario, handling, fallback, and severity.

**Add a locale overlay with full depth**

A comprehensive locale overlay that covers all sections (regulatory authority, documents, verification systems, risk factors, reporting, audit, data protection, tax, language, technology) takes more time but is extremely valuable.

### Hard (half-day to full day, deep domain expertise)

**Create a new base skill**

Writing a complete base skill from scratch requires deep knowledge of the operational process. You must cover all required sections per the [skill format specification](spec/SKILL_FORMAT.md) and include a framework alignment mapping.

Use the [skill template](template/skill-template/SKILL.md) as your starting point.

**Create a new industry section**

Opening a new industry (e.g., Healthcare, Agriculture) requires defining the sub-sectors, identifying the reference framework, and writing at least 2-3 initial skills with locale overlays.

---

## How to Submit

### For all contributions

1. Fork the repository
2. Create a branch: `git checkout -b <type>/<description>` (e.g., `locale/ng-kyc` or `skill/loan-origination`)
3. Make your changes following the format specifications
4. Ensure your contribution meets the quality standards below
5. Submit a pull request using the PR template

### Quality Standards

All contributions must:

- [ ] Follow the [skill format specification](spec/SKILL_FORMAT.md) (all required sections present)
- [ ] Include accurate, verifiable information with sources cited where applicable
- [ ] Include a `reference_framework` in metadata and a `## Framework Alignment` section in the skill body (even if the framework is "APQC Cross-Industry PCF")
- [ ] Not contain proprietary or confidential client information
- [ ] Not contain personally identifiable information (PII)
- [ ] Use clear, professional English
- [ ] Include at least 3 validation scenarios (for new skills)
- [ ] Include at least 3 KPIs in the reporting section (for new skills)

### For locale overlays specifically

- [ ] Cite the specific laws, regulations, or guidelines referenced
- [ ] Include a `last_updated` date in the frontmatter
- [ ] Include the `legal_framework` field listing relevant legislation
- [ ] Be reviewed by someone with in-country domain expertise

---

## Contributor License Agreement (CLA)

By submitting a pull request, you agree to the following:

1. You have the right to submit the contribution
2. Your contribution does not contain proprietary or confidential information from any employer, client, or third party
3. You grant Intelligent Tyms Inc. ("Tyms") a perpetual, worldwide, non-exclusive, royalty-free license to use, reproduce, modify, and distribute your contribution as part of OpenIOM and the Tyms commercial platform
4. Your contribution will be licensed under Apache 2.0 (for base skills) or CC BY-SA 4.0 (for locale overlays) as appropriate
5. You understand that your contribution is public and may be used by others under these licenses

---

## Review Process

1. **Automated checks** — CI validates format compliance, metadata schema, and locale file presence
2. **Maintainer review** — A Tyms maintainer reviews for format compliance and consistency
3. **Domain expert review** — For new skills and locale overlays, at least one domain expert reviews for accuracy
4. **Merge** — Once approved, the contribution is merged to main

Typical review time: 3-7 days for locale overlays, 1-2 weeks for new skills.

---

## Recognition

All contributors are recognized in the repository. Significant contributors may be invited to join as domain expert reviewers or, as the project matures, to participate in the steering committee.

---

## Questions?

- Open a [GitHub Discussion](../../discussions) for questions about contributing
- Open an [issue](../../issues) to report errors or request new skills
- Email: opensource@tyms.com

---

## Code of Conduct

All contributors must follow the [Code of Conduct](CODE_OF_CONDUCT.md).
