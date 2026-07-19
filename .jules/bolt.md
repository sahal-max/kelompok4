## 2024-05-24 - Layout Thrashing in Scroll Animations
**Learning:** Using `getBoundingClientRect()` inside an unthrottled `scroll` event listener causes severe layout thrashing (synchronous layout recalculations) and blocks the main thread. This is a common anti-pattern for "scroll to reveal" animations that degrades scrolling performance.
**Action:** Always prefer `IntersectionObserver` over `scroll` events for element visibility detection, as it offloads the calculations to the browser's optimized internal mechanics and doesn't block the main thread.
