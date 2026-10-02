---
description: Positive. Infers objectives from context the assistant already holds, with no objectives typed.
tags: [positive, objectives, inferred]
expected_outcome: Two catalog picks (a seed round and waitlist signups) with one line of evidence each, one ask to confirm or dismiss, nothing asked as a form, a state block with draft objectives.
max_turns: 12
timeout_seconds: 300
allowed_tools: [Skill, Read, Glob]
---
[Context the assistant already holds from earlier in this chat and its memory for this person]
- Earlier in this chat the person said: "We are raising a seed round and want it closed within a month. I have 12 investor conversations going."
- Memory note: the product waitlist is at 140 signups; the person wants 500 by Dec 15, 2026.
- Today is 2026-10-02.

[New message]
Start my SGNL.
