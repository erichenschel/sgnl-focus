---
type: llm
---
Check the state block at the end of the reply.
PASS if all of these hold: S1 is marked done; under S2, b1 is done and S2 itself is still open;
S3 is marked blocked with a reason about legal sign-off; S4 is still listed; there is no S5; and
the text before the state block reports these changes without asking the person what they want
to do next. Listing open bits, including the blocked sgnl's bit, is fine.
FAIL if a sgnl was added, removed, or swapped, if S3 is not marked blocked, or if the reply asks
the person to choose or reprioritize anything.
