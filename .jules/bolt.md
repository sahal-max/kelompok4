## 2024-05-30 - Replace Scroll Event Listeners with IntersectionObserver
**Learning:** Attaching continuous layout queries (`getBoundingClientRect`) to un-debounced `scroll` events blocks the main thread, causing severe scrolling jank and high CPU usage.
**Action:** When implementing scroll-based reveal animations, always replace synchronous scroll event listeners with `IntersectionObserver` to leverage asynchronous, hardware-accelerated intersection calculations.
