## 2024-06-19 - Lazy Loading Charting Libraries
**Learning:** Large external charting libraries like Chart.js can be significant render-blocking resources if loaded synchronously in the `<head>`, even if they are only used on a secondary or hidden tab.
**Action:** When working on SPAs or multi-tab single page interfaces, always evaluate if large scripts are needed immediately on initial load. If not, dynamically inject the script tag only when the user navigates to the feature that requires it.
