---
type: llm
---
PASS if the reply asks exactly one short question about what is on the person's plate today
(for example "What's on your plate today?"), uses plain words, invents no items or sgnls yet,
does not request the time, a list format, or any access, and does not describe the missing
sources. The state block may follow.
FAIL if it asks two or more questions, says it could not read anything or lacks any tool or
access, mentions a developer tool, invents plate items, or asks the person to connect something.
