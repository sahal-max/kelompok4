## 2026-08-31 - IntersectionObserver over Scroll Listeners
**Learning:** Replaced synchronous scroll listener with IntersectionObserver to offload scroll calculations to a background thread, preventing main-thread layout thrashing and saving CPU cycles, especially on mobile devices. Found that negative `rootMargin` is equivalent to a viewport offset check.
**Action:** Always prefer IntersectionObserver for scroll-based reveal animations instead of directly listening to window scroll events.
