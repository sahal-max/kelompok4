
## 2024-05-18 - Replacing scroll event listeners with IntersectionObserver
**Learning:** Using `getBoundingClientRect` inside a `scroll` event listener causes layout thrashing (forced synchronous layout), significantly blocking the main thread during scrolling. This is a common performance anti-pattern in vanilla JS implementations for scroll-reveal effects.
**Action:** Always prefer `IntersectionObserver` over `scroll` event listeners for elements that need to react to viewport intersection. It offloads the intersection calculation from the main thread and avoids synchronous layout reads.
