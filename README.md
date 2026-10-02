# SGNL Focus

![SGNL Focus icon](assets/icon.png)

SGNL Focus is a skills-only plugin with one skill, `sgnl-cycle`. It runs the SGNL method inside
one conversation: a fixed planning cycle where every item on your plate is scored against 1 to 3
measurable objectives, only 3 to 5 items make the cut for the next 18 hours, the list does not
change mid-cycle, you report only done or blocked, and you close with a ratio of focused hours
against a target and a floor. A short state block lets a cycle resume in a new chat.

The skill does not use your calendar, inbox, code, or files, even when your assistant can access
them. It works from what you type and what your assistant already knows in the conversation and
its memory.

The skill drafts; you act. It never sends, deletes, merges, publishes, pays, or marks anything
done in another system, and never says it did. Ask it to send an email and it gives you the
draft and says you send it.

## What it does

1. **Objectives, inferred.** On first use the skill infers 1 to 3 objectives from what your
   assistant already knows and anything you paste. Each is a catalog pick such as
   `Fundraising > Close a round (seed, 1 month)`, with a date and one line of evidence. You
   confirm or dismiss with one reply. If nothing can be inferred, it asks one question: "What
   are you working toward this month?" You never fill a form.
2. **Open a cycle.** You give the time and an unsorted dump of everything on your plate. The skill
   scores each item against your objectives and returns 3 to 5 sgnls, the items that move an
   objective inside its horizon. Each sgnl has 1 to 5 bits (do, expect). The skill recognizes the type of work and applies a
   playbook: trigger, what the assistant prepares, what you decide. Your bits are the decisions
   only you can make, and the skill offers to draft the rest in chat. Everything else is noise,
   listed once with a reason. The cycle ends 18 clock hours after it opens; sleep inside it does
   not count against the ratio, which divides by awake hours.
3. **During the cycle.** You report done (naming bits) or blocked. New items wait for the next
   cycle. The sgnls do not change mid-cycle.
4. **Close.** You give hours per sgnl and awake hours. The skill returns a ratio (sgnl hours over
   awake hours; target 80, floor 50), a recap, and carries blocked and unfinished sgnls forward.
   Noise is dropped.

Every reply ends with a short state block. Paste it into a new chat to resume.

## Playbooks

Fundraising (investor replies, follow-ups for quiet investors, meeting prep brief, investor
update, thin pipeline), email funnel, ship and test, sales and partnerships, hiring, customer
support, investor and board updates, content and GTM. See
`skills/sgnl-cycle/references/playbooks.md`.

## Data

The plugin has no server, no scripts, no hooks, and no MCP servers. It makes no network calls and
keeps no record outside your chat. Its only output is the state block in your own conversation.
Inferring objectives reads only context your assistant already holds in the conversation and its
memory; the skill searches nothing further. Your assistant app's chat history and memory settings
still apply to that conversation, under its own privacy policy. The skill does not ask for health details, account numbers, IDs, or
credentials, leaves them out of the state block if you offer them, and does not track health
objectives. See [PRIVACY.md](PRIVACY.md).

## Install

### Claude Code

```bash
claude plugin marketplace add erichenschel/sgnl-focus
claude plugin install sgnl-focus@sgnl-focus
```

### Claude apps (web and desktop)

1. Zip this folder: `zip -r sgnl.zip . -x '.git/*' 'evals/results/*'`
2. In Claude, open Customize > Plugins > Add > Upload plugin and choose `sgnl.zip`.

Plugins in the Claude apps need a paid plan.

### ChatGPT desktop app (local testing)

1. Copy this folder to `~/plugins/sgnl-focus`.
2. Create `~/.agents/plugins/marketplace.json`:

```json
{
  "name": "local-sgnl",
  "plugins": [
    {
      "name": "sgnl-focus",
      "source": { "source": "local", "path": "./plugins/sgnl-focus" },
      "policy": { "installation": "AVAILABLE", "authentication": "ON_INSTALL" },
      "category": "Productivity"
    }
  ]
}
```

3. Restart the ChatGPT desktop app, open the Plugins Directory, choose the `local-sgnl` source,
   install SGNL Focus, and start a new chat.

## Starter prompts

Each works in a new chat. They are also the `defaultPrompt` entries in `.codex-plugin/plugin.json`.

- Start my SGNL. Infer my objectives from what you know about my work and show me the evidence.
- Open an SGNL cycle. It is Thu 2026-10-01 09:00. My plate: fix export bug, email 5 trial users, tidy desk.
- Explain the SGNL method in five lines, then propose my objectives.

## Files

- `.claude-plugin/plugin.json`: the Claude plugin manifest.
- `.codex-plugin/plugin.json`: the OpenAI (ChatGPT and Codex) manifest, with the listing fields
  in `interface`.
- `skills/sgnl-cycle/SKILL.md`: the method.
- `skills/sgnl-cycle/references/`: the state block format, reply templates, the objective catalog and playbooks, and a worked example.
- `evals/`: test cases for `claude plugin eval`.

## Support

Open an issue at https://github.com/erichenschel/sgnl-focus/issues. See [SUPPORT.md](SUPPORT.md).

## License

MIT. See [LICENSE](LICENSE). Use is subject to [TERMS.md](TERMS.md).
