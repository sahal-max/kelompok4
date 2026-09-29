1. **Create/Update Journal (.jules/bolt.md)**
   - Add a critical learning about the `.scroll-reveal` anti-pattern: the `scroll` event listener queries the DOM on every scroll event even when no `.scroll-reveal` elements exist, causing unnecessary main thread work. The solution is an `IntersectionObserver` with a guard clause.
2. **Verify Journal Creation**
   - Use `cat .jules/bolt.md` to ensure the journal entry was correctly written.
3. **Optimize `index.html`**
   - Replace the synchronous `scroll` event listener with an `IntersectionObserver` in `index.html`.
   - Initialize via `initRevealObserver()`.
   - Include a guard clause to prevent execution when the `.scroll-reveal` class is unused.
   - Configure the callback to check `entry.isIntersecting || entry.boundingClientRect.top < 0` and call `observer.unobserve(entry.target)`.
   - Add a comment explaining the performance optimization.
4. **Verify `index.html` modification**
   - Use `grep` or `cat` to verify the new `IntersectionObserver` logic was written successfully in `index.html`.
5. **Frontend Verification**
   - Use `frontend_verification_instructions` to generate a Playwright script to verify the frontend works without errors, then mark as `frontend_verification_complete`.
6. **Pre-commit Steps**
   - Complete pre-commit steps to ensure proper testing, verification, review, and reflection are done.
7. **Submit Changes**
   - Create PR titled "⚡ Bolt: [improvement]" with description sections "💡 What", "🎯 Why", "📊 Impact", and "🔬 Measurement".
