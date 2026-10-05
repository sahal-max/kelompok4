## 2024-05-24 - Optimize Scroll Event Listeners with IntersectionObserver
**Learning:** Found a performance bottleneck where `window.addEventListener('scroll')` and `getBoundingClientRect()` were being executed excessively, causing main thread blocking.
**Action:** Replaced the scroll listener with `IntersectionObserver` which is heavily optimized for scroll-based interactions and requires less synchronous execution. Added a guard clause to return early if no target elements are found. Unobserving the target elements once revealed saves memory and CPU time.
