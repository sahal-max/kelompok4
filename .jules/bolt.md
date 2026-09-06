## 2024-05-15 - IntersectionObserver Fallback
**Learning:** When replacing synchronous scroll listeners with IntersectionObserver, elements that are already in the viewport or above it (e.g. after a page reload preserving scroll position) might not trigger the initial `isIntersecting` callback if the observer only watches for edges crossing the threshold.
**Action:** Always include a fallback check `entry.boundingClientRect.top < 0` inside the IntersectionObserver callback to ensure elements already scrolled past are properly processed.
