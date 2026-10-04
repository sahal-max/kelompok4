## 2024-06-25 - IntersectionObserver Over Scroll Event Listeners
**Learning:** Synchronous `scroll` event listeners attached to the window can cause severe layout thrashing and block the main thread, especially when running `getBoundingClientRect()` repeatedly on every scroll tick.
**Action:** Always replace scroll-bound visibility checks with `IntersectionObserver`. Additionally, always include a guard clause (e.g., `if (elements.length === 0) return;`) to avoid creating the observer if the target elements do not exist in the DOM, saving memory and processing overhead.
