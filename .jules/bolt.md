## 2024-05-24 - Layout Thrashing with Scroll Events
**Learning:** Using `window.addEventListener('scroll')` with `getBoundingClientRect()` synchronously on every scroll event in a static site like this causes severe layout thrashing, as it forces the browser to recalculate styles and layout continuously on the main thread.
**Action:** Always prefer `IntersectionObserver` for scroll-based visibility checks, and include a negative `rootMargin` to simulate the `- 150` pixels threshold logic cleanly. Unobserve targets once they are visible to further reduce CPU load.
