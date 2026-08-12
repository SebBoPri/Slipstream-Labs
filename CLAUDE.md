# CLAUDE.md

Notes for working in this repo.

## Headless Chrome screenshots

Headless Chrome on this machine ignores `--window-size`. Use `Emulation.setDeviceMetricsOverride` via CDP for any mobile-width screenshot. Plain `--headless --screenshot` renders at 500px and will produce false layout bugs.

`getComputedStyle`/`offsetHeight` on the content of a closed native `<details>` reports it as visible (`display:block`, non-zero height) on this machine's headless Chrome, even with zero custom CSS. The actual paint is correct (content is hidden) — confirmed by screenshot. Don't trust DOM property queries to check open/closed `<details>` state here; take a screenshot instead.
