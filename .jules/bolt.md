
## 2024-05-20 - IntersectionObserver Edge Cases
**Learning:** In this architecture, utility classes like `.scroll-reveal` might not be used initially, meaning standard `IntersectionObserver` setups could attach empty observers. Furthermore, testing negative root margins in Playwright requires explicit padding injection to allow sufficient scrolling.
**Action:** Always include a guard clause (e.g., `if (elements.length === 0) return;`) before initializing observers to save memory. When writing E2E tests for scroll behaviors with negative margins, inject spacer elements to ensure the page has enough height to trigger the intersection.
