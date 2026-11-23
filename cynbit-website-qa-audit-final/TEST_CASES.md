# Test Cases

**Website:** https://www.cynbit.in/  
**Type:** Exploratory manual test cases  
**Status note:** “Observed” reflects the user's reported observation; it is not an independent automated test result.

| Test ID | Page / Module | Scenario | Test data / action | Expected result | Recorded observation | Status |
|---|---|---|---|---|---|---|
| TC-001 | Careers form | Submit with required fields empty | Leave required fields blank and attempt validation | Required fields show clear messages | Page scrolls/highlights First Name without a clear explanatory message | Fail – observed |
| TC-002 | Careers form | Validate email format | Enter `abc123` | Clear invalid-email message | Email field is highlighted/scrolled to, but no explanatory message appears | Fail – observed |
| TC-003 | Careers form | Validate phone input | Enter alphabetic value such as `abcdef` | Phone rejects letters and explains valid format | No clear phone validation message was observed | Fail – observed; re-test |
| TC-004 | Careers form | Validate name input | Enter the previously tested unusual/special-character value | Apply documented name rules and show feedback | No clear validation feedback was observed | Needs verification |
| TC-005 | Careers form | Validate multiple missing/invalid fields | Attempt validation with multiple incomplete fields | Each relevant field is clearly identified | Page scrolls to applicant information without clear field-specific explanations | Fail – observed |
| TC-006 | Careers form | Validate empty resume link | Leave Resume Link blank | If mandatory, show a required-field message | Form highlights Resume Link and blocks progress, but no explanatory message appears | Fail – observed |
| TC-007 | Careers form | Validate invalid resume URL | Enter `abc123` | Reject invalid URL with clear message | Form highlights Resume Link and blocks progress, but no explanatory message appears | Fail – observed |
| TC-008 | Careers form | Accept URL-formatted resume value | Enter `https://www.cynbit.in/careers/digital-marketing-intern` | Accept syntactically valid URL | URL was accepted in the field | Pass – field acceptance only |
| TC-009 | Full-Stack Developer application | Validate CGPA lower boundary | Select CGPA (Scale 1–10), enter `0` | Reject value below 1 | Score Value was reported to accept 0 | Fail – observed; submission not confirmed |
| TC-010 | BitElevate | Test highlighted card interaction | Click card and its text/arrow | Intended action works, or card is styled as static | Card/text/arrow reported not clickable; highlight appears by default | Needs design confirmation |
| TC-011 | Homepage | Test specialization track cards | Click Full-Stack, UI/UX, and Python & AI options | Each intended track action works | All three options reported not clickable | Fail – observed |
| TC-012 | Blog article | Check article body completeness | Open Data Privacy Advantage and compare with other articles | Complete approved article body renders | Article reported to have limited/missing content compared with others | Needs content-owner confirmation |
| TC-013 | Blog article | Test Share action | Click Share | Intended sharing action or copy-link feedback occurs | Share button reported not working | Fail – observed; exact response not recorded |
| TC-014 | Blog listing | Test search filtering | Search for random term `one` | Results follow defined search rules; unrelated results should not appear | All options reportedly remain visible | Needs re-test of Enter/search-button behaviour |
| TC-015 | Case Studies | Test KPI interaction | Click a KPI once | If interactive, details open on first click | KPI reported not to open on one click | Needs verification; second-click behaviour unknown |
| TC-016 | Products | Compare product-section alignment | Compare Cynbit Studio, Revio, TenantEase | Layout follows approved design | TenantEase appears right-aligned; other two appear left-aligned | Design review required |

## Additional suggested tests (not executed / no result recorded)
- Check all header, footer, social, and in-page links.
- Test all navigation dropdowns and mobile menu.
- Check form field labels, required indicators, keyboard navigation, and focus visibility.
- Test responsive layout at actual desktop, tablet, and mobile viewport sizes.
- Run Lighthouse and record actual results if required and available.
- Check page loading and image rendering on a normal network.
- Verify no horizontal overflow on mobile.
- Retest all reported issues after fixes.

Testing Notes

A Pass result for TC-008 confirms only that the URL was accepted in the field. It does not confirm successful form submission.
TC-009 records field-level acceptance of zero. Server-side acceptance has not been verified.
TC-010 and TC-011 require confirmation of the intended design before being classified as functional defects.
TC-012 requires comparison with approved article content.
TC-014 requires investigation of the blog search matching rules before confirming a defect.
TC-015 requires another test to establish whether a second click opens the KPI.
Suggested tests listed above must not be treated as completed tests.

