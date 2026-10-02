# Changelog

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
