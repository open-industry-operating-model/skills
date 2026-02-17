# OpenIOM Skill Templates

Use these templates when creating new skills or locale overlays.

## Files

| Template | Use When |
|----------|----------|
| `skill-template/SKILL.md` | Creating a new base skill |
| `skill-template/metadata.yaml` | Creating the metadata file for a new skill |
| `skill-template/locales/LOCALE_TEMPLATE.md` | Creating a locale overlay for a skill |

## How to Use

### Creating a new skill

1. Copy the entire `skill-template/` directory to the appropriate location:
   ```
   skills/{industry}/{sub-sector}/{skill-name}/
   ```
2. Rename `LOCALE_TEMPLATE.md` to the country code (e.g., `UG.md`)
3. Fill in all required sections in `SKILL.md`
4. Fill in all required fields in `metadata.yaml`
5. Fill in the locale overlay
6. Submit a PR following the [contribution guide](../CONTRIBUTING.md)

### Adding a locale overlay to an existing skill

1. Copy `skill-template/locales/LOCALE_TEMPLATE.md` to the skill's `locales/` directory
2. Rename to the country code (e.g., `NG.md`)
3. Fill in all sections with country-specific information
4. Submit a PR

## Quality Checklist

Before submitting, verify:

- [ ] `name` in frontmatter matches directory name
- [ ] `reference_framework` is filled in (check [FRAMEWORKS.md](../industries/FRAMEWORKS.md))
- [ ] All required sections are present (see [SKILL_FORMAT.md](../spec/SKILL_FORMAT.md))
- [ ] At least 3 KPIs in Reporting section
- [ ] At least 3 validation scenarios
- [ ] At least one locale overlay included
- [ ] Locale overlay cites specific laws/regulations
