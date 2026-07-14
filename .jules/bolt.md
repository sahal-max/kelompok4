## 2024-05-18 - Replacing window scroll listeners with IntersectionObserver
**Learning:** Attaching scroll listeners to `window` for simple reveal animations causes severe layout thrashing and high main-thread blocking, which can drop scrolling frames below 60FPS.
**Action:** Always prefer `IntersectionObserver` when determining element visibility instead of manual bounding box calculations on `scroll` events, as it delegates the work off the main thread.
