# Learning Reflection

During this website QA audit, I practised exploring a live website from a user's perspective and checking how its visible components behave. I reviewed application-form validation, navigation elements, blog search and sharing, content rendering, KPI interactions, and product-page layout.

I learned that identifying an issue is only the first step. A useful bug report should explain the page and component, the action performed, the expected result, the actual result, and the impact on users. I also learned to distinguish a functional defect from a design choice that needs confirmation.

The audit highlighted the importance of testing boundary values and invalid inputs, checking whether interactive-looking elements actually work, and recording evidence. I also learned not to claim that a form submission, accessibility check, performance test, or security test passed unless I have directly tested it.

I also performed responsive layout checks using Chrome mobile emulation at a viewport of 400 × 608 CSS pixels. This helped me understand the importance of checking page alignment, navigation, form visibility, and horizontal scrolling on smaller screens.

For future testing, I would capture the browser version and viewport, use consistent test data, attach screenshots for reproducible issues, and retest every reported issue after a fix.