## 2024-05-24 - Optimizing Scroll Reveal Animations
**Learning:** Attaching a synchronous `window.addEventListener('scroll', ...)` that triggers `getBoundingClientRect()` causes significant main thread blocking and layout thrashing (forced synchronous layout) on every scroll tick.
**Action:** Always replace scroll-bound visibility checks with `IntersectionObserver`, which offloads the calculations off the main thread, and remember to `unobserve` elements after they are revealed to free up resources.
