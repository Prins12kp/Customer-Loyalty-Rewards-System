# AI Interaction Log

## 1. Initial implementation request
**Prompt:** Build a rewards system dashboard covering purchase proof, fraud prevention, and factory-owner management.
**Outcome:** AI selected React and TypeScript, replaced the starter screen, and created a dashboard with metrics, rewards, redemption records, and fraud controls.
**Validation:** The app ran locally and the implementation was reviewed against all three requirement areas.

## 2. Assumptions documentation
**Prompt:** Document every assumption using `ASSUMPTIONS.md`.
**Outcome:** AI recorded assumptions for code-based purchase proof, points values, reuse rules, owner permissions, seeded data, and prototype scope.
**Validation:** Requirements were checked against the implementation and mocked versus production behavior was made explicit.

## 3. AI was wrong: search filter referenced an invalid method
**Prompt:** Implement search and status filtering for the redemption table.
**Notice of mistake:** The TypeScript build reported `Property 'toLower' does not exist on type 'string'` at the search expression.
**Fix:** AI replaced the typo with `toLowerCase()` and ran the build again. It also confirmed that search and status conditions combine correctly.

## 4. AI was wrong: CSS used an invalid z-index assignment
**Prompt:** Complete the application styles and verify the production build.
**Notice of mistake:** Vite Lightning CSS failed with `Unexpected token Delim('=')` in the toast CSS rule.
**Fix:** AI located `z-index=60`, corrected it to `z-index:60`, and rebuilt successfully. This was also verified with no remaining invalid-property search results.

## 5. Dashboard navigation interaction
**Prompt:** Add navigation between overview, rewards, customers, codes, and payouts without introducing unrelated routes.
**Outcome:** AI implemented view state and section placeholders while keeping the main overview as the complete dashboard.
**Validation:** Navigation buttons update the heading and panel content in the browser.

## 6. Responsive mobile layout
**Prompt:** Make the dashboard usable on desktop and mobile screens.
**Outcome:** AI added breakpoints that collapse sidebar labels and move navigation to the bottom on the smallest screens.
**Validation:** The CSS was reduced to mobile, tablet, and desktop rules and checked for build errors.

## 7. Repository requirements audit
**Prompt:** Review the repository against README, assumptions, architecture, testing, environment, and commit-history requirements.
**Outcome:** AI identified that the existing repository was not initialized with Git and that required documentation and test tooling still needed to be added.
**Validation:** AI planned and created the remaining documentation and test setup, then initialized Git for meaningful commits.

## 8. AI was wrong: test DOMs accumulated between cases
**Prompt:** Run the four automated component tests.
**Notice of mistake:** The first test run showed three failures because React Testing Library found duplicate dashboard elements. Earlier rendered DOM remained between test cases.
**Fix:** AI added Vitest `afterEach` cleanup in `src/test/setup.ts`. The suite was rerun and all four tests passed.

## 9. Test strategy and verification
**Prompt:** Add automated tests or a documented manual test plan with results.
**Outcome:** AI added a Vitest component suite, a test setup file, and a documented manual test matrix with pass/fail results.
**Validation:** The four automated tests pass and the production build remains available for manual and deployment testing.
