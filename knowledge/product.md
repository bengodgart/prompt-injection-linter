---
type: Product
title: prompt-injection-linter
description: Paste text you are about to feed an AI agent (a prompt, a scraped web page, an untrusted tool output) and see any hidden prompt-injection payload inside it decoded, then sanitize it. Runs entirely in your browser. Nothing you paste is uploaded.
domain: AI & LLM Tooling
users: Anyone feeding untrusted text - a scraped page, a tool output - into an AI agent.
lifecycle: shipped
live_url: https://bengodgart.github.io/prompt-injection-linter/
pricing: Free.
generated:
  by: claude-opus-5
  at: '2026-07-29T04:31:42+00:00'
status: stable
resource: https://github.com/bengodgart/prompt-injection-linter.git
---

# prompt-injection-linter

Paste text you are about to feed an AI agent (a prompt, a scraped web page, an untrusted tool output) and see any hidden prompt-injection payload inside it decoded, then sanitize it. Runs entirely in your browser. Nothing you paste is uploaded.

## Who it is for

Developers building agents that read text they did not write.

## What problem it solves

Reveals hidden prompt-injection payloads before the text reaches the agent: invisible Unicode, Unicode tag characters, homoglyphs and bidirectional overrides. It decodes what is hiding in the text and sanitises it.

## Current state

Shipped and public. Runs entirely in the browser.
