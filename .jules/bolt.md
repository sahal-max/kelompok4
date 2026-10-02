## 2024-05-24 - IntersectionObserver instead of scroll event
**Learning:** In scroll-based animations, attaching synchronous event listeners to the `scroll` event can cause layout thrashing and jank. The `.scroll-reveal` elements were checked synchronously on every frame.
**Action:** Replace `window.addEventListener('scroll', ...)` with an `IntersectionObserver` that asynchronously observes the elements and unobserves them once they intersect, reducing main thread blocking.
