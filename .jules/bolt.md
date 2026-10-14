## 2025-01-20 - [Scroll Event Anti-Pattern]
**Learning:** Attaching a scroll event listener that calls `getBoundingClientRect()` inside the callback causes severe layout thrashing and main-thread blocking, leading to poor scrolling performance and jank.
**Action:** Always replace scroll-based visibility checks with `IntersectionObserver`. It's asynchronous and doesn't block the main thread.