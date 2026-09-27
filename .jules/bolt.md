
## 2024-05-24 - Replacing Scroll Events with IntersectionObserver
**Learning:** In purely static architectures (like this single `index.html` setup) where synchronous scroll event listeners cause severe main-thread blocking and layout thrashing (due to `getBoundingClientRect()` on every scroll), replacing them with an `IntersectionObserver` is a critical performance win.
**Action:** When migrating scroll events to `IntersectionObserver`, always implement a guard clause (`if (elements.length === 0) return;`) to avoid observer initialization overhead when unused, and include `obs.unobserve(entry.target)` inside the callback to reclaim memory once the animation completes.
