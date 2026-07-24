## 2024-05-18 - Avoid Sync Layout Thrashing in Scroll Listeners
**Learning:** Using `getBoundingClientRect()` inside a `scroll` event listener forces the browser to synchronously recalculate layout (reflow) on every scroll tick, heavily blocking the main thread.
**Action:** Always replace scroll-based visibility checks with `IntersectionObserver`, which offloads these calculations from the main thread and provides a much smoother scrolling experience.
