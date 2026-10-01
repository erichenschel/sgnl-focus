---
description: Negative. A request to add a sixth sgnl gets one reminder and goes to the next cycle.
tags: [negative, during, cap]
expected_outcome: One-line reminder, passport in next:, five sgnls unchanged, no S6.
max_turns: 12
timeout_seconds: 300
allowed_tools: [Skill, Read, Glob]
---
sgnl-state v1
objectives:
O1 | 20 paying customers for the bookkeeping app | by 2026-12-31
O2 | v2 live in the app store | by 2026-11-15
O3 | 3 essays published on my blog | by 2026-12-31
cycle: open 2026-10-01 07:00 | ends 2026-10-02 01:00 | status open
S1 open | O2 | Fix the export crash
  b1 open | Reproduce the crash on the test phone | crash steps written down
  b2 open | Patch the date parser | export works on the test file
S2 open | O1 | Send the pricing page to the 5 trial users
  b1 open | Draft a 4-line email with the link | draft ready
  b2 open | Send it to all 5 | 5 sent
S3 open | O2 | Submit the v2 build for review
  b1 open | Upload the build | build in the review queue
S4 open | O1 | Book 3 customer calls
  b1 open | Send a booking link to the 5 trial users | link sent
  b2 open | Confirm 3 slots | 3 calls booked
S5 open | O3 | Draft the cash vs accrual essay
  b1 open | Write the outline | 5 headings
  b2 open | Write the first draft | 800 words
noise: reorganize the bookshelf (moves no objective); renew passport (moves no objective)
end-state

Add a sixth sgnl: renew my passport. It has to happen today.
