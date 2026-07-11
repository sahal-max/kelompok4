## 2024-07-11 - IntersectionObserver Optimization
**Learning:** Found a classic performance bottleneck in the codebase architecture: layout thrashing caused by querying `.getBoundingClientRect()` inside a synchronous `scroll` event listener for scroll reveal animations.
**Action:** Replace synchronous `scroll` listeners with `IntersectionObserver` to allow the browser to manage visibility checks asynchronously and off the main thread.
