## 2025-01-20 - Unused Class Querying in Scroll Handler
**Learning:** Found an anti-pattern where a scroll event continuously queried the DOM (`querySelectorAll('.scroll-reveal')`) and forced a reflow (`getBoundingClientRect().top`), even though there were no `.scroll-reveal` elements in the document. This caused unnecessary layout thrashing on every scroll tick.
**Action:** Always check if elements exist before attaching scroll listeners or observers to them, and prefer `IntersectionObserver` over synchronous DOM queries in scroll handlers to prevent main-thread blocking.
