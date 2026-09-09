## 2024-09-09 - Scroll Event Performance Bottleneck
**Learning:** Found a major performance bottleneck where a native `scroll` event listener coupled with `getBoundingClientRect()` was being used to trigger reveal animations. This causes forced synchronous layouts (layout thrashing) on the main thread for every single scroll event. The solution is using an `IntersectionObserver`.
**Action:** When implementing scroll-based interactions or visibility toggles, always default to `IntersectionObserver` instead of listening to global scroll events.
