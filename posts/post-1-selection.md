I found the same bug described three different ways in one week.

Anthropic's own research on prompt-injection defenses.
Palo Alto Unit42 reporting indirect prompt injection in the wild, on real web pages.
Promptfoo showing zero-width Unicode can silently backdoor AI-generated code.

Same root cause every time: text can carry characters a model reads and a human never
sees. Invisible Unicode, a whole block that mirrors the ASCII table but renders as
nothing, letters swapped for Cyrillic or Greek lookalikes.

Then I looked for a tool that checks the text going INTO an agent, before you paste it
into a prompt. Not a browser extension that scans the page you're reading. Something
for the builder's side of the interaction.

I couldn't find one. So I built one.

Paste text, see what's hiding in it, decode it, sanitize it. No account, no upload, no
model call for the detection itself, just Unicode analysis running in your browser.

Build post and demo coming next.

#PromptInjection #AIsecurity
