# OpenIOM Governance

## Current Model

OpenIOM is founded and maintained by **Tyms** (Intelligent Tyms Inc.). The project currently operates under a **BDFL (Benevolent Dictator for Life)** model, where Tyms has final authority on all decisions.

This is appropriate for an early-stage project where speed, consistency, and quality control matter more than distributed governance. As the community grows, governance will evolve.

---

## Decision-Making

### Day-to-Day Decisions

Tyms maintainers handle:
- Reviewing and merging pull requests
- Managing releases and versioning
- Responding to issues and discussions
- Enforcing quality standards and format compliance

### Strategic Decisions

Tyms leadership handles:
- Adding new industries to the taxonomy
- Changes to the skill format specification
- Changes to the metadata schema
- Licensing decisions
- Partnership and endorsement decisions

---

## Transition Plan

As OpenIOM grows, governance will transition from BDFL to a **Steering Committee** model:

### Phase 1: Current (BDFL)
- Tyms maintains full authority
- Community feedback welcomed through GitHub issues and discussions
- Transparency through public roadmap and changelog

### Phase 2: Advisory Committee (target: Month 6-8)
- Form a Steering Committee with:
  - Tyms (permanent seat)
  - 2-3 external members selected based on contribution volume and domain expertise
- Committee advises on: new industry prioritization, locale quality standards, spec evolution
- Tyms retains final decision authority but commits to transparency about when and why it overrides committee recommendations

### Phase 3: Shared Governance (target: Month 12+)
- Steering Committee has decision authority over:
  - New industry approval
  - Specification changes
  - Locale quality standards
  - Dispute resolution between contributors
- Tyms retains authority over:
  - Trademark and brand
  - CLA terms
  - Licensing changes
  - Decisions affecting the Tyms commercial platform

---

## Roles

### Maintainer
- Employed by or contracted to Tyms
- Can merge PRs, manage releases, enforce standards
- Responsible for review SLA (target: 24 hours for initial response)

### Domain Expert Reviewer
- Trusted community member with verified domain expertise
- Can approve PRs within their domain (industry/locale)
- Cannot merge without maintainer approval (initially)
- Selected by maintainers based on contribution history and expertise

### Trusted Contributor
- Community member with significant contribution history
- May be granted merge rights on specific industry or locale areas
- Selected by maintainers, ratified by steering committee when it exists

### Contributor
- Anyone who submits a PR that gets merged
- Listed on the contributors page
- May participate in GitHub discussions and community calls

---

## Transparency Commitments

1. All governance decisions are documented in this file or in GitHub issues
2. Steering committee meeting minutes will be published (when committee exists)
3. Spec changes go through a public RFC (Request for Comments) process
4. The roadmap is public
5. Rejection of contributions includes a clear explanation

---

## Contact

- Governance questions: opensource@tyms.com
- General discussion: [GitHub Discussions](../../discussions)
