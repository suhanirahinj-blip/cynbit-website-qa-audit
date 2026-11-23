# Cynbit Website QA Audit

## Project Overview

This repository contains a manual QA audit of selected pages and workflows on the Cynbit website. The audit documents ten potential findings, test scenarios, environment information, test execution notes, and improvement recommendations.

**Website:** https://www.cynbit.in/  
**Audit Type:** Manual Functional, Usability, Content, and UI Review  
**Prepared:** 23 November 2026

## Scope

The following pages and workflows were reviewed based on the observations recorded during this audit:

- Homepage
- BitElevate page
- Blog listing and Data Privacy Advantage article
- Careers / Full-Stack Developer application form
- Case Studies
- Products page

Mobile responsive checks were also performed using Chrome mobile emulation at a viewport of 400 × 608 CSS pixels.

## Findings

Ten potential findings are documented in `BUG_REPORT.md`.

These include observations related to:

- Application-form validation.
- Name and phone input validation.
- Non-clickable interface elements.
- Blog article content and sharing functionality.
- Blog search behaviour.
- Academic score validation.
- Case Studies KPI interaction.
- Product-section alignment.

Some findings require further investigation or confirmation of the intended design and business rules. Severity and priority classifications are provisional.

## Repository Structure

```text
cynbit-website-qa-audit/
├── README.md
├── QA_AUDIT_REPORT.md
├── BUG_REPORT.md
├── TEST_CASES.md
├── TEST_ENVIRONMENT.md
├── IMPROVEMENT_RECOMMENDATIONS.md
├── AI_USAGE.md
├── LEARNING_REFLECTION.md
├── test-results/
│   └── test-execution-log.md
└── test-evidence/
    ├── screenshots/
    └── recordings/
```

## How to Use

1. Read `TEST_ENVIRONMENT.md` to understand the testing environment and its limitations.
2. Review `TEST_CASES.md` and `test-results/test-execution-log.md` for the test scenarios and recorded observations.
3. Review the individual findings in `BUG_REPORT.md`.
4. Refer to `IMPROVEMENT_RECOMMENDATIONS.md` for suggested improvements.
5. Read `QA_AUDIT_REPORT.md` for the overall audit summary.
6. Review `AI_USAGE.md` for the disclosure of AI assistance.
7. Add genuine screenshots to `test-evidence/screenshots/` and reference their filenames in the relevant bug entries.

## Important Notes

- This is a manual, observation-based QA audit, not a source-code review or penetration test.
- Browser version, operating-system build, device details, and desktop viewport dimensions were not captured in the available notes. These details are marked as not recorded rather than guessed.
- Mobile testing was performed using Chrome mobile emulation, not a physical mobile device.
- No Lighthouse metrics, automated accessibility results, backend logs, or API responses were provided. No performance or security pass is claimed.
- The audit notes do not establish that an application was successfully submitted to Cynbit's production system.
- Do not submit a real application merely to reproduce a validation issue.
- Findings should be reproduced and verified before being treated as confirmed defects.
- Re-test the website before final submission because website behaviour may change.

## Evidence

Place genuine screenshots in:

`test-evidence/screenshots/`

Place genuine screen recordings in:

`test-evidence/recordings/`

Use descriptive filenames such as:

- `BUG-001-application-validation.png`
- `BUG-003-bitelevate-card.png`
- `BUG-008-cgpa-validation.png`

Only include screenshots and recordings that were actually captured. Do not create placeholder evidence or claim unavailable evidence exists.

## Conclusion

This repository provides a structured record of selected manual QA observations, test results, potential issues, and improvement recommendations. It is intended to support further investigation, verification, and retesting by the development team.