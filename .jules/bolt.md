## 2026-09-10 - Scroll Event Listener Bottleneck
**Learning:** Attaching a generic scroll event listener that repeatedly calls `getBoundingClientRect()` causes forced synchronous layouts (layout thrashing) and blocks the main thread on every scroll tick.
**Action:** Always replace generic scroll event listeners with `IntersectionObserver` when monitoring elements entering or leaving the viewport, and unobserve elements once they've been processed if the effect is one-time (like adding an `.active` class).
