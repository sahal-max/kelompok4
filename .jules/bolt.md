## 2024-05-20 - Unnecessary Scroll Event Listeners
**Learning:** The `scroll` event listener queries the DOM on every scroll event even when no `.scroll-reveal` elements exist, causing unnecessary main thread work.
**Action:** Use an `IntersectionObserver` with a guard clause to prevent execution when the `.scroll-reveal` class is unused. Configure the callback to check `entry.isIntersecting || entry.boundingClientRect.top < 0` and call `observer.unobserve(entry.target)`.
