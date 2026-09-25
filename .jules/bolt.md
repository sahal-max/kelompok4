
## 2024-05-24 - Avoid querying the DOM with scroll event listeners
**Learning:** The codebase previously contained a generic scroll event listener (`window.addEventListener('scroll', revealOnScroll)`) that executed on every scroll event tick. Inside the handler, `document.querySelectorAll('.scroll-reveal')` was repeatedly executed, causing expensive layout thrashing and main thread blocking, even when no matching elements were present.
**Action:** Always replace scroll-based visibility checks with `IntersectionObserver`. Include a guard clause (`if (elements.length === 0) return;`) to avoid unnecessary observer initialization when the targeted elements don't exist in the current DOM.
