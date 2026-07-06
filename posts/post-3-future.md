Where I'd take this next, if there's a reason to.

Right now it checks one pasted block of text: invisible characters, the Unicode tag
block, bidi overrides, homoglyphs, and a small phrase heuristic. That covers the
"paste a prompt or a scraped page" case.

Two extensions I parked instead of building:

A small corpus of known injection payloads as a JSON fixture, so it doubles as a
red-team dataset, not just a single demo string.

A mode built for tool-call output specifically, since MCP and agent tools pass
untrusted text around just as often as prompts do, and that's a slightly different
shape of input.

Neither is built. I'd rather hear whether either one is actually useful to someone
before I add it.

If you build or run agents that ingest scraped content, tool output, or pasted user
text, I'd like to know what your actual exposure looks like. Happy to compare notes.

LIVE_URL

#AIsecurity #AIagents
