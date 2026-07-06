# PRD: Prompt Injection Linter

**One-liner:** A free single-page tool that reveals hidden prompt-injection payloads in
any text you are about to feed an AI agent, decodes the smuggled instructions, and lets
you sanitize it, running entirely in your browser so the suspicious input never leaves
your device.

**Usefulness:** Attackers hide instructions inside text using invisible and zero-width
Unicode, the Unicode tag-character range, homoglyphs, and bidi overrides. The model reads
them; humans and most filters do not. Palo Alto Unit42 has documented indirect prompt
injection in the wild on real web pages, Promptfoo showed zero-width Unicode can silently
backdoor AI-generated code, and Anthropic publishes its own prompt-injection defense
research. Anyone building an agent that ingests web content or user text has this
exposure today, and there was no prompt-engineer-facing linter for the text going into
the agent (existing tools scan pages you browse, not text you are about to paste into a
prompt). Paste, see the hidden payload decoded, sanitize, done.

## v1 scope (built)

1. One input: paste a block of text.
2. Five detection passes, each a pure function in `core.js`:
   - invisible / zero-width characters
   - Unicode tag-character range (U+E0000 to U+E007F)
   - bidi override / isolate characters
   - homoglyphs of ASCII letters (curated Cyrillic/Greek map)
   - a small heuristic list of injection instruction phrases
3. A decoded payload view that reconstructs any instruction smuggled in the tag-character
   range into readable text.
4. A Sanitize button that strips the invisible/tag/bidi layer, then re-scans and confirms
   the hidden layer is clean.
5. A short inline explainer for each detection category with one real example, plus a
   plain-text source list.
6. A built-in Load example fixture: a benign-looking sentence with a hidden zero-width and
   tag-character payload, so the demo works in one click with no typing required.

## Non-goals (not built, per brief)

- Accounts or saved scans.
- A browser extension.
- Any model call for the core detection.
- An API or a "pro" tier.
- Batch file upload.

## Demo path (2 minutes)

1. Open `index.html`.
2. Click Load example. The box fills and scans automatically.
3. See the hidden zero-width character and tag-character payload reported, and the
   decoded instruction text shown in the Decoded payload box.
4. Click Sanitize. See the hidden layer removed and the re-scan report "clean," with the
   visible sentence unchanged.
5. Optionally paste your own text and click Scan.

## Done-when checklist

- [x] The page loads and turns a text with a hidden payload into a visible decoded
      payload in under 2 minutes, using only the Load example button.
- [x] A known-bad sample (the built-in fixture) is detected and, after Sanitize, re-scans
      clean. Proven in `test.js` and independently exercised against the live
      `index.html` UI logic.
- [x] README explains each detection category with sources.
- [x] Copy passes a no-em-dash sweep.
- [x] Nothing requires sign-up; no network request happens during a scan.

Mid-build ideas that came up and were not built go in `parking_lot.md`.
