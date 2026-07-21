## 2024-05-24 - Unconditional Scroll Listeners
**Learning:** The codebase used an unconditional, continuous `scroll` event listener that queried the DOM (`document.querySelectorAll`) and caused layout thrashing (`getBoundingClientRect`), even when no elements matched the selector.
**Action:** Always prefer `IntersectionObserver` over `window.addEventListener('scroll')` for visibility checks to delegate tracking to the browser and eliminate main-thread layout thrashing.
