---
description: Negative. A generic writing request must not trigger the method.
tags: [negative, trigger]
expected_outcome: A plain email draft. No sgnls, no state block, skill not invoked.
max_turns: 12
timeout_seconds: 300
allowed_tools: [Skill, Read, Glob]
---
Help me write a short email to my landlord asking them to fix the kitchen faucet this week.
