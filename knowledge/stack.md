---
type: Tech Stack
title: prompt-injection-linter stack
description: 'Frameworks, storage and services prompt-injection-linter runs on.'
runtime: Browser
framework: 'None. Plain HTML, CSS and JavaScript.'
build: 'None. Single page, one script file, no dependencies.'
storage: 'None. Nothing you paste is uploaded or stored.'
hosting: GitHub Pages
tests: 'node test.js'
generated:
  by: claude-opus-5
  at: '2026-07-29T04:24:12+00:00'
status: stable
---

# Stack

* **Runtime**: the browser. There is no backend and no framework.
* **Framework**: none. Single page, one script file, no build step, no dependencies.
* **Files that carry the logic**: `index.html` for the page, `core.js` for all the detection
  and sanitise logic as plain functions, `test.js` for the suite.
* **Storage**: none. Nothing pasted is uploaded.
* **Hosting**: GitHub Pages.
* **Tests**: `node test.js`.

## Notes

`core.js` runs unchanged in both the browser, as globals, and Node. The claim that nothing
leaves the page is checkable: open the Network tab while using it and it stays empty.
