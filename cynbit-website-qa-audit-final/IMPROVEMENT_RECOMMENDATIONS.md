# Improvement Recommendations

These recommendations are based on the ten observations recorded during the manual website audit. They are suggestions for investigation and improvement, not confirmed root causes. Items requiring design or business-rule confirmation should be reviewed with the relevant product owner or development team.

---

## Priority 1 – Functional Clarity and Data Validation

### 1. Improve Application-Form Validation (BUG-001, BUG-002)

- Display a clear inline message beside each invalid or missing field.
- Associate validation messages with inputs using accessible labels and error descriptions.
- Preserve entered values when validation fails.
- Validate input on both client and server sides.
- Define phone and name validation rules carefully. Support legitimate international names, including apostrophes, hyphens, spaces, and non-English characters.
- Validate phone numbers according to appropriate international formats rather than assuming one fixed format.
- Provide a clear summary of errors when the user attempts submission.

### 2. Enforce Academic Score Boundaries (BUG-008)

- Confirm the business rule for CGPA (Scale 1–10).
- If the minimum is 1, reject zero and values outside the selected scale.
- Display a concise message explaining the accepted range.
- Add boundary tests for minimum, maximum, below-minimum, and above-maximum values.
- Ensure the same validation rules are applied on both client and server sides.

### 3. Repair or Clarify Interactive Elements (BUG-003, BUG-004, BUG-006, BUG-009)

- Ensure interactive cards and controls use semantic links or buttons.
- Make the intended clickable area consistent with the visual design.
- Provide keyboard access and visible focus states for interactive elements.
- Ensure the Share control performs its intended action and provides feedback to the user.
- Confirm what the Case Studies KPI elements are intended to do. Implement the expected behaviour or remove misleading interactive cues.
- Confirm whether the BitElevate card and Practical Specialization Track options are intended to be interactive. If they are static, their appearance should not imply otherwise.

---

## Priority 2 – Search and Content Experience

### 4. Verify Blog Search Behaviour (BUG-007)

- Confirm which fields are searched: title, article body, tags, or all of these.
- Ensure the search query is applied correctly when the user types or submits it.
- Show a clear no-results message when no content matches.
- Add tests for matching terms, non-matching terms, empty input, case differences, and partial words.
- Investigate why the search term `one` displays all articles before treating the behaviour as a confirmed defect.

### 5. Verify Article Content Completeness (BUG-005)

- Compare the rendered article with the approved CMS or source content.
- Check whether the article body is missing, unpublished, or not rendered by the page template.
- Ensure the article layout handles short and long content consistently without hiding content.
- Ask the content owner to confirm the expected article content before classifying it as incomplete.

---

## Priority 3 – Visual Consistency and Design Confirmation

### 6. Review Product-Section Alignment (BUG-010)

- Ask the design owner whether the TenantEase right-side placement is intentional.
- If it is not intentional, align the section with the approved product-page design.
- If alternating layouts are intentional, preserve them and ensure spacing, alignment, and responsiveness remain consistent.
- Check the layout at different viewport sizes to ensure that the content remains readable and properly aligned.

---

## General Quality Improvements

- Maintain consistent hover, active, and focus states across interactive elements.
- Use descriptive link text and accessible names for icon-only controls.
- Test navigation and interactive controls using a keyboard as well as a mouse.
- Check responsive behaviour at representative mobile, tablet, and desktop viewport sizes.
- Perform accessibility checks for labels, focus visibility, keyboard navigation, and validation announcements.
- Run Lighthouse and record actual metrics before making performance claims.
- Retest each issue after a fix and attach genuine before-and-after evidence.
- Maintain a regression test checklist for previously reported issues.

---

## Important Notes

1. These recommendations are based on manual observations and do not establish the underlying technical causes.
2. Priority levels are provisional and should be reviewed by the development team.
3. Items involving intended design behaviour or business rules require confirmation before implementation.
4. Accessibility