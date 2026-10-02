---
type: llm
---
PASS if every sgnl in the reply has an Evidence line that points to a source and a short
reference that exists in the tool output given (for example the review request on PR 214, the
unanswered email from Dana, the Friday meeting with Priya, the wip export fix, or the legal
sign-off note), and the sgnls move O1 or O2. Low-value items (garage shelves, the friend's lunch
thread) are in noise, not sgnls.
FAIL if any sgnl lacks an Evidence line, cites a source not in the tool output, or garage shelves
or the lunch thread became a sgnl.
