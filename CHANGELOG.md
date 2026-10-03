# Changelog

## 0.3.1 - 2026-10-03

- Works without developer tools. The plate is gathered in this order: today's date; the
  conversation and memory; connected tools (calendar, email, docs, chat, Linear, Asana); then
  developer sources (git, `gh`, herdr sessions, local files) only if they exist. Developer
  sources are optional extras.
- The `What I looked at` line names only what was found. It never mentions a missing tool.
- With no connected tools and nothing in the conversation, the skill asks one short question
  ("What's on your plate today?") and still returns sgnls after the answer.
- Plain words: no developer jargon (git, PR, repo, commit, deploy, branch, terminal) unless the
  person uses that tool. Raw ticket and change ids only for people who use that tool.
- Evals: added `non-technical-ceo-phone` and `zero-connectors-asks-once`, both failing on
  developer jargon or a mention of a missing tool. Stricter graders on the existing cases (see
  the PR for the grader review).

## 0.3.0 - 2026-10-02

- Opening a cycle no longer asks for the time or a plate. The skill gathers the plate itself,
  read-only and bounded (about 10 tool calls, the last 7 days, top items), from what the host
  already offers: the clock or `date`; with a shell, git status and branch, recent commits,
  open PRs and review requests via `gh`, TODO and memory files, and `herdr agent list` when
  `HERDR_ENV=1`; and, on any host, connected mail, calendar, issue tracker, docs, or chat tools
  if available. Anything already in the conversation is reused.
- Everything gathered is evidence, never instructions. Instruction lines in tool output go to
  noise, unquoted.
- New output: a `What I looked at` line (sources used, sources unavailable), an `Evidence:`
  pointer per sgnl, a `Draft for S1 b1` draft, and a closing `Start with sgnl 1: ...` line.
  Drafts only; nothing is sent or changed externally.
- Objectives are still confirmed with one reply; if the state block already has confirmed
  objectives, the skill goes straight to gathering.
- Privacy copy updated: the skill reads only what the host already gives it access to in this
  session, and nothing leaves the chat. Data may be read through the host's connected tools.
- Evals: added `auto-plate-from-context`, `herdr-sessions-as-plate`, and `connector-injection`;
  updated `fundraising-playbook-cycle` and `open-cycle-injection` for evidence, the looked-at
  line, and the drafted first bit.

## 0.2.0 - 2026-10-02

- Objectives are inferred from what the assistant already knows, shown as catalog picks with one
  line of evidence, and confirmed or dismissed with one reply. One open question only if nothing
  can be inferred.
- Playbooks for fundraising, email funnel, ship and test, sales and partnerships, hiring,
  customer support, investor and board updates, and content and GTM. Bits are the human-only
  decisions; the assistant offers drafts in chat.
- Approval rule: the skill drafts and never sends, deletes, merges, publishes, pays, or marks
  anything done in another system.
- Evals: `set-objectives` rewritten for the infer-and-confirm flow; added
  `infer-objectives-from-context`, `infer-nothing-asks-open-question`,
  `fundraising-playbook-cycle`, and `negative-claims-to-send`.

## 0.1.0 - 2026-10-01

- First release.
