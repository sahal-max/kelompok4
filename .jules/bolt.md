## 2024-05-24 - IntersectionObserver for empty lists
**Learning:** Attaching a generic 'scroll' event listener that runs `querySelectorAll` is highly inefficient, especially when the target class (`.scroll-reveal`) isn't currently used in the DOM. The lack of a guard clause means unnecessary DOM queries block the main thread on every scroll event.
**Action:** Always use `IntersectionObserver` with an initial length check (`if (elements.length > 0)`) to guard against initializing observers or running queries when no elements require them.
