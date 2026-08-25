## 2026-08-25 - Replace synchronous scroll listener with IntersectionObserver
**Learning:** The existing codebase was using synchronous DOM reads (`getBoundingClientRect()`) on every scroll event to trigger the reveal animation, leading to main thread blocking and layout thrashing.
**Action:** Replaced the scroll listener with `IntersectionObserver` to offload the intersection checks from the main thread, greatly improving scroll performance.
