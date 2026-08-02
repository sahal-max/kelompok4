## 2024-06-25 - Scroll Listener Layout Thrashing
**Learning:** Found a critical bottleneck where `getBoundingClientRect()` was called inside a `scroll` event listener on `index.html`. This causes severe layout thrashing (forced synchronous layout) and blocks the main thread.
**Action:** Replace `scroll` event listeners that check element visibility with `IntersectionObserver`. Also, remember to add a check for `entry.boundingClientRect.top < 0` to ensure elements already scrolled past are correctly processed (e.g., on page reload).
