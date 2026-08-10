## 2024-10-15 - Scroll Event Listeners Without Elements
**Learning:** A global `scroll` event listener that queries the DOM (`document.querySelectorAll('.scroll-reveal')`) runs continuously on every scroll event, causing layout thrashing and main thread blocking, even if the class `.scroll-reveal` is entirely absent from the page.
**Action:** Always wrap scroll observers or event listeners in a guard clause (`if (elements.length > 0)`) to ensure the expensive logic and observer instantiation is completely bypassed when unnecessary.
