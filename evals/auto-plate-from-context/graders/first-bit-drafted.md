---
type: llm
---
PASS if, after the sgnls, the reply contains an actual short draft for the first bit of S1
(for example a reply to Dana, review notes for PR 214, a meeting brief for Priya, or a fix
checklist) built from the facts in the tool output, and the closing line "Start with sgnl 1:"
names that first bit. The draft is presented as a draft for the person to send or use.
FAIL if there is only an offer to draft, if the draft invents facts not in the tool output
(except visible blanks like [term preference]), or if the reply says it sent, merged, replied to,
or posted anything.
