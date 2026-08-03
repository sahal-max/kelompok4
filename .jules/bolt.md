## 2026-08-03 - IntersectionObserver for Scroll Animations
**Learning:** Attaching standard event listeners like `scroll` combined with synchronous DOM calculations (e.g. `getBoundingClientRect()`) causes massive layout thrashing on the main thread, leading to janky performance during user interaction.
**Action:** Always prefer `IntersectionObserver` over explicit `scroll` event listeners for implementing visibility triggers or scroll animations, and include checks for elements already past the viewport if initialized after a reload.
