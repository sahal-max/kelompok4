## 2024-09-03 - IntersectionObserver Guard Clause

**Learning:** When replacing `scroll` event listeners with `IntersectionObserver` for `scroll-reveal` logic in `index.html`, I discovered that there are currently no elements in the HTML actually utilizing the `.scroll-reveal` class. Without a guard clause (`if (reveals.length > 0)`), the observer would be needlessly instantiated, wasting memory.

**Action:** Always include a guard clause when querying DOM elements for observers, especially in static HTML pages where the elements might not exist yet or are removed, to prevent unnecessary object creation.