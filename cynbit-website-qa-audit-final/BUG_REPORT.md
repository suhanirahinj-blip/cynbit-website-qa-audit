# Bug & Issue Report

**Website:** https://www.cynbit.in/  
**Report date:** 23 November 2026  
**Status convention:** Open – reported from manual observation; not independently verified by the development team.  
**Severity/priority:** Initial estimates only; confirm with the product owner.

---

## BUG-001: Application form provides insufficient validation feedback

- **Page:** Careers – job application form (specific role page to be noted for each reproduction)
- **Module:** Job Application Form
- **Category:** Functional – Form Validation / Usability
- **Severity / Priority:** Medium / P2 (provisional)
- **Preconditions:** Open a job application form.
- **Steps observed:**
  1. Attempt to submit the form with required information missing.
  2. Enter an invalid email value such as `abc123` and attempt validation.
  3. Leave the resume link empty or enter an invalid value such as `abc123`.
- **Expected:** Each invalid or missing field should have a clear, field-specific message explaining how to correct it. The invalid field should be visually identified and announced accessibly.
- **Actual:** The page scrolls to or highlights fields such as First Name, Email, and Resume Link, but no clear explanatory validation message is shown. The resume field blocks the invalid/empty value but does not explain the error.
- **Impact:** Applicants may not understand what needs correction and may abandon the form.
- **Recommendation:** Display concise inline validation messages, associate them with their fields, and provide an accessible error summary when appropriate.
- **Evidence:** Add an actual screenshot to `test-evidence/screenshots/` and record its filename here.
- **Verification note:** Do not claim a successful or failed backend submission unless it was safely and directly observed.

## BUG-002: Name and phone fields lack clear validation for invalid-looking inputs

- **Page:** Careers – job application form
- **Module:** Applicant Details
- **Category:** Functional – Input Validation
- **Severity / Priority:** Medium / P2 (provisional)
- **Steps observed:**
  1. Enter a clearly invalid-looking name value (the notes mention a special-character test).
  2. Enter alphabetic characters such as `abcdef` in the phone field.
  3. Observe the form's validation feedback.
- **Expected:** The form should validate the name and phone fields according to documented business rules and show clear messages for invalid values. Phone input should reject alphabetic characters.
- **Actual:** The tested name/phone inputs did not produce clear field-level validation messages. The notes indicate the form appeared to accept invalid-looking values, but do not establish that a real application was successfully submitted.
- **Impact:** Incorrect applicant contact details may be entered, potentially preventing recruiters from contacting applicants.
- **Recommendation:** Define field rules, validate on both client and server, and display field-specific errors. Do not reject legitimate names containing apostrophes, hyphens, spaces, or non-English characters.
- **Evidence:** Add actual screenshots if available.
- **Verification note:** Re-test using a clearly invalid phone value and safe dummy data. Stop before final submission if it would transmit a real application.

## BUG-003: BitElevate card appears interactive but is not clickable

- **Page:** https://www.cynbit.in/bitelevate
- **Module:** BitElevate card
- **Category:** UI/UX – Interaction / Visual Affordance
- **Severity / Priority:** Medium / P2 (provisional)
- **Steps observed:**
  1. Open the BitElevate page.
  2. Click the highlighted BitElevate card.
  3. Click its “True software engineering proof” text/arrow area.
  4. Hover over the other cards.
- **Expected:** If the card is styled to look interactive, it should provide a working action. If it is static, its styling should not misleadingly suggest clickability.
- **Actual:** The highlighted card and its text/arrow were reported as not clickable. The highlighted styling appears by default, while the other cards do not highlight on hover.
- **Impact:** Visitors may expect navigation or an action and become confused.
- **Recommendation:** Make the card a semantic link/button with a clear destination, or remove misleading interactive styling.
- **Evidence:** Add actual screenshot/recording if available.
- **Verification note:** Confirm with the design owner whether the card is intended to be interactive or merely featured.

## BUG-004: Practical Specialization Track options are not clickable

- **Page:** https://www.cynbit.in/
- **Module:** Practical Specialization Tracks – “Choose Your Track”
- **Elements:**
  - Full-Stack Web Development
  - UI/UX Product Design
  - Python & AI Systems
- **Category:** Functional – Navigation / Interaction
- **Severity / Priority:** Medium / P2 (provisional)
- **Expected:** Each track card or its arrow should navigate to relevant details or perform its clearly indicated action.
- **Actual:** The three track options were reported as not clickable.
- **Impact:** Visitors cannot proceed directly from the track section to learn more or select a track.
- **Recommendation:** Add working links/actions to each track, or remove visual cues that imply clickability.
- **Evidence:** Add actual screenshot/recording if available.
- **Verification note:** Confirm the intended design behaviour and test both card body and arrow.

## BUG-005: Data Privacy Advantage blog article appears to have incomplete content

- **Page:** https://www.cynbit.in/blog/data-privacy-advantage
- **Module:** Blog Article Content
- **Category:** Content – Rendering / Completeness
- **Severity / Priority:** Medium / P2 (provisional)
- **Expected:** The article should display its complete approved content, consistent with the site's intended article layout.
- **Actual:** The user reported that this article has little/limited content while other articles display more content; an author information card is visible.
- **Impact:** Readers may be unable to access the complete article.
- **Recommendation:** Check the CMS/content record, article template, and rendering of the article body. Compare against the approved source content.
- **Evidence:** Add actual screenshot(s) showing the article and comparison article.
- **Verification note:** The content owner should confirm the expected article length; a short article is not automatically a defect.

## BUG-006: Blog article Share button does not work

- **Page:** https://www.cynbit.in/blog/data-privacy-advantage
- **Module:** Share Functionality
- **Category:** Functional – Social Sharing
- **Severity / Priority:** Medium / P2 (provisional)
- **Expected:** Clicking Share should open the intended share options, copy the article URL, or perform the action indicated by the control.
- **Actual:** The Share button was reported as not working.
- **Impact:** Visitors may be unable to share the article easily.
- **Recommendation:** Implement the intended share action, provide a fallback copy-link action, and show feedback after copying.
- **Evidence:** Add actual screenshot/recording if available.
- **Verification note:** Record browser/device and whether the click has no response, an error, or a blocked popup.

## BUG-007 – Blog Search Result for Term "one" Is Unexpected

- **Page:** https://www.cynbit.in/blog
- **Area:** Blog search
- **Priority:** P2 (provisional)
- **Status:** Needs investigation; not confirmed

**Test observations:**

| Search input | Actual result |
|---|---|
| xyz987 | No results found |
| qwerty987654 | No results found |
| one | All blog articles displayed |

**Expected:** Search results should match the documented search scope and query-matching rules.

**Notes:** The term "one" may occur in every article or match content beyond titles. Investigate search indexing, tokenisation and search scope before classifying this as a confirmed defect.

## BUG-008: CGPA Score Value accepts zero despite displayed 1–10 scale

- **Page:** https://www.cynbit.in/careers/full-stack-developer
- **Module:** Job Application Form – Academic Details
- **Field:** Score Value
- **Category:** Functional – Boundary / Input Validation
- **Severity / Priority:** Medium / P2 (provisional)
- **Test input:** `0`
- **Displayed scale:** CGPA (Scale 1–10)
- **Expected:** If the selected score system explicitly defines a minimum of 1, zero should be rejected with a clear validation message.
- **Actual:** The Score Value field was reported to accept `0`.
- **Impact:** Applicants may enter a score outside the displayed scale.
- **Recommendation:** Enforce minimum and maximum values consistent with the selected score system and validate on both client and server.
- **Evidence:** Add actual screenshot showing the selected scale and entered value.
- **Verification note:** Confirm whether zero is accepted only in the field or also passes form submission. The expected range should be confirmed with the product owner.

## BUG-009: Case-study KPI elements do not open on the first click

- **Page:** https://www.cynbit.in/case-studies
- **Module:** KPI section
- **Category:** Functional – Interaction
- **Severity / Priority:** Medium / P2 (provisional)
- **Expected:** If the KPI elements are interactive, their details should open on the first click.
- **Actual:** KPIs were reported as not opening with one click.
- **Impact:** Visitors may need repeated attempts or may not discover the related information.
- **Recommendation:** Verify event handling, clickable area, and keyboard interaction. If KPIs are not intended to be interactive, remove affordances that imply they are.
- **Evidence:** Add a short recording or screenshot if available.
- **Verification note:** The user did not confirm whether a second click opens the KPI or whether it never opens. Re-test and document the exact result before developer handoff.

## BUG-010: TenantEase product information alignment differs from other product sections

- **Page:** https://www.cynbit.in/products#tenantease
- **Module:** Product Information Sections
- **Category:** UI/UX – Layout Consistency
- **Severity / Priority:** Low / P3 (provisional)
- **Expected:** Product sections should follow the intended consistent layout pattern across Cynbit Studio, Revio, and TenantEase.
- **Actual:** TenantEase information appears on the right, while Cynbit Studio and Revio information appears on the left.
- **Impact:** The section may look visually inconsistent if the differing alignment is unintended.
- **Recommendation:** Confirm the approved design. If all sections should align consistently, correct the layout; if alternating alignment is intentional, retain it.
- **Evidence:** Add a full-page or section screenshot showing all three product sections.
- **Verification note:** Alternating left/right layouts are common design patterns and may be intentional. Do not classify as a confirmed defect without design confirmation.


## Mobile Responsive Testing – Additional Observations

**Testing environment:** Chrome mobile emulation, viewport 400 × 608 CSS pixels.

| Test area | Actual result | Status |
|---|---|---|
| Homepage layout | Properly aligned | Passed |
| Careers form layout | Fields and Submit button visible; no overlap | Passed |
| Blog layout | Properly aligned | Passed |
| Products layout | Cynbit Studio, Revio and TenantEase displayed properly | Passed |
| Homepage horizontal scrolling | No horizontal scrolling observed | Passed |
| Careers form visibility | Fields and Submit button displayed properly | Passed |
| Mobile navigation | Menu opens, links are visible and usable, menu closes after selection | Passed |
| Empty form submission | Highlights/scrolls to field without clear error message | Issue observed |
| Invalid email submission | Highlights/scrolls to email field without clear error message | Issue observed |
| CGPA score 0 | Accepted as field input for CGPA scale 1–10 | Issue observed |

**Note:** Mobile testing was performed using browser emulation, not a physical mobile device.