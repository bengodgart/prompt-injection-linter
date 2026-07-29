---
type: Playbook
title: Run prompt-injection-linter locally
description: 'How to open prompt-injection-linter and run its tests on a dev machine.'
generated:
  by: claude-opus-5
  at: '2026-07-29T06:00:00+00:00'
status: stable
---

# Steps

1. Clone the repo: `git clone https://github.com/bengodgart/prompt-injection-linter.git`
2. `cd prompt-injection-linter`
3. `python -m http.server 8000`, or just open `index.html` directly.

The deployed copy is at https://bengodgart.github.io/prompt-injection-linter/.

## Available scripts

* `node test.js` runs the test suite.

## Common failures

* None recorded. The page fetches nothing, so it works from disk as well as over a server.
