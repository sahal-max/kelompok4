## 2024-05-18 - Deferring external scripts for FCP improvement
**Learning:** Loading large external libraries like Chart.js synchronously in the `<head>` blocks HTML parsing and delays First Contentful Paint (FCP).
**Action:** Always add the `defer` attribute to external `<script>` tags, especially those that only need to execute after the DOM is fully parsed, to prevent render-blocking.
