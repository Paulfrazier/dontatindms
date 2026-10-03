# Contributing a scenario to Don't @ in DMs.

Thanks for helping sharpen this quiz. Scenarios live in one place and the bar is low.

## TL;DR

1. Fork on GitHub and open `spec.json` (source of truth; `index.html` is rendered from it via `fairpoint-kit/render.py`).
2. Scenarios live in the `"scenarios"` array.
3. Inside `"scenarios": [ … ]`, copy the template below and fill it in.
4. Open a PR. Keep it to one or a few scenarios.

## Scenario template

```json
{
  "q": "What someone is about to do, in one sentence.",
  "correct": "plain",
  "why": {
    "plain": "Why no-@ is right/wrong here.",
    "at": "Why the @mention is right/wrong here."
  }
}
```

Where each `why` entry is what you'd say if the reader picked that choice.

## The choices for this site

- `plain` — Just send it — no @
- `at` — Add the @mention

`correct` must be exactly one of those keys, and `why` must have an entry for **every**
key (no more, no fewer). The site validates this — a mismatched scenario won't render.

## Style

- Bias the bank toward the pedagogical point — most answers should be **`plain` (no @)**.
- Keep `q` to one sentence. Quote-style ("you reply: …") works well.
- Keep each `why` punchy — one sentence, and **name the failure mode** for wrong answers.
- The quiz shuffles every session, so order doesn't matter.
- Copy is opinionated and concrete. No hedging, no filler.

More from [Fairpoint](https://fairpoint.website).
