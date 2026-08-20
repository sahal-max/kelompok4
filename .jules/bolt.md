## 2024-08-20 - IntersectionObserver Optimization
**Learning:** When dynamically injecting test elements into `index.html` for Playwright validation, the Intersection Observer defined in the page's original script must be re-evaluated and bound within the test context. Native scripts execute synchronously on load, missing elements injected dynamically later.
**Action:** When validating IntersectionObserver logic with Playwright in static pages, always re-bind the observer to the dynamically created elements during the test's `page.evaluate()` step.
