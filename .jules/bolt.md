## 2024-09-08 - IntersectionObserver Guard Clause
**Learning:** Found an anti-pattern where a main-thread blocking `scroll` event listener and `getBoundingClientRect` logic was executed continuously, even when no elements matching the target class (`.scroll-reveal`) existed in the DOM.
**Action:** Always include a guard clause (e.g., `if (elements.length > 0)`) before initializing observers or expensive event listeners to prevent unnecessary overhead when the feature is unused.
