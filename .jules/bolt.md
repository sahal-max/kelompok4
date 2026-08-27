## 2024-08-27 - IntersectionObserver and unobserve
**Learning:** The intersection observer triggers elements to be revealed when scrolling. Once an element is revealed, it doesn't need to be observed anymore since it only adds a class and never removes it.
**Action:** When using IntersectionObserver for one-time scroll reveals, call observer.unobserve(entry.target) immediately after triggering the effect to free up memory and calculation overhead.
