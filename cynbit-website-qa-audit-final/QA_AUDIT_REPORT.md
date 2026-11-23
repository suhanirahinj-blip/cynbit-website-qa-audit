# Cynbit Website – QA Audit Report

## 1. Executive Summary

A manual review was performed on selected Cynbit website pages and workflows. Ten potential issues were recorded from observed behaviour involving application-form validation, non-clickable interface elements, blog content and search, sharing functionality, KPI interaction, and product-section alignment.

The findings are based on manual observations. Functional findings should be reproduced before release decisions are made. The TenantEase alignment finding may be intentional, and the KPI interaction finding requires confirmation of the expected behaviour.

Mobile responsive checks were also performed using Chrome mobile emulation at a viewport of 400 × 608 CSS pixels. The tested layouts displayed correctly, with no horizontal scrolling or overlapping elements observed in the tested areas.

No claim is made that all website pages, browsers, devices, accessibility criteria, performance characteristics, or security controls were exhaustively tested.

## 2. Audit Details

| Item | Details |
|---|---|
| Website | https://www.cynbit.in/ |
| Audit Date | 23 November 2026 |
| Audit Type | Manual Website QA Audit |
| Primary Focus | Functional behaviour, form validation, navigation, content rendering, usability, responsive layout, and visual consistency |
| Potential Findings Recorded | 10 |
| Mobile Testing | Chrome mobile emulation |
| Mobile Viewport | 400 × 608 CSS pixels |
| Test Evidence | Add only screenshots actually captured to `test-evidence/screenshots/` |

## 3. Scope

The audit covered selected pages and workflows:

- **Homepage:** Practical Specialization Tracks and mobile navigation.
- **BitElevate Page:** Highlighted BitElevate card and its apparent interactive behaviour.
- **Blog Listing:** Search behaviour.
- **Blog Article:** Data Privacy Advantage content and Share functionality.
- **Careers Application Forms:** Field validation, name and phone inputs, and academic score validation.
- **Case Studies:** KPI interaction.
- **Products Page:** Cynbit Studio, Revio, and TenantEase section alignment and responsive layout.

## 4. Out of Scope / Not Verified

The following activities were not performed or were not established by the available test evidence:

- Source-code review.
- Backend or database validation.
- API testing.
- Authentication and authorization testing.
- Penetration testing or vulnerability scanning.
- Load and stress testing.
- Comprehensive cross-browser testing.
- Automated accessibility audit.
- Measured performance testing using Lighthouse or Core Web Vitals.
- Successful production job-application submission.
- Physical mobile device testing.

## 5. Test Approach and Methodology

The following manual testing approach was used:

1. Opened selected public website pages in a browser.
2. Interacted with visible cards, links, search controls, and Share controls.
3. Entered sample invalid values in application-form fields where described in the observation notes.
4. Checked the visible response of form validation and input fields.
5. Compared observed behaviour with expected user-facing behaviour.
6. Checked selected page layouts and navigation using Chrome mobile emulation.
7. Recorded potential findings with provisional severity and priority where impact or intended behaviour requires confirmation.

This was exploratory manual testing. Not all test cases were executed under a controlled or fully recorded environment.

## 6. Test Environment

Refer to `TEST_ENVIRONMENT.md` for the available environment details.

Known details:

- Browser: Google Chrome.
- Operating System: Windows.
- Mobile Testing: Chrome mobile emulation.
- Mobile Viewport: 400 × 608 CSS pixels.

The exact Chrome version, Windows edition/build, desktop viewport, and network conditions were not recorded.

## 7. Findings Summary

| ID | Finding | Area | Initial Priority |
|---|---|---|---|
| BUG-001 | Application form provides insufficient field-level validation feedback | Careers Form | P2 |
| BUG-002 | Name and phone inputs lack clear validation feedback for invalid-looking values | Careers Form | P2 |
| BUG-003 | BitElevate card appears interactive but is not clickable | BitElevate Page | P2 |
| BUG-004 | Three Practical Specialization Track options are not clickable | Homepage | P2 |
| BUG-005 | Data Privacy Advantage article appears to have limited content | Blog Article | P2 |
| BUG-006 | Share button does not work as expected | Blog Article | P2 |
| BUG-007 | Search term `one` displays all blog articles | Blog Listing | P2 – Needs Investigation |
| BUG-008 | CGPA score field accepts 0 despite displayed 1–10 scale | Careers Application Form | P2 |
| BUG-009 | KPI elements were reported as not opening on the first click | Case Studies | P2 – Needs Verification |
| BUG-010 | TenantEase information alignment differs from other product sections | Products Page | P3 – Design Confirmation Required |

All severity and priority classifications are provisional and should be confirmed by the product owner or development team.

## 8. Detailed Findings

Refer to `BUG_REPORT.md` for the complete details of each finding, including:

- Page and module.
- Reproduction steps.
- Expected behaviour.
- Actual observed behaviour.
- User impact.
- Recommendations.
- Evidence requirements.
- Verification notes.

## 9. Mobile Responsive Testing

Mobile layout checks were performed using Chrome mobile emulation at a viewport of 400 × 608 CSS pixels.

| Test Area | Actual Result | Status |
|---|---|---|
| Homepage layout | Properly aligned | Passed |
| Careers form layout | Fields and Submit button visible; no overlap | Passed |
| Blog layout | Properly aligned | Passed |
| Products layout | Cynbit Studio, Revio, and TenantEase displayed properly | Passed |
| Homepage horizontal scrolling | No horizontal scrolling observed | Passed |
| Careers form visibility | Fields and Submit button displayed properly | Passed |
| Mobile navigation | Menu opens, links are visible and usable, and menu closes after selection | Passed |
| Empty form submission | Highlights/scrolls to field without a clear error message | Issue Observed |
| Invalid email submission | Highlights/scrolls to email field without a clear error message | Issue Observed |
| CGPA score `0` | Accepted as field input for CGPA scale 1–10 | Issue Observed |

**Mobile Testing Note:** Testing was performed using browser emulation, not a physical mobile device. These results do not establish compatibility across all mobile devices or browsers.

## 10. Test Coverage and Limitations

The available notes describe selected exploratory checks, not a complete test of every page or field.

Important limitations include:

- The final server-side submission outcome of the careers form was not established.
- The invalid-looking name and phone inputs require further verification against documented validation rules.
- The intended interaction for the Case Studies KPI elements was not confirmed.
- The alternating TenantEase product-section alignment may be a deliberate design pattern.
- The blog search result for `one` requires investigation. The search scope and matching rules were not established.
- The Data Privacy Advantage article's completeness should be checked against the content owner's approved source.
- The BitElevate card may be intentionally featured. Its lack of click behaviour is a usability concern only if its styling implies an action.
- Screenshots and recordings should be attached only when they have actually been captured.

## 11. Recommendations

Refer to `IMPROVEMENT_RECOMMENDATIONS.md` for detailed recommendations.

The main areas for improvement include:

1. Clearer application-form validation messages.
2. Consistent input validation and academic score boundaries.
3. Working or clearly non-interactive cards and controls.
4. Verification of blog search and Share functionality.
5. Confirmation of article content completeness.
6. Review of KPI behaviour and product-section alignment.
7. Additional accessibility and responsive testing.

## 12. Conclusion

The manual audit identified ten areas requiring follow-up. The next step is for the development team to reproduce the form-validation, search, Share, and interaction findings and confirm the intended behaviour of the KPI and product-layout observations.

Genuine screenshots and recordings should be attached wherever available. Each reported issue should be retested after a fix, with the result documented before the audit is treated as complete.

This report documents selected manual QA observations and is not a comprehensive website certification or release sign-off.