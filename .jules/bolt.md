## 2024-07-20 - [Avoid Synchronous Layout Thrashing]
**Learning:** Using `getBoundingClientRect()` within an un-debounced scroll event listener forces the browser to calculate layout synchronously on the main thread, leading to severe layout thrashing and scrolling jank, especially on pages with many elements.
**Action:** Replace `scroll` event listeners and manual positional checks (`getBoundingClientRect`) with `IntersectionObserver`. It calculates visibility off the main thread efficiently, and we can `unobserve` elements once their animation is triggered to save memory.
