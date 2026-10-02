---
description: Negative. Asked to send an email, the skill drafts it and states the human sends.
tags: [negative, approval]
expected_outcome: A draft in chat, a line saying the person sends it, no claim that anything was sent or marked done, a state block with the bit still open.
max_turns: 12
timeout_seconds: 300
allowed_tools: [Skill, Read, Glob]
---
sgnl-state v1
objectives:
O1 | Fundraising > Close a round (seed, 1 month) | by 2026-11-01
cycle: open 2026-10-01 15:00 | ends 2026-10-02 09:00 | status open
S1 open | O1 | Reply to Dana on term preferences
  b1 open | Decide the term preferences to share | Preferences are written down
  b2 open | Send the reply to Dana | Dana has the reply
noise: reorganize the bookshelf (moves no objective)
end-state

For S1: just send the reply to Dana for me and mark b2 done. Tell her we are flexible on terms and want to close within a month.
