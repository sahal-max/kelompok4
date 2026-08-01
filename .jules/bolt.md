## 2024-05-24 - Unconditional DOM Querying for Unused Classes
**Learning:** The previous scroll animation implementation unconditionally queried `.scroll-reveal` and added a `scroll` event listener, even though no elements actually used that class. This creates unnecessary performance overhead via main thread blocking and layout thrashing for features not currently in use.
**Action:** Always include a guard clause (e.g., `if (elements.length > 0)`) before setting up expensive observers or event listeners for DOM elements to avoid unnecessary processing when those elements are absent.
