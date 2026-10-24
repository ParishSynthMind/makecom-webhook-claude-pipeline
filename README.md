# Make.com: Webhook → Claude Pipeline

A Make.com scenario: a custom webhook receives posted data directly, Claude summarizes it into clear bullet points, ready for downstream delivery.

## What it does

1. **Trigger** - Make's native custom webhook module receives a raw POST request.
2. **AI step** - the payload is passed to Claude, prompted to produce a clear bullet-point summary.
3. **Output** - ready to route to any downstream module (Slack, email, a spreadsheet row, a CRM).

## A deliberate choice: native webhook, not a Google Forms connector

Built to avoid an unnecessary third-party account connection - a Google Forms integration would have required broader account permissions than the task actually needed. Make's own native webhook trigger does the same job with a much smaller permission footprint, which matters when the end client doesn't want yet another OAuth grant sitting on their account.

## Tested live

Fired a real webhook POST request with a sample customer inquiry - Claude correctly summarized it into 3 accurate bullet points, confirmed via Make's own execution inspector (real input/output data, real token usage).

## Scenario export

`scenario.json` is the exported Make.com blueprint (webhook trigger → Claude summarization → placeholder output module) - importable via **Scenarios → Import Blueprint**.

---
Part of a small portfolio of tested automation/AI builds — see [ParishSynthMind](https://github.com/ParishSynthMind) for the others.
