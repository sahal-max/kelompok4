## 2024-05-24 - Initial Discovery
**Learning:** Found render-blocking external script in the `<head>` (`Chart.js`) which delays the first paint, and missing preconnects for Google fonts.
**Action:** Always check `<head>` for external scripts missing `defer` or `async` and add `preconnect` to external font domains.
