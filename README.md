# Prompt Cutter — Cut Input AI Token Usage

A client-side tool that compresses prompts before you send them to an AI
model — stripping filler words and redundant phrasing while preserving the
task, the facts, and the constraints — so you spend fewer tokens per request
without changing what you're asking for.

**[Live demo](https://www.promptcutter.com)**

## What it does

Paste (or dictate) a prompt, and it:

1. Detects the task type — write email, translate, fix a bug, summarize,
   explain, generate content — from phrasing and keywords
2. Strips stopwords, filler phrases, and redundant wording using a
   dependency-free rule-based pipeline (no API call required for this mode)
3. Tags the compressed prompt with a compact task marker so the receiving
   model still knows exactly what's being asked
4. Shows an estimated token count before/after, with a diff view of what
   was cut
5. Optionally, runs the same compression *live* through the Claude API for
   a higher-quality result (bring-your-own API key, stored locally —
   never sent anywhere but Anthropic)

Voice input is also wired up via the Web Speech API, for dictating a prompt
instead of typing it.

## Why it's not just a demo

Every claim this tool makes about itself has actually been tested, and the
results — including the parts that didn't work — are documented:

- **Compression works, with a measured limit.** A 6-pair downstream A/B test
  (same task, compressed vs. original prompt, fresh chat each side) found
  translate/explain/generate came back essentially equivalent — no
  measurable quality loss. Email, bug-fixing, and summarization each showed
  a real but modest gap: specific details (a line number, an exact
  duration) were present in the compressed prompt but engaged with less
  precisely in the response.
- **Offline mode is English-only, verified rather than assumed.** Testing
  the same request in French, Spanish, and German against the actual
  compression code showed reduction collapsing from 41% (English) to
  roughly -2–3% for the others, with task detection failing outright.
- **The accuracy figure is honestly scoped.** The 95%-accuracy number comes
  from a 38-example set written in-house — documented as such, not
  presented as an external benchmark.

## Stack

Vanilla HTML/CSS/JS, no build step, no dependencies. Web Speech API for
voice input. Anthropic Claude API (Haiku) for the optional live-compression
mode, called directly from the browser with a user-supplied key.

## Status

The compression engine, task detection, and voice input are fully working.
The credits counter, upload/share/members nav buttons, and pricing panel
visible in the UI are front-end previews only — not yet wired to real
functionality, since the backend they'd depend on (hosted API proxy,
payment processing, usage limits) doesn't exist yet. See the project
roadmap for what's planned next: a hosted-key mode so users don't need
their own API key, and a browser extension as a likely better form factor
than a standalone page.

---
*Formerly "Token Saver" — rebranded to Prompt Cutter with a dark navy/red
visual identity.*
