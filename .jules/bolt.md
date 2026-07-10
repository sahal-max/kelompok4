## 2024-04-10 - Render Blocking Scripts in Static Sites
**Learning:** Found a render-blocking script tag (`<script src="...">`) in the `<head>` for `Chart.js` which blocks the first contentful paint (FCP) of the static HTML site.
**Action:** Adding the `defer` attribute to external scripts loaded in `<head>` (especially heavy ones like Chart.js) ensures they don't block HTML parsing, allowing the page to render faster without waiting for the script to download and execute.
