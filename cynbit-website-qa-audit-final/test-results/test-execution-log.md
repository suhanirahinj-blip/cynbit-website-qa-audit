# Test Execution Log

**Application:** Cynbit Website  
**Website:** https://www.cynbit.in/  
**Execution Date:** 23 November 2026  
**Execution Type:** Manual Exploratory Testing  
**Tester:** Candidate-led manual review

## Session Summary

Selected website pages and workflows were manually explored. The results below are based on observations recorded during the audit.

Desktop viewport dimensions, exact browser version, and network details were not recorded. Mobile responsive checks were performed using Google Chrome mobile emulation at 400 × 608 CSS pixels.

## Test Execution Results

| Test ID | Area | Input / Action | Result Recorded | Status |
|---|---|---|---|---|
| TC-001 | Careers Form | Submit empty form | Page scrolls/highlights First Name without clear explanatory feedback | Fail – Observed |
| TC-002 | Careers Form | Enter invalid email `abc123` | Email is highlighted/scrolled to; no explanatory message appears | Fail – Observed |
| TC-003 | Careers Form | Enter alphabetic phone value `abcdef` | No clear field-level validation message observed | Needs Retest |
| TC-004 | Careers Form | Enter previously tested unusual/special-character name value | No clear validation feedback observed | Needs Verification |
| TC-005 | Careers Form | Attempt validation with multiple incomplete fields | Page scrolls to applicant information without clear field-specific messages | Needs Verification |
| TC-006 | Careers Form | Leave Resume Link empty | Field highlighted and progress blocked; no explanatory message | Fail – Observed |
| TC-007 | Careers Form | Enter invalid Resume Link `abc123` | Field highlighted and progress blocked; no explanatory message | Fail – Observed |
| TC-008 | Careers Form | Enter valid Cynbit Careers URL as Resume Link | URL accepted in the field | Pass – Field Acceptance Only |
| TC-009 | Full-Stack Developer Application | Select CGPA scale 1–10 and enter Score Value `0` | Field reported to accept 0 | Issue Observed – Submission Not Confirmed |
| TC-010 | BitElevate | Click highlighted card and text/arrow; hover over other cards | Highlighted card reported as not clickable and highlighted by default | Needs Design Confirmation |
| TC-011 | Homepage | Click three specialization track options | All three options reported as not clickable | Needs Design Confirmation |
| TC-012 | Blog Article | Open Data Privacy Advantage | Article reported to have less content than other articles | Needs Content-Owner Confirmation |
| TC-013 | Blog Article | Click Share | Share button reported as not working; exact response not recorded | Needs Retest |
| TC-014 | Blog Listing | Search for `one` | All blog articles displayed | Needs Investigation |
| TC-015 | Case Studies | Click KPI once | KPI reported not to open on first click | Needs Verification |
| TC-016 | Products | Compare three product sections | TenantEase appears right-aligned; Cynbit Studio and Revio appear left-aligned | Design Review Required |

## Additional Blog Search Retest

| Search Input | Actual Result | Status |
|---|---|---|
| `xyz987` | No results found | Observed – Expected Result |
| `qwerty987654` | No results found | Observed – Expected Result |
| `one` | All blog articles displayed | Needs Investigation |

The search behaviour for `one` requires further investigation. It may match content present in multiple articles or search beyond article titles. It is not yet confirmed as a defect.

## Additional Mobile Test Execution

**Execution Date:** 23 November 2026  
**Browser:** Google Chrome  
**Device Mode:** Mobile emulation  
**Viewport:** 400 × 608 CSS pixels

| Test ID | Test Scenario | Actual Result | Status |
|---|---|---|---|
| MOB-001 | Homepage responsive layout | Layout appeared properly aligned | Passed |
| MOB-002 | Careers form responsive layout | Fields and Submit button were visible without reported overlap or cut-off | Passed |
| MOB-003 | Blog responsive layout | Layout appeared properly aligned | Passed |
| MOB-004 | Products responsive layout | All three product sections displayed properly | Passed |
| MOB-005 | Homepage horizontal scrolling | No horizontal scrolling observed | Passed |
| MOB-006 | Mobile navigation | Menu opened, links were visible and usable, and menu closed after selection | Passed |
| MOB-007 | Empty Careers form validation | Field highlighted and page scrolled; no clear error message appeared | Issue Observed |
| MOB-008 | Invalid email validation | Email field highlighted and page scrolled; no clear error message appeared | Issue Observed |
| MOB-009 | CGPA score value `0` | Value accepted as field input | Issue Observed – Submission Not Confirmed |

## Evidence Handling

Add only screenshots or recordings actually captured during testing.

**Evidence folders:**

- `test-evidence/screenshots/`
- `test-evidence/recordings/`

Reference the exact filenames in the relevant test case or bug report after adding the evidence.

Do not create placeholder evidence or claim that screenshots or recordings exist if they were not captured.

## Execution Limitations

- A field accepting text does not prove that a server-side form submission succeeds.
- The CGPA observation confirms field-level input acceptance only. Server-side validation has not been verified.
- The final application submission should not be attempted using real personal data or without authorization.
- Some findings require confirmation of intended design, content, or business rules.
- Mobile results represent Chrome mobile emulation, not testing on a physical mobile device.
- No automated test execution, backend verification, performance testing, or security testing is claimed.
- Exact browser version, operating-system build, desktop viewport, and network conditions were not recorded.
- Findings should be reproduced and verified before being treated as confirmed defects.

## Execution Summary

The audit covered 16 exploratory test cases and 9 additional mobile checks. Several usability and validation observations were recorded. Some results require retesting or confirmation of the intended website behaviour.

The execution log records the observations made during the audit and does not claim that unexecuted or unverified tests have passed.